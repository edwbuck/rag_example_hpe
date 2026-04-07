# RAG Example HPE
This repository contains the tracked items for the programming assignment given
to Edwin Buck by HPE as a demonstration of Edwin's ability to design, program,
and create a Retrival Augmented Generation solution.

There are two solutions in this submission:

- The first is a simple extension of
[Huggingface "Simple RAG from Scratch" article](https://huggingface.co/blog/ngxson/make-your-own-rag)

- The second solution uses python classes to illustrate the components highlited in the assignment.

## Installation requirements

Installation documentation is located in "architecture/Installation.md" along with other documentation
providing an Overview and Design Choices.  Your platform may require tuning or adapatation of the
installation documentation, depending on platform details, like firewall setup, differences in operating
systems, and alterations for port conflicts.

We recommend that you use a conda managed virtual environment, and launch your `jupyter-lab` instance in
that virtual environment to protect against polluting your Python package installations.  Additionally,
we recommend that you create a new Jupyter Kernel, to ensure that your in-Jupyter Notebooks also use
the same virtual enviornment.

We require the installation of ollama, and depending on your installation approach, you many need to
launch ollama independetly with `ollama serve` prior to running these notebooks.  Non-default ports (not 11434)
may require additional setup and work, not descibed in the installation documentation.

## VENV instructions

The typical apply

```
python -m venv env source env/bin/activate 
pip install -r requirements.txt
```

Where possible, installations are performed within the Jupyter Notebooks.  Take care to read the
`architecture/Installation.md` document to caputre the details of venv setup for JupyterLab and
the kernel creation / installation into the venv to keep your regular environment pristine, or
ignore it all and install into your system environment.

## simple_all_in_one.ipynb

This notebook contains all of the code necessary to demonstrate a fully functional, but simple RAG 
(Resource Augemented Generation) approach.  It lacks the rigor of clarifying the key components, but
was useful in determining the basic interactions of the involved components.

## rag_create_kb.ipynb and rag_chatbot.ipynb

These notebooks contain similar code that also demonstrates a fully functional RAG approach.  However,
it takes care to highlight the components by mapping each of the following components to a Python class:

- Knowledge Base: a repository of textual information and its encoded semantic vectors
- Semantic Layer: a translation service of texual information to encoded semantic vectors
- Retrieval System: a lookup mechanisim to find the closest knowledge based text, calculated by semantic
  vector similarity to the querying semantic vector.
- Augmentation: a system for combining user messages with system messages, seeking to improve LLM output
  of a language generating model.
- Generation: an interface that accepts messages and generates textual output based on its backing LLM.

Additionally, it includes a few utility componenets, supporting the key components above

- DocumentLoader: an interface that wraps the text file input, splitting each "document" or line of
  information so it can be processed independently.
- UserInput: a source of user input messages, promting the user in a REPL-like manner, handling when
  the user declines to continue the session.
s
## Known design limitations

- The components are all in the same directory as the submissions, cluttering the notebook space.

  The challenges of getting a Jupyter Notebook to load a class as if it were part of a module, once
  solved, were enough.  Upon putting the items into a sub-foder, new errors arose.  These could be
  investigated and fixed, but improvements in code maintenance would likely take the entire system out
  of a Jupyter Notebook enviornment.

- Unit tests were not developed

  Automated testing is paramount to quality code.  However, Jupyter Notebooks present a few challenges
  that were not deeply investigated when inports from other directories and the desire to hide unit tests
  under a testing folder were initially attempted.  As these were not the focus of the effort, little
  work was done to address the lack of unit testing, even though it is paramount to production software
  stability (which was explicitly not a goal of the exercise). 
    
- Only the cosine distance is supported by the Retrieval System

  Instead of `getCosineNearest(...)` a `getNearest(method='cosine', ...)` approach would provide flexibilty
  in leveraging different algorithms for selecting the nearest vectors to a vectorized input.  As this
  doesn't provide additional illustrative power as to how a RAG works, it was not persued.

- The solution does not use a standalone vector database

  This was originally an early design goal; however, in the early prototyping phases, the deployment
  instructions were deemed too laborious for a casual reviewer (and seemed very specific to my Fedora
  laptop).  Initially pgvector and Postgres was selected, but due to their poor performance, the project
  shifted to considering other vector databases.

  As weighing and reviewing the relative merits of other vector databases took its toll, a pivot was made
  to simply marshal the knowledge base, implemented as a pair-array in simple_all_in_one.ipynb Knowledge
  to disk.  This would provide the means to split the creation / maintenance of the Knowledge Base from
  its loading and use, permitting two Jupyter Notebooks to capture the separate workflows. 

