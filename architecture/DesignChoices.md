# Design Choices

This captures the design choices of the RAG demo for HPE's pre-hiring process.

## Required Componenets

* Knowledge Base 
* Semantic Layer
* Retrieval System
* Augmentation
* Generation

## Deliverables

* A 10 minute presentation.

  * Slide deck (estimated 10 slides, 8 of content)
    * Introduction
    * Use case details
    * Architectural overview
      * Architectural component diagram
      * Architectural deployment diagram
    * Functional overview
      * Communication overview
      * Sequence of building knowledge base
      * Sequence of querying knowledge base
    * Conclusion

* A 5 minute question and answer session after the presentation.

  * Development of a Q & A section
  * Exposure of the archtectural notebook
  * References to supporting sources

* A 45 minute review and defense of the solution

  * Explanation of each line of code (where applicable)

* A RAG encompassing the solution

  * Implemented in Python
  * Jupyter Notebook environemnt
  * Configuration captured into notebook (where applicable)
  * Additional resources to recreate enviornment in a foreign environment.

## Evaulation

* Commitment to schedule
* Communication during effort
* Deliverables

## Problem Space

The demo is intended to illustrate the design and implementation process of
creating a RAG (Retrieval-Agumented Generation) solution.  The content being
retreived and the utility of the data being presented is not the focus, and is
an unbound constraint.

For this reason, I want a problem space that is

- Somewhat familiar to most people, to entice participation.
- Not politically charged, to prevent argumentative discussion.
- Is unlikely to be upturned by subject matter experts, to disruptive discusson
  of the findings.
- Is small, to permit use within the constraints of a personal laptop.
- Is not overly personal, to prevent personal passion from hijacking the
  presentation.
- Is somewhat fun, permitting a bit of levity in a potentially dry presentation
  of code architecture and programming approaches.

To this end, I chose the cat-facts tutorial from HuggingFace.  I determined that
it met all the critera above, and due to its tutorail usage would addtionally
be a known entity to many of the reveiwers.  With this in mind, I hope that
this will focus more on the architecture presentation, and to lessen the
impact of the lack of novelty, I'll add in one or two features.

### Potential features to add

1. Use of an Standalone Vector Database

Currently the tutorial uses an array of vector encodings that act as the vector
database, when third party vector databases exist.  While this simlifies the
tutorial, it would be a natural improvement to include a third party vector
database and the Python code to connect to it, populate it, and query it.

As this is intended for a laptop, Postgres seems a natural choice and Postgres's
extensible nature makes it capable of having vector extensions.  Postgres fully
supports extensions through a relatively simple interface allowing one to add
functionality to the database engine, but before programming a search showed
that a pgvector extension already exists, supporting four different means
of querying for vector distance which works with the remaining LIMIT operation.

Instructions are available at the [pgvector](https://github.com/pgvector/pgvector)
repository.

2. Adding in a data appender.

This idea would add in new cat facts, while keeping an eye on de-duplicating
the added data.  As data will be encoded in vector form, comparison for
de-duplication would be done on a vector basis, with encoding of the new
fact being compared to the existing databse, and the five nearest facts being
presented (likely cosine distance).  This would then be presented to the user
who would confirm or cancel the addition of the previously presented fact.

Datasets that could be used incude:

- [Cat Cognitian](https://catcognition.com/statistics/)
- [Fact Retriever](https://www.factretriever.com/cat-facts)
- [The Discrening Cat](https://thediscerningcat.com/fun-facts-about-cats/)
- [Pet MD](https://www.petmd.com/cat/general-health/fun-facts-about-cats)
- [Fun Facts](https://funfacts.co/fun-facts-about-cats/)

It is worthy to note that some of these datasets are obviously sources of the
original dataset.


## Chunking Strategy

The tutorial uses a chunking strategy of chunks contain isolated facts.

This is suitable for the problem space as the facts are unlikely to ever contain
information that semantically requires the context within a larger body of text
that helps explain or constrain the fact with additional information.

This has the added benefit of keeping the chunks small, reducing the load on the
vector database, reducing the processing of a chunk into a vector, and the
resources required to perform the processing.  As the constraint is to fit
within a laptop, limiting the work to be done and the resources to perform it
is highly desirable, even when Encoding LLMs could support larger chunks and
have additional token size capactity.

The [Hugging Face RAG Demo](https://huggingface.co/blog/ngxson/make-your-own-rag)
contains a cat-facts.txt with one fact per line, and we'll maintain that as the
input data file, mapping each line as a chunk to be vectorized by the Encoding
LLM.

## Component Strategy

* Knowledge Base 
  - Met by the cat-facts.txt text file database.

* Semantic Layer
  - Met by the array vector database
  - Time permitting, met by the Postgres database with the pgvector extension.

* Retrieval System
  - Met by full scans of the array based vector database.
  - Time permitting, met by the SQL like queries supported by pgvector.

* Augmentation
  - Met by combining the vectorized inputs for the query, with the facts
    retrieved by the database.

* Generation
  - Met by the output of an LLM combining the vectorized query and the
    vectorized facts, with additonal directives to control style, tone, and
    other guiding commentary.

## Design Choices within components

* Knowledge Base 
  - Encodings stored in a file, to faclitate separation of knowledge base
    generation and use.

* Semantic Layer
  - Uses Ollama to simplify LLM management.
  - Additionally will pull LLMs into Ollama from Jupyter Notebook to simplify
    deployment efforts.
  - Use cosine distance to select top N matches.

* Retrieval System
  - Uses Ollama to simplify LLM management.

* Augmentation
  - Fully included in Jupyter Notebook.

* Generation
  - Use Ollama to simplify LLM management.


<!-- vim: set ft=markdwon ts=2 sw=2 et ai colorcolumn=80 : -->    
