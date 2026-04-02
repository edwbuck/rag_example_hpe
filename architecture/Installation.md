# Installation of components

## Operating System

Work was performed on Fedora 

## Python

Python was verified to be installed and at version 3.14.3

``` 
edwbuck@fedora:~$ python --version
Python 3.14.3
```

Prior installation of python included the following
```
edwbuck@fedora:~$ which python
/usr/bin/python
edwbuck@fedora:~$ rpm -qf /usr/bin/python
python-unversioned-command-3.14.3-1.fc43.noarch
```

## Jupyter

Prior to installing Jupyter, YUM repositories were checked for
previous Fedora packaging of Jupyter.  This was done with

```
edwbuck@fedora:~$ dnf list | grep jupyter
Updating and loading repositories:
 RPM Fusion for Fedora 43 - Nonfree - U 100% |   1.6 KiB/s |   5.6 KiB |  00m04s
 RPM Fusion for Fedora 43 - Nonfree - S 100% |   1.7 KiB/s |   5.6 KiB |  00m03s
 RPM Fusion for Fedora 43 - Nonfree - N 100% |   1.8 KiB/s |   5.8 KiB |  00m03s
 RPM Fusion for Fedora 43 - Free - Upda 100% |   1.1 KiB/s |   3.2 KiB |  00m03s
 Jenkins-stable                         100% |   1.4 KiB/s |   3.2 KiB |  00m02s
 Fedora 43 - x86_64 - Updates           100% |   8.7 KiB/s |  24.7 KiB |  00m03s
 google-chrome                          100% | 609.0   B/s |   1.3 KiB |  00m02s
 Copr repo for PyCharm owned by phracek 100% | 984.0   B/s |   2.1 KiB |  00m02s
 Adoptium                               100% | 818.0   B/s |   1.7 KiB |  00m02s
 LibreWolf Software Repository          100% | 395.0   B/s | 833.0   B |  00m02s
 Copr repo for TestTextfileProject owne 100% | 753.0   B/s |   1.5 KiB |  00m02s
Repositories loaded.
black+jupyter.noarch                                                                     25.1.0-7.fc43                                                   fedora
gap-pkg-jupyterkernel.noarch                                                             1.5.1-7.fc43                                                    fedora
gap-pkg-jupyterkernel-doc.noarch                                                         1.5.1-7.fc43                                                    fedora
gap-pkg-jupyterviz.noarch                                                                1.5.6-17.fc43                                                   fedora
gap-pkg-jupyterviz-doc.noarch                                                            1.5.6-17.fc43                                                   fedora
jupyterlab.noarch                                                                        4.4.10-2.fc43                                                   updates
lfortran-jupyter.x86_64                                                                  0.56.0-2.fc43                                                   fedora
python-jupyter-filesystem.noarch                                                         5.8.1-5.fc43                                                    fedora
python3-hatch-jupyter-builder.noarch                                                     0.9.1-5.fc43                                                    fedora
python3-jupyter-c-kernel.noarch                                                          1.2.2-29.fc43                                                   fedora
python3-jupyter-cache.noarch                                                             1.0.1-6.fc43                                                    fedora
python3-jupyter-cache+cli.noarch                                                         1.0.1-6.fc43                                                    fedora
python3-jupyter-client.noarch                                                            8.6.1-19.fc43                                                   fedora
python3-jupyter-console.noarch                                                           6.6.3-14.fc43                                                   fedora
python3-jupyter-core.noarch                                                              5.8.1-5.fc43                                                    fedora
python3-jupyter-events.noarch                                                            0.12.0-6.fc43                                                   fedora
python3-jupyter-kernel-singular.noarch                                                   0.9.9-23.fc43                                                   fedora
python3-jupyter-kernel-test.noarch                                                       0.7.0-9.fc43                                                    fedora
python3-jupyter-lsp.noarch                                                               2.3.0-2.fc43                                                    fedora
python3-jupyter-packaging.noarch                                                         0.12.3-19.fc43                                                  fedora
python3-jupyter-polymake.noarch                                                          0.16-35.20180129.7049940.fc43                                   updates
python3-jupyter-server.noarch                                                            2.17.0-2.fc43                                                   fedora
python3-jupyter-server+test.noarch                                                       2.17.0-2.fc43                                                   fedora
python3-jupyter-server-terminals.noarch                                                  0.5.3-9.fc43                                                    fedora
python3-jupyterlab-jupytext.noarch                                                       1.19.1-1.fc43                                                   updates
python3-jupyterlab-server.noarch                                                         2.27.3-8.fc43                                                   fedora
python3-jupyterlab-server+test.noarch                                                    2.27.3-8.fc43                                                   fedora
python3-jupyterlab-widgets.noarch                                                        3.0.15-5.fc43                                                   fedora
python3-jupyterlab_pygments.noarch                                                       0.3.0-12.fc43                                                   fedora
python3-pari-jupyter.x86_64                                                              1.4.3-10.fc43                                                   fedora
python3-pytest-jupyter.noarch                                                            0.10.1-9.fc43                                                   fedora
python3-pytest-jupyter+client.noarch                                                     0.10.1-9.fc43                                                   fedora
python3-pytest-jupyter+server.noarch                                                     0.10.1-9.fc43                                                   fedora
systemtap-jupyter.x86_64      
```

As packages existed, a Fedora specific internet search was performed for Fedora specific Jupyter installation instructions (if any).  As no clear cut solution
was found qickly, I proceeded with 

```
edwbuck@fedora:~$ sudo dnf -y install jupyterlab
Updating and loading repositories:
 RPM Fusion for Fedora 43 - Nonfree - Updates                                                                                                                               100% |   1.0 KiB/s |   5.6 KiB |  00m06s
 RPM Fusion for Fedora 43 - Nonfree - Steam                                                                                                                                 100% |   1.1 KiB/s |   5.6 KiB |  00m05s
 RPM Fusion for Fedora 43 - Nonfree - NVIDIA Driver                                                                                                                         100% |   1.1 KiB/s |   5.8 KiB |  00m05s
 RPM Fusion for Fedora 43 - Free - Updates                                                                                                                                  100% | 664.0   B/s |   3.2 KiB |  00m05s
 LibreWolf Software Repository                                                                                                                                              100% | 196.0   B/s | 833.0   B |  00m04s
 Fedora 43 - x86_64 - Updates                                                                                                                                               100% |   5.3 KiB/s |  24.7 KiB |  00m05s
 Copr repo for PyCharm owned by phracek                                                                                                                                     100% | 517.0   B/s |   2.1 KiB |  00m04s
 google-chrome                                                                                                                                                              100% | 320.0   B/s |   1.3 KiB |  00m04s
 Jenkins-stable                                                                                                                                                             100% | 779.0   B/s |   3.2 KiB |  00m04s
 Adoptium                                                                                                                                                                   100% | 422.0   B/s |   1.7 KiB |  00m04s
 Copr repo for TestTextfileProject owned by edwbuck                                                                                                                         100% | 380.0   B/s |   1.5 KiB |  00m04s
Repositories loaded.
The following OpenPGP key (0xEF5975CA) is about to be removed:
 Reason     : Expired on 2026-03-26 17:11:07
 UserID     : "Jenkins Project <jenkinsci-board@googlegroups.com>"
 Fingerprint: 63667EE74BBA1F0A08A698725BA31D57EF5975CA

As a result, installing packages signed with this key will fail.
It is recommended to remove the expired key to allow importing
an updated key. This might leave already installed packages unverifiable.

The system will now proceed with removing the key.
Key 0xEF5975CA was successfully removed.
Package                                                                 Arch             Version                                                                  Repository                                    Size
Installing:
 jupyterlab                                                             noarch           4.4.10-2.fc43                                                            updates                                   34.9 MiB
Installing dependencies:
 blosc2                                                                 x86_64           2.21.2-1.fc43                                                            fedora                                   566.9 KiB
 google-crc32c                                                          x86_64           1.1.2-12.fc43                                                            fedora                                    28.0 KiB
 grpc                                                                   x86_64           1.48.4-54.fc43                                                           fedora                                    10.5 MiB
 grpc-cpp                                                               x86_64           1.48.4-54.fc43                                                           fedora                                     3.0 MiB
 grpc-data                                                              noarch           1.48.4-54.fc43                                                           fedora                                    29.6 KiB
 libarrow-flight-libs                                                   x86_64           20.0.0-10.fc43                                                           updates                                    1.4 MiB
 libarrow-glib-libs                                                     x86_64           20.0.0-10.fc43                                                           updates                                    1.5 MiB
 pandoc-common                                                          noarch           3.6.4-36.fc43                                                            fedora                                     2.0 MiB
 protobuf-compiler                                                      x86_64           3.19.6-18.fc43                                                           fedora                                     2.5 MiB
 python-jupyter-filesystem                                              noarch           5.8.1-5.fc43                                                             fedora                                     0.0   B
 python-qt5-rpm-macros                                                  noarch           5.15.12-0.1.fc43                                                         updates                                  147.0   B
 python3-Bottleneck                                                     x86_64           1.6.0-1.fc43                                                             updates                                  577.8 KiB
 python3-aiodns                                                         noarch           3.6.1-1.fc43                                                             updates                                   75.4 KiB
 python3-aiohappyeyeballs                                               noarch           2.6.1-9.fc43                                                             fedora                                   102.5 KiB
 python3-aiohttp                                                        x86_64           3.13.3-4.fc43                                                            updates                                    4.1 MiB
 python3-aiosignal                                                      noarch           1.4.0-4.fc43                                                             fedora                                    24.8 KiB
 python3-argon2-cffi                                                    noarch           23.1.0-8.fc43                                                            fedora                                    72.7 KiB
 python3-argon2-cffi-bindings                                           x86_64           21.2.0-13.fc43                                                           fedora                                    51.3 KiB
 python3-arrow                                                          noarch           1.3.0-5.fc43                                                             fedora                                   612.0 KiB
 python3-asttokens                                                      noarch           3.0.0-5.fc43                                                             fedora                                   199.2 KiB
 python3-async-lru                                                      noarch           2.0.5-5.fc43                                                             fedora                                    37.8 KiB
 python3-bleach                                                         noarch           6.2.0-8.fc43                                                             updates                                  190.0 KiB
 python3-blosc2                                                         x86_64           3.8.0-4.fc43                                                             updates                                    2.1 MiB
 python3-comm                                                           noarch           0.2.3-3.fc43                                                             fedora                                    35.8 KiB
 python3-cpuinfo                                                        noarch           9.0.0-16.fc43                                                            fedora                                   310.8 KiB
 python3-decorator                                                      noarch           5.2.1-5.fc43                                                             fedora                                    81.8 KiB
 python3-et_xmlfile                                                     noarch           2.0.0-6.fc43                                                             fedora                                   100.3 KiB
 python3-executing                                                      noarch           2.2.1-2.fc43                                                             fedora                                   294.3 KiB
 python3-fastjsonschema                                                 noarch           2.21.2-2.fc43                                                            fedora                                   194.3 KiB
 python3-fqdn                                                           noarch           1.5.1-18.fc43                                                            fedora                                    21.0 KiB
 python3-frozenlist                                                     x86_64           1.8.0-1.fc43                                                             updates                                  150.6 KiB
 python3-google-api-core                                                noarch           1:2.27.0-1.fc43                                                          updates                                    1.1 MiB
 python3-google-api-core+grpc                                           noarch           1:2.27.0-1.fc43                                                          updates                                   13.8 KiB
 python3-google-auth                                                    noarch           1:2.45.0-1.fc43                                                          updates                                    1.5 MiB
 python3-google-auth-oauthlib                                           noarch           1.2.3-2.fc43                                                             updates                                   98.4 KiB
 python3-google-cloud-core                                              noarch           2.3.3-12.fc43                                                            updates                                  180.9 KiB
 python3-google-cloud-storage                                           noarch           2.14.0-11.fc43                                                           fedora                                     1.2 MiB
 python3-google-crc32c                                                  x86_64           1.8.0-1.fc43                                                             updates                                   63.8 KiB
 python3-google-resumable-media                                         noarch           2.8.0-1.fc43                                                             updates                                  653.0 KiB
 python3-googleapis-common-protos                                       noarch           1.63.0-13.fc43                                                           fedora                                   778.4 KiB
 python3-greenlet                                                       x86_64           3.1.1-8.fc43                                                             fedora                                   950.9 KiB
 python3-grpcio                                                         x86_64           1.48.4-54.fc43                                                           fedora                                     7.7 MiB
 python3-grpcio-status                                                  noarch           1.48.4-54.fc43                                                           fedora                                    14.4 KiB
 python3-ipykernel                                                      noarch           6.29.3-16.fc43                                                           fedora                                   974.4 KiB
 python3-ipython                                                        noarch           8.37.0-11.fc43                                                           fedora                                     4.7 MiB
 python3-isoduration                                                    noarch           20.11.0-15.fc43                                                          fedora                                    58.0 KiB
 python3-jedi                                                           noarch           0.19.2-8.fc43                                                            fedora                                     5.7 MiB
 python3-json-logger                                                    noarch           3.3.0-5.fc43                                                             fedora                                    81.5 KiB
 python3-json5                                                          noarch           0.12.1-2.fc43                                                            updates                                  364.3 KiB
 python3-jsonpointer                                                    noarch           2.4-8.fc43                                                               fedora                                    45.8 KiB
 python3-jsonschema+format-nongpl                                       noarch           4.23.0-6.fc43                                                            fedora                                     8.9 KiB
 python3-jupyter-client                                                 noarch           8.6.1-19.fc43                                                            fedora                                   982.0 KiB
 python3-jupyter-core                                                   noarch           5.8.1-5.fc43                                                             fedora                                   213.8 KiB
 python3-jupyter-events                                                 noarch           0.12.0-6.fc43                                                            fedora                                    98.7 KiB
 python3-jupyter-lsp                                                    noarch           2.3.0-2.fc43                                                             fedora                                   454.3 KiB
 python3-jupyter-server                                                 noarch           2.17.0-2.fc43                                                            fedora                                     3.0 MiB
 python3-jupyter-server-terminals                                       noarch           0.5.3-9.fc43                                                             fedora                                    71.3 KiB
 python3-jupyterlab-server                                              noarch           2.27.3-8.fc43                                                            fedora                                   420.5 KiB
 python3-jupyterlab_pygments                                            noarch           0.3.0-12.fc43                                                            fedora                                    62.0 KiB
 python3-matplotlib-inline                                              noarch           0.1.7-9.fc43                                                             fedora                                    39.8 KiB
 python3-mistune                                                        noarch           3.1.3-5.fc43                                                             fedora                                   508.6 KiB
 python3-multidict                                                      x86_64           6.6.4-2.fc43                                                             updates                                  323.3 KiB
 python3-nbclient                                                       noarch           0.10.2-9.fc43                                                            fedora                                   232.0 KiB
 python3-nbconvert                                                      noarch           7.16.4-12.fc43                                                           fedora                                     1.2 MiB
 python3-nbformat                                                       noarch           5.10.4-5.fc43                                                            fedora                                   555.5 KiB
 python3-ndindex                                                        x86_64           1.10.0-5.fc43                                                            fedora                                     1.1 MiB
 python3-nest-asyncio                                                   noarch           1.6.0-10.fc43                                                            fedora                                    25.9 KiB
 python3-notebook-shim                                                  noarch           0.2.4-8.fc43                                                             fedora                                    67.6 KiB
 python3-oauthlib                                                       noarch           3.2.2-10.fc43                                                            fedora                                   996.3 KiB
 python3-pandocfilters                                                  noarch           1.5.1-11.fc43                                                            fedora                                    39.0 KiB
 python3-parso                                                          noarch           0.8.5-2.fc43                                                             updates                                  930.1 KiB
 python3-prometheus_client                                              noarch           0.23.0-2.fc43                                                            updates                                  425.1 KiB
 python3-prompt-toolkit                                                 noarch           3.0.41-10.fc43                                                           fedora                                     4.1 MiB
 python3-propcache                                                      x86_64           0.4.1-1.fc43                                                             updates                                  152.9 KiB
 python3-proto-plus                                                     noarch           1.22.3-11.fc43                                                           fedora                                   270.7 KiB
 python3-protobuf                                                       noarch           3.19.6-18.fc43                                                           fedora                                     1.5 MiB
 python3-pure-eval                                                      noarch           0.2.3-6.fc43                                                             fedora                                   106.0 KiB
 python3-pyasn1                                                         noarch           0.6.2-1.fc43                                                             updates                                  884.5 KiB
 python3-pyasn1-modules                                                 noarch           0.6.2-1.fc43                                                             updates                                    1.7 MiB
 python3-pycares                                                        x86_64           4.10.0-3.fc43                                                            fedora                                   279.6 KiB
 python3-pytz                                                           noarch           2026.1-1.fc43                                                            updates                                  224.0 KiB
 python3-pyzmq                                                          x86_64           27.1.0-5.fc43                                                            updates                                    1.3 MiB
 python3-requests-oauthlib                                              noarch           1.3.1-15.fc43                                                            fedora                                   134.1 KiB
 python3-rfc3339-validator                                              noarch           0.1.4-20.fc43                                                            fedora                                     9.9 KiB
 python3-rfc3986-validator                                              noarch           0.1.1-22.fc43                                                            fedora                                    12.6 KiB
 python3-rsa                                                            noarch           4.9-12.fc43                                                              fedora                                   257.9 KiB
 python3-send2trash                                                     noarch           1.8.3-6.fc43                                                             fedora                                    69.4 KiB
 python3-stack-data                                                     noarch           0.6.3-18.fc43                                                            fedora                                   223.3 KiB
 python3-terminado                                                      noarch           0.18.1-7.fc43                                                            fedora                                   133.0 KiB
 python3-tornado                                                        x86_64           6.5.2-3.fc43                                                             fedora                                     5.4 MiB
 python3-traitlets                                                      noarch           5.14.3-8.fc43                                                            fedora                                     1.0 MiB
 python3-uri-template                                                   noarch           1.3.0-5.fc43                                                             fedora                                    88.6 KiB
 python3-wcwidth                                                        noarch           0.6.0-1.fc43                                                             updates                                  470.6 KiB
 python3-webcolors                                                      noarch           24.11.1-6.fc43                                                           fedora                                    87.8 KiB
 python3-websocket-client                                               noarch           1.8.0-7.fc43                                                             fedora                                   468.7 KiB
 python3-yarl                                                           x86_64           1.22.0-1.fc43                                                            updates                                  550.9 KiB
Installing weak dependencies:
 pandoc-cli                                                             x86_64           3.6.4-38.fc43                                                            updates                                  203.5 MiB
 python3-PyMySQL                                                        noarch           1.1.2-2.fc43                                                             fedora                                   403.5 KiB
 python3-QtPy                                                           noarch           2.4.3-6.fc43                                                             fedora                                   638.9 KiB
 python3-aiohttp+speedups                                               x86_64           3.13.3-4.fc43                                                            updates                                    0.0   B
 python3-fsspec                                                         noarch           2026.1.0-1.fc43                                                          updates                                    1.9 MiB
 python3-gcsfs                                                          noarch           2025.9.0-2.fc43                                                          fedora                                   357.9 KiB
 python3-openpyxl                                                       noarch           3.1.5-4.fc43                                                             fedora                                     1.9 MiB
 python3-pandas                                                         x86_64           2.3.3-2.fc43                                                             updates                                   41.7 MiB
 python3-psycopg2                                                       x86_64           2.9.10-4.fc43                                                            fedora                                   628.4 KiB
 python3-pyarrow                                                        x86_64           20.0.0-10.fc43                                                           updates                                   26.3 MiB
 python3-qt5-base                                                       x86_64           5.15.12-0.1.fc43                                                         updates                                   15.6 MiB
 python3-sqlalchemy                                                     x86_64           2.0.48-1.fc43                                                            updates                                   24.4 MiB
 python3-tables                                                         x86_64           3.10.2-7.fc43                                                            fedora                                    10.2 MiB
 python3-tabulate                                                       noarch           0.9.0-18.fc43                                                            updates                                  346.7 KiB
 python3-tabulate+widechars                                             noarch           0.9.0-18.fc43                                                            updates                                    0.0   B
 python3-xarray                                                         noarch           2025.12.0-1.fc43                                                         updates                                   21.5 MiB
 python3-xlrd                                                           noarch           2.0.1-26.fc43                                                            fedora                                     1.0 MiB
 python3-xlsxwriter                                                     noarch           3.2.9-1.fc43                                                             fedora                                     1.7 MiB
 xclip                                                                  x86_64           0.13-25.git11cba61.fc43                                                  fedora                                    58.2 KiB
 xsel                                                                   x86_64           1.2.1-9.fc43                                                             fedora                                    47.7 KiB

Transaction Summary:
 Installing:       117 packages

Total size of inbound packages is 86 MiB. Need to download 86 MiB.
After this operation, 475 MiB extra will be used (install 475 MiB, remove 0 B).
[  1/117] python-jupyter-filesystem-0:5.8.1-5.fc43.noarch                                                                                                                   100% |  48.7 KiB/s |   9.6 KiB |  00m00s
[  2/117] python3-async-lru-0:2.0.5-5.fc43.noarch                                                                                                                           100% |  86.9 KiB/s |  22.3 KiB |  00m00s
[  3/117] python3-jupyter-core-0:5.8.1-5.fc43.noarch                                                                                                                        100% | 524.4 KiB/s |  82.3 KiB |  00m00s
[  4/117] python3-ipykernel-0:6.29.3-16.fc43.noarch                                                                                                                         100% |   1.1 MiB/s | 261.6 KiB |  00m00s
[  5/117] python3-jupyter-lsp-0:2.3.0-2.fc43.noarch                                                                                                                         100% |   1.4 MiB/s | 165.4 KiB |  00m00s
[  6/117] python3-jupyter-server-0:2.17.0-2.fc43.noarch                                                                                                                     100% |   3.5 MiB/s | 624.4 KiB |  00m00s
[  7/117] python3-jupyterlab-server-0:2.27.3-8.fc43.noarch                                                                                                                  100% |   1.7 MiB/s | 139.4 KiB |  00m00s
[  8/117] python3-notebook-shim-0:0.2.4-8.fc43.noarch                                                                                                                       100% | 686.3 KiB/s |  40.5 KiB |  00m00s
[  9/117] python3-traitlets-0:5.14.3-8.fc43.noarch                                                                                                                          100% |   3.0 MiB/s | 225.0 KiB |  00m00s
[ 10/117] python3-comm-0:0.2.3-3.fc43.noarch                                                                                                                                100% | 429.9 KiB/s |  21.9 KiB |  00m00s
[ 11/117] python3-tornado-0:6.5.2-3.fc43.x86_64                                                                                                                             100% |   5.1 MiB/s | 966.3 KiB |  00m00s
[ 12/117] python3-jupyter-client-0:8.6.1-19.fc43.noarch                                                                                                                     100% |   2.6 MiB/s | 254.2 KiB |  00m00s
[ 13/117] python3-matplotlib-inline-0:0.1.7-9.fc43.noarch                                                                                                                   100% | 411.0 KiB/s |  24.2 KiB |  00m00s
[ 14/117] python3-ipython-0:8.37.0-11.fc43.noarch                                                                                                                           100% |   5.8 MiB/s |   1.2 MiB |  00m00s
[ 15/117] python3-nest-asyncio-0:1.6.0-10.fc43.noarch                                                                                                                       100% | 285.9 KiB/s |  19.4 KiB |  00m00s
[ 16/117] python3-argon2-cffi-0:23.1.0-8.fc43.noarch                                                                                                                        100% | 821.4 KiB/s |  41.1 KiB |  00m00s
[ 17/117] python3-jupyter-events-0:0.12.0-6.fc43.noarch                                                                                                                     100% |   1.1 MiB/s |  52.9 KiB |  00m00s
[ 18/117] python3-jupyter-server-terminals-0:0.5.3-9.fc43.noarch                                                                                                            100% | 769.5 KiB/s |  37.7 KiB |  00m00s
[ 19/117] python3-nbconvert-0:7.16.4-12.fc43.noarch                                                                                                                         100% |   4.3 MiB/s | 360.6 KiB |  00m00s
[ 20/117] python3-nbformat-0:5.10.4-5.fc43.noarch                                                                                                                           100% |   1.9 MiB/s | 147.4 KiB |  00m00s
[ 21/117] python3-send2trash-0:1.8.3-6.fc43.noarch                                                                                                                          100% | 785.4 KiB/s |  49.5 KiB |  00m00s
[ 22/117] python3-terminado-0:0.18.1-7.fc43.noarch                                                                                                                          100% | 894.8 KiB/s |  44.7 KiB |  00m00s
[ 23/117] python3-decorator-0:5.2.1-5.fc43.noarch                                                                                                                           100% | 542.6 KiB/s |  32.0 KiB |  00m00s
[ 24/117] python3-websocket-client-0:1.8.0-7.fc43.noarch                                                                                                                    100% |   2.1 MiB/s | 145.0 KiB |  00m00s
[ 25/117] python3-prompt-toolkit-0:3.0.41-10.fc43.noarch                                                                                                                    100% |   3.5 MiB/s | 893.4 KiB |  00m00s
[ 26/117] python3-stack-data-0:0.6.3-18.fc43.noarch                                                                                                                         100% | 830.8 KiB/s |  65.6 KiB |  00m00s
[ 27/117] python3-jedi-0:0.19.2-8.fc43.noarch                                                                                                                               100% |   4.6 MiB/s |   1.6 MiB |  00m00s
[ 28/117] python3-argon2-cffi-bindings-0:21.2.0-13.fc43.x86_64                                                                                                              100% | 561.3 KiB/s |  27.5 KiB |  00m00s
[ 29/117] python3-json-logger-0:3.3.0-5.fc43.noarch                                                                                                                         100% | 466.1 KiB/s |  41.0 KiB |  00m00s
[ 30/117] python3-jsonschema+format-nongpl-0:4.23.0-6.fc43.noarch                                                                                                           100% | 182.1 KiB/s |   9.5 KiB |  00m00s
[ 31/117] python3-rfc3339-validator-0:0.1.4-20.fc43.noarch                                                                                                                  100% | 284.5 KiB/s |  15.1 KiB |  00m00s
[ 32/117] python3-rfc3986-validator-0:0.1.1-22.fc43.noarch                                                                                                                  100% | 294.2 KiB/s |  14.7 KiB |  00m00s
[ 33/117] python3-jupyterlab_pygments-0:0.3.0-12.fc43.noarch                                                                                                                100% | 598.9 KiB/s |  30.5 KiB |  00m00s
[ 34/117] python3-mistune-0:3.1.3-5.fc43.noarch                                                                                                                             100% |   2.5 MiB/s | 153.9 KiB |  00m00s
[ 35/117] python3-nbclient-0:0.10.2-9.fc43.noarch                                                                                                                           100% | 988.4 KiB/s |  70.2 KiB |  00m00s
[ 36/117] python3-pandocfilters-0:1.5.1-11.fc43.noarch                                                                                                                      100% | 339.7 KiB/s |  21.4 KiB |  00m00s
[ 37/117] python3-asttokens-0:3.0.0-5.fc43.noarch                                                                                                                           100% |   1.0 MiB/s |  60.4 KiB |  00m00s
[ 38/117] python3-fastjsonschema-0:2.21.2-2.fc43.noarch                                                                                                                     100% |   1.1 MiB/s |  66.6 KiB |  00m00s
[ 39/117] python3-executing-0:2.2.1-2.fc43.noarch                                                                                                                           100% |   1.3 MiB/s |  77.8 KiB |  00m00s
[ 40/117] python3-pure-eval-0:0.2.3-6.fc43.noarch                                                                                                                           100% | 661.8 KiB/s |  39.7 KiB |  00m00s
[ 41/117] python3-fqdn-0:1.5.1-18.fc43.noarch                                                                                                                               100% | 343.6 KiB/s |  17.9 KiB |  00m00s
[ 42/117] python3-isoduration-0:20.11.0-15.fc43.noarch                                                                                                                      100% | 784.0 KiB/s |  40.8 KiB |  00m00s
[ 43/117] python3-jsonpointer-0:2.4-8.fc43.noarch                                                                                                                           100% | 423.3 KiB/s |  21.6 KiB |  00m00s
[ 44/117] python3-uri-template-0:1.3.0-5.fc43.noarch                                                                                                                        100% | 724.1 KiB/s |  37.7 KiB |  00m00s
[ 45/117] python3-webcolors-0:24.11.1-6.fc43.noarch                                                                                                                         100% | 731.3 KiB/s |  38.8 KiB |  00m00s
[ 46/117] python3-arrow-0:1.3.0-5.fc43.noarch                                                                                                                               100% |   2.6 MiB/s | 163.2 KiB |  00m00s
[ 47/117] python3-wcwidth-0:0.6.0-1.fc43.noarch                                                                                                                             100% | 232.1 KiB/s | 123.3 KiB |  00m01s
[ 48/117] python3-bleach-0:6.2.0-8.fc43.noarch                                                                                                                              100% |  94.8 KiB/s |  67.3 KiB |  00m01s
[ 49/117] python3-json5-0:0.12.1-2.fc43.noarch                                                                                                                              100% | 184.4 KiB/s |  73.4 KiB |  00m00s
[ 50/117] python3-prometheus_client-0:0.23.0-2.fc43.noarch                                                                                                                  100% | 392.2 KiB/s | 151.4 KiB |  00m00s
[ 51/117] python3-parso-0:0.8.5-2.fc43.noarch                                                                                                                               100% | 564.1 KiB/s | 217.8 KiB |  00m00s
[ 52/117] python3-pyzmq-0:27.1.0-5.fc43.x86_64                                                                                                                              100% | 684.6 KiB/s | 416.9 KiB |  00m01s
[ 53/117] python3-pandas-0:2.3.3-2.fc43.x86_64                                                                                                                              100% |   1.8 MiB/s |   7.7 MiB |  00m04s
[ 54/117] pandoc-common-0:3.6.4-36.fc43.noarch                                                                                                                              100% |   1.1 MiB/s | 589.2 KiB |  00m01s
[ 55/117] python3-Bottleneck-0:1.6.0-1.fc43.x86_64                                                                                                                          100% | 816.7 KiB/s | 181.3 KiB |  00m00s
[ 56/117] python3-pytz-0:2026.1-1.fc43.noarch                                                                                                                               100% | 338.0 KiB/s |  65.9 KiB |  00m00s
[ 57/117] xsel-0:1.2.1-9.fc43.x86_64                                                                                                                                        100% | 570.3 KiB/s |  29.7 KiB |  00m00s
[ 58/117] python3-qt5-base-0:5.15.12-0.1.fc43.x86_64                                                                                                                        100% |   4.1 MiB/s |   3.0 MiB |  00m01s
[ 59/117] python-qt5-rpm-macros-0:5.15.12-0.1.fc43.noarch                                                                                                                   100% |  54.6 KiB/s |   9.3 KiB |  00m00s
[ 60/117] xclip-0:0.13-25.git11cba61.fc43.x86_64                                                                                                                            100% | 698.5 KiB/s |  36.3 KiB |  00m00s
[ 61/117] python3-QtPy-0:2.4.3-6.fc43.noarch                                                                                                                                100% |   2.8 MiB/s | 255.3 KiB |  00m00s
[ 62/117] jupyterlab-0:4.4.10-2.fc43.noarch                                                                                                                                 100% | 791.4 KiB/s |   8.2 MiB |  00m11s
[ 63/117] python3-sqlalchemy-0:2.0.48-1.fc43.x86_64                                                                                                                         100% |   3.4 MiB/s |   3.9 MiB |  00m01s
[ 64/117] python3-gcsfs-0:2025.9.0-2.fc43.noarch                                                                                                                            100% |   1.1 MiB/s | 104.8 KiB |  00m00s
[ 65/117] python3-google-cloud-storage-0:2.14.0-11.fc43.noarch                                                                                                              100% |   2.5 MiB/s | 210.0 KiB |  00m00s
[ 66/117] python3-fsspec-0:2026.1.0-1.fc43.noarch                                                                                                                           100% | 573.8 KiB/s | 471.1 KiB |  00m01s
[ 67/117] python3-openpyxl-0:3.1.5-4.fc43.noarch                                                                                                                            100% |   3.3 MiB/s | 618.3 KiB |  00m00s
[ 68/117] python3-psycopg2-0:2.9.10-4.fc43.x86_64                                                                                                                           100% |   3.0 MiB/s | 209.8 KiB |  00m00s
[ 69/117] python3-et_xmlfile-0:2.0.0-6.fc43.noarch                                                                                                                          100% | 127.0 KiB/s |  45.3 KiB |  00m00s
[ 70/117] libarrow-flight-libs-0:20.0.0-10.fc43.x86_64                                                                                                                      100% |   1.6 MiB/s | 421.4 KiB |  00m00s
[ 71/117] grpc-0:1.48.4-54.fc43.x86_64                                                                                                                                      100% |   5.7 MiB/s |   2.6 MiB |  00m00s
[ 72/117] grpc-cpp-0:1.48.4-54.fc43.x86_64                                                                                                                                  100% |   4.7 MiB/s | 720.9 KiB |  00m00s
[ 73/117] libarrow-glib-libs-0:20.0.0-10.fc43.x86_64                                                                                                                        100% |   1.2 MiB/s | 421.7 KiB |  00m00s
[ 74/117] grpc-data-0:1.48.4-54.fc43.noarch                                                                                                                                 100% | 385.6 KiB/s |  18.9 KiB |  00m00s
[ 75/117] protobuf-compiler-0:3.19.6-18.fc43.x86_64                                                                                                                         100% |   3.9 MiB/s | 783.5 KiB |  00m00s
[ 76/117] python3-PyMySQL-0:1.1.2-2.fc43.noarch                                                                                                                             100% |   1.8 MiB/s | 119.6 KiB |  00m00s
[ 77/117] python3-tables-0:3.10.2-7.fc43.x86_64                                                                                                                             100% |   5.9 MiB/s |   1.7 MiB |  00m00s
[ 78/117] blosc2-0:2.21.2-1.fc43.x86_64                                                                                                                                     100% |   3.0 MiB/s | 220.6 KiB |  00m00s
[ 79/117] python3-cpuinfo-0:9.0.0-16.fc43.noarch                                                                                                                            100% | 929.0 KiB/s |  68.7 KiB |  00m00s
[ 80/117] python3-tabulate-0:0.9.0-18.fc43.noarch                                                                                                                           100% | 254.1 KiB/s |  72.7 KiB |  00m00s
[ 81/117] pandoc-cli-0:3.6.4-38.fc43.x86_64                                                                                                                                 100% |   2.6 MiB/s |  28.4 MiB |  00m11s
[ 82/117] python3-xlrd-0:2.0.1-26.fc43.noarch                                                                                                                               100% |   2.2 MiB/s | 221.6 KiB |  00m00s
[ 83/117] python3-xlsxwriter-0:3.2.9-1.fc43.noarch                                                                                                                          100% |   2.9 MiB/s | 392.1 KiB |  00m00s
[ 84/117] python3-greenlet-0:3.1.1-8.fc43.x86_64                                                                                                                            100% |   2.1 MiB/s | 268.1 KiB |  00m00s
[ 85/117] python3-xarray-0:2025.12.0-1.fc43.noarch                                                                                                                          100% |   3.8 MiB/s |   3.3 MiB |  00m01s
[ 86/117] python3-ndindex-0:1.10.0-5.fc43.x86_64                                                                                                                            100% |   3.8 MiB/s | 290.5 KiB |  00m00s
[ 87/117] python3-google-api-core-1:2.27.0-1.fc43.noarch                                                                                                                    100% |   1.3 MiB/s | 264.8 KiB |  00m00s
[ 88/117] python3-googleapis-common-protos-0:1.63.0-13.fc43.noarch                                                                                                          100% |   3.3 MiB/s | 224.7 KiB |  00m00s
[ 89/117] python3-proto-plus-0:1.22.3-11.fc43.noarch                                                                                                                        100% |   1.6 MiB/s | 104.7 KiB |  00m00s
[ 90/117] python3-protobuf-0:3.19.6-18.fc43.noarch                                                                                                                          100% |   3.8 MiB/s | 311.4 KiB |  00m00s
[ 91/117] python3-google-api-core+grpc-1:2.27.0-1.fc43.noarch                                                                                                               100% |  69.2 KiB/s |  12.6 KiB |  00m00s
[ 92/117] python3-grpcio-0:1.48.4-54.fc43.x86_64                                                                                                                            100% |   7.2 MiB/s |   2.4 MiB |  00m00s
[ 93/117] python3-grpcio-status-0:1.48.4-54.fc43.noarch                                                                                                                     100% | 367.3 KiB/s |  17.6 KiB |  00m00s
[ 94/117] python3-blosc2-0:3.8.0-4.fc43.x86_64                                                                                                                              100% | 430.5 KiB/s | 588.1 KiB |  00m01s
[ 95/117] python3-rsa-0:4.9-12.fc43.noarch                                                                                                                                  100% |   1.0 MiB/s |  83.4 KiB |  00m00s
[ 96/117] python3-google-auth-1:2.45.0-1.fc43.noarch                                                                                                                        100% |   1.3 MiB/s | 364.4 KiB |  00m00s
[ 97/117] python3-google-cloud-core-0:2.3.3-12.fc43.noarch                                                                                                                  100% | 186.4 KiB/s |  73.6 KiB |  00m00s
[ 98/117] python3-google-crc32c-0:1.8.0-1.fc43.x86_64                                                                                                                       100% | 101.8 KiB/s |  39.1 KiB |  00m00s
[ 99/117] google-crc32c-0:1.1.2-12.fc43.x86_64                                                                                                                              100% | 443.8 KiB/s |  22.2 KiB |  00m00s
[100/117] python3-google-resumable-media-0:2.8.0-1.fc43.noarch                                                                                                              100% | 498.4 KiB/s | 104.2 KiB |  00m00s
[101/117] python3-aiohappyeyeballs-0:2.6.1-9.fc43.noarch                                                                                                                    100% | 783.4 KiB/s |  43.1 KiB |  00m00s
[102/117] python3-aiosignal-0:1.4.0-4.fc43.noarch                                                                                                                           100% | 391.7 KiB/s |  20.0 KiB |  00m00s
[103/117] python3-google-auth-oauthlib-0:1.2.3-2.fc43.noarch                                                                                                                100% | 205.5 KiB/s |  40.5 KiB |  00m00s
[104/117] python3-requests-oauthlib-0:1.3.1-15.fc43.noarch                                                                                                                  100% |   1.1 MiB/s |  58.5 KiB |  00m00s
[105/117] python3-oauthlib-0:3.2.2-10.fc43.noarch                                                                                                                           100% |   3.5 MiB/s | 254.8 KiB |  00m00s
[106/117] python3-frozenlist-0:1.8.0-1.fc43.x86_64                                                                                                                          100% | 394.3 KiB/s |  58.7 KiB |  00m00s
[107/117] python3-pyasn1-modules-0:0.6.2-1.fc43.noarch                                                                                                                      100% |   1.4 MiB/s | 378.1 KiB |  00m00s
[108/117] python3-aiohttp-0:3.13.3-4.fc43.x86_64                                                                                                                            100% | 827.9 KiB/s | 854.4 KiB |  00m01s
[109/117] python3-multidict-0:6.6.4-2.fc43.x86_64                                                                                                                           100% | 507.8 KiB/s |  86.8 KiB |  00m00s
[110/117] python3-pyarrow-0:20.0.0-10.fc43.x86_64                                                                                                                           100% | 766.6 KiB/s |   4.8 MiB |  00m06s
[111/117] python3-propcache-0:0.4.1-1.fc43.x86_64                                                                                                                           100% | 273.7 KiB/s |  61.0 KiB |  00m00s
[112/117] python3-tabulate+widechars-0:0.9.0-18.fc43.noarch                                                                                                                 100% |  59.0 KiB/s |   8.7 KiB |  00m00s
[113/117] python3-pyasn1-0:0.6.2-1.fc43.noarch                                                                                                                              100% | 968.6 KiB/s | 199.5 KiB |  00m00s
[114/117] python3-yarl-0:1.22.0-1.fc43.x86_64                                                                                                                               100% | 489.9 KiB/s | 144.0 KiB |  00m00s
[115/117] python3-pycares-0:4.10.0-3.fc43.x86_64                                                                                                                            100% |   1.4 MiB/s |  76.2 KiB |  00m00s
[116/117] python3-aiohttp+speedups-0:3.13.3-4.fc43.x86_64                                                                                                                   100% |  87.6 KiB/s |  11.9 KiB |  00m00s
[117/117] python3-aiodns-0:3.6.1-1.fc43.noarch                                                                                                                              100% | 196.7 KiB/s |  27.3 KiB |  00m00s
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[117/117] Total                                                                                                                                                             100% |   4.6 MiB/s |  86.4 MiB |  00m19s
Running transaction
[  1/119] Verify package files                                                                                                                                              100% | 446.0   B/s | 117.0   B |  00m00s
[  2/119] Prepare transaction                                                                                                                                               100% | 144.0   B/s | 117.0   B |  00m01s
[  3/119] Installing python3-traitlets-0:5.14.3-8.fc43.noarch                                                                                                               100% |  94.8 MiB/s |   1.0 MiB |  00m00s
[  4/119] Installing python3-jupyter-core-0:5.8.1-5.fc43.noarch                                                                                                             100% |  14.5 MiB/s | 222.3 KiB |  00m00s
[  5/119] Installing python3-tornado-0:6.5.2-3.fc43.x86_64                                                                                                                  100% | 217.8 MiB/s |   5.4 MiB |  00m00s
[  6/119] Installing python-jupyter-filesystem-0:5.8.1-5.fc43.noarch                                                                                                        100% |   1.0 MiB/s |   2.1 KiB |  00m00s
[  7/119] Installing python3-protobuf-0:3.19.6-18.fc43.noarch                                                                                                               100% | 120.3 MiB/s |   1.6 MiB |  00m00s
[  8/119] Installing python3-pyzmq-0:27.1.0-5.fc43.x86_64                                                                                                                   100% |  74.3 MiB/s |   1.3 MiB |  00m00s
[  9/119] Installing python3-jupyter-client-0:8.6.1-19.fc43.noarch                                                                                                          100% |  49.2 MiB/s |   1.0 MiB |  00m00s
[ 10/119] Installing python3-decorator-0:5.2.1-5.fc43.noarch                                                                                                                100% |  41.2 MiB/s |  84.5 KiB |  00m00s
[ 11/119] Installing python3-googleapis-common-protos-0:1.63.0-13.fc43.noarch                                                                                               100% |  45.2 MiB/s | 833.1 KiB |  00m00s
[ 12/119] Installing python3-terminado-0:0.18.1-7.fc43.noarch                                                                                                               100% |  27.0 MiB/s | 138.4 KiB |  00m00s
[ 13/119] Installing python3-matplotlib-inline-0:0.1.7-9.fc43.noarch                                                                                                        100% |  10.8 MiB/s |  44.1 KiB |  00m00s
[ 14/119] Installing python3-pyasn1-0:0.6.2-1.fc43.noarch                                                                                                                   100% | 110.7 MiB/s | 907.2 KiB |  00m00s
[ 15/119] Installing python3-propcache-0:0.4.1-1.fc43.x86_64                                                                                                                100% |  51.4 MiB/s | 158.0 KiB |  00m00s
[ 16/119] Installing python3-multidict-0:6.6.4-2.fc43.x86_64                                                                                                                100% |  45.8 MiB/s | 328.3 KiB |  00m00s
[ 17/119] Installing python3-frozenlist-0:1.8.0-1.fc43.x86_64                                                                                                               100% |  50.3 MiB/s | 154.7 KiB |  00m00s
[ 18/119] Installing python3-cpuinfo-0:9.0.0-16.fc43.noarch                                                                                                                 100% |  23.7 MiB/s | 314.8 KiB |  00m00s
[ 19/119] Installing blosc2-0:2.21.2-1.fc43.x86_64                                                                                                                          100% | 139.3 MiB/s | 570.5 KiB |  00m00s
[ 20/119] Installing grpc-data-0:1.48.4-54.fc43.noarch                                                                                                                      100% |  29.7 MiB/s |  30.4 KiB |  00m00s
[ 21/119] Installing grpc-0:1.48.4-54.fc43.x86_64                                                                                                                           100% | 421.2 MiB/s |  10.5 MiB |  00m00s
[ 22/119] Installing python3-grpcio-0:1.48.4-54.fc43.x86_64                                                                                                                 100% | 277.0 MiB/s |   7.8 MiB |  00m00s
[ 23/119] Installing python3-wcwidth-0:0.6.0-1.fc43.noarch                                                                                                                  100% | 117.4 MiB/s | 480.8 KiB |  00m00s
[ 24/119] Installing python3-rfc3986-validator-0:0.1.1-22.fc43.noarch                                                                                                       100% |   7.5 MiB/s |  15.3 KiB |  00m00s
[ 25/119] Installing python3-rfc3339-validator-0:0.1.4-20.fc43.noarch                                                                                                       100% |   4.1 MiB/s |  12.7 KiB |  00m00s
[ 26/119] Installing python3-prompt-toolkit-0:3.0.41-10.fc43.noarch                                                                                                         100% | 123.3 MiB/s |   4.2 MiB |  00m00s
[ 27/119] Installing python3-grpcio-status-0:1.48.4-54.fc43.noarch                                                                                                          100% |   8.9 MiB/s |  18.3 KiB |  00m00s
[ 28/119] Installing python3-aiosignal-0:1.4.0-4.fc43.noarch                                                                                                                100% |  13.6 MiB/s |  27.9 KiB |  00m00s
[ 29/119] Installing python3-yarl-0:1.22.0-1.fc43.x86_64                                                                                                                    100% | 136.2 MiB/s | 558.0 KiB |  00m00s
[ 30/119] Installing python3-rsa-0:4.9-12.fc43.noarch                                                                                                                       100% |  17.5 MiB/s | 269.3 KiB |  00m00s
[ 31/119] Installing python3-pyasn1-modules-0:0.6.2-1.fc43.noarch                                                                                                           100% |  74.3 MiB/s |   1.8 MiB |  00m00s
[ 32/119] Installing python3-google-auth-1:2.45.0-1.fc43.noarch                                                                                                             100% | 106.2 MiB/s |   1.6 MiB |  00m00s
[ 33/119] Installing python3-jupyter-server-terminals-0:0.5.3-9.fc43.noarch                                                                                                 100% |  25.4 MiB/s |  77.9 KiB |  00m00s
[ 34/119] Installing python3-prometheus_client-0:0.23.0-2.fc43.noarch                                                                                                       100% |  61.9 MiB/s | 443.4 KiB |  00m00s
[ 35/119] Installing python3-proto-plus-0:1.22.3-11.fc43.noarch                                                                                                             100% |  46.9 MiB/s | 288.5 KiB |  00m00s
[ 36/119] Installing python3-google-api-core+grpc-1:2.27.0-1.fc43.noarch                                                                                                    100% | 121.1 KiB/s | 124.0   B |  00m00s
[ 37/119] Installing python3-google-api-core-1:2.27.0-1.fc43.noarch                                                                                                         100% |  85.5 MiB/s |   1.1 MiB |  00m00s
[ 38/119] Installing python3-google-cloud-core-0:2.3.3-12.fc43.noarch                                                                                                       100% |  37.8 MiB/s | 193.5 KiB |  00m00s
[ 39/119] Installing python3-pycares-0:4.10.0-3.fc43.x86_64                                                                                                                 100% |  69.6 MiB/s | 285.2 KiB |  00m00s
[ 40/119] Installing python3-aiodns-0:3.6.1-1.fc43.noarch                                                                                                                   100% |  25.6 MiB/s |  78.7 KiB |  00m00s
[ 41/119] Installing python3-oauthlib-0:3.2.2-10.fc43.noarch                                                                                                                100% |  68.1 MiB/s |   1.0 MiB |  00m00s
[ 42/119] Installing python3-requests-oauthlib-0:1.3.1-15.fc43.noarch                                                                                                       100% |  35.8 MiB/s | 146.5 KiB |  00m00s
[ 43/119] Installing python3-google-auth-oauthlib-0:1.2.3-2.fc43.noarch                                                                                                     100% |   7.9 MiB/s | 105.0 KiB |  00m00s
[ 44/119] Installing python3-aiohappyeyeballs-0:2.6.1-9.fc43.noarch                                                                                                         100% |  21.0 MiB/s | 107.7 KiB |  00m00s
[ 45/119] Installing python3-aiohttp-0:3.13.3-4.fc43.x86_64                                                                                                                 100% | 217.3 MiB/s |   4.1 MiB |  00m00s
[ 46/119] Installing google-crc32c-0:1.1.2-12.fc43.x86_64                                                                                                                   100% |  14.4 MiB/s |  29.4 KiB |  00m00s
[ 47/119] Installing python3-google-crc32c-0:1.8.0-1.fc43.x86_64                                                                                                            100% |  13.7 MiB/s |  70.0 KiB |  00m00s
[ 48/119] Installing python3-google-resumable-media-0:2.8.0-1.fc43.noarch                                                                                                   100% | 108.6 MiB/s | 667.1 KiB |  00m00s
[ 49/119] Installing python3-google-cloud-storage-0:2.14.0-11.fc43.noarch                                                                                                   100% | 200.0 MiB/s |   1.2 MiB |  00m00s
[ 50/119] Installing python3-ndindex-0:1.10.0-5.fc43.x86_64                                                                                                                 100% | 110.0 MiB/s |   1.1 MiB |  00m00s
[ 51/119] Installing python3-blosc2-0:3.8.0-4.fc43.x86_64                                                                                                                   100% | 261.7 MiB/s |   2.1 MiB |  00m00s
[ 52/119] Installing python3-greenlet-0:3.1.1-8.fc43.x86_64                                                                                                                 100% |  79.9 MiB/s | 981.3 KiB |  00m00s
[ 53/119] Installing python3-tabulate-0:0.9.0-18.fc43.noarch                                                                                                                100% |  26.3 MiB/s | 350.3 KiB |  00m00s
[ 54/119] Installing protobuf-compiler-0:3.19.6-18.fc43.x86_64                                                                                                              100% | 146.5 MiB/s |   2.5 MiB |  00m00s
[ 55/119] Installing grpc-cpp-0:1.48.4-54.fc43.x86_64                                                                                                                       100% | 300.6 MiB/s |   3.0 MiB |  00m00s
[ 56/119] Installing libarrow-glib-libs-0:20.0.0-10.fc43.x86_64                                                                                                             100% | 302.6 MiB/s |   1.5 MiB |  00m00s
[ 57/119] Installing libarrow-flight-libs-0:20.0.0-10.fc43.x86_64                                                                                                           100% | 281.1 MiB/s |   1.4 MiB |  00m00s
[ 58/119] Installing python3-et_xmlfile-0:2.0.0-6.fc43.noarch                                                                                                               100% |  34.3 MiB/s | 105.5 KiB |  00m00s
[ 59/119] Installing python3-fsspec-0:2026.1.0-1.fc43.noarch                                                                                                                100% | 139.7 MiB/s |   2.0 MiB |  00m00s
[ 60/119] Installing python-qt5-rpm-macros-0:5.15.12-0.1.fc43.noarch                                                                                                        100% | 205.1 KiB/s | 420.0   B |  00m00s
[ 61/119] Installing python3-pytz-0:2026.1-1.fc43.noarch                                                                                                                    100% |  74.7 MiB/s | 229.4 KiB |  00m00s
[ 62/119] Installing python3-Bottleneck-0:1.6.0-1.fc43.x86_64                                                                                                               100% |  48.9 MiB/s | 600.5 KiB |  00m00s
[ 63/119] Installing python3-pandas-0:2.3.3-2.fc43.x86_64                                                                                                                   100% | 279.5 MiB/s |  41.9 MiB |  00m00s
[ 64/119] Installing pandoc-common-0:3.6.4-36.fc43.noarch                                                                                                                   100% |  81.7 MiB/s |   2.0 MiB |  00m00s
[ 65/119] Installing python3-parso-0:0.8.5-2.fc43.noarch                                                                                                                    100% |  84.0 MiB/s | 946.1 KiB |  00m00s
[ 66/119] Installing python3-jedi-0:0.19.2-8.fc43.noarch                                                                                                                    100% |  33.9 MiB/s |   6.1 MiB |  00m00s
[ 67/119] Installing python3-json5-0:0.12.1-2.fc43.noarch                                                                                                                   100% |  90.4 MiB/s | 370.3 KiB |  00m00s
[ 68/119] Installing python3-bleach-0:6.2.0-8.fc43.noarch                                                                                                                   100% |  64.0 MiB/s | 196.7 KiB |  00m00s
[ 69/119] Installing python3-arrow-0:1.3.0-5.fc43.noarch                                                                                                                    100% | 121.0 MiB/s | 619.8 KiB |  00m00s
[ 70/119] Installing python3-isoduration-0:20.11.0-15.fc43.noarch                                                                                                           100% |  16.8 MiB/s |  68.8 KiB |  00m00s
[ 71/119] Installing python3-webcolors-0:24.11.1-6.fc43.noarch                                                                                                              100% |  30.3 MiB/s |  93.1 KiB |  00m00s
[ 72/119] Installing python3-uri-template-0:1.3.0-5.fc43.noarch                                                                                                             100% |  30.5 MiB/s |  93.6 KiB |  00m00s
[ 73/119] Installing python3-jsonpointer-0:2.4-8.fc43.noarch                                                                                                                100% |   4.0 MiB/s |  48.8 KiB |  00m00s
[ 74/119] Installing python3-fqdn-0:1.5.1-18.fc43.noarch                                                                                                                    100% |  11.8 MiB/s |  24.1 KiB |  00m00s
[ 75/119] Installing python3-jsonschema+format-nongpl-0:4.23.0-6.fc43.noarch                                                                                                100% | 121.1 KiB/s | 124.0   B |  00m00s
[ 76/119] Installing python3-pure-eval-0:0.2.3-6.fc43.noarch                                                                                                                100% |  36.1 MiB/s | 110.9 KiB |  00m00s
[ 77/119] Installing python3-executing-0:2.2.1-2.fc43.noarch                                                                                                                100% |  97.9 MiB/s | 300.7 KiB |  00m00s
[ 78/119] Installing python3-asttokens-0:3.0.0-5.fc43.noarch                                                                                                                100% |  66.8 MiB/s | 205.3 KiB |  00m00s
[ 79/119] Installing python3-stack-data-0:0.6.3-18.fc43.noarch                                                                                                              100% |  55.9 MiB/s | 228.8 KiB |  00m00s
[ 80/119] Installing python3-ipython-0:8.37.0-11.fc43.noarch                                                                                                                100% |  96.4 MiB/s |   4.8 MiB |  00m00s
[ 81/119] Installing python3-fastjsonschema-0:2.21.2-2.fc43.noarch                                                                                                          100% |  39.6 MiB/s | 202.5 KiB |  00m00s
[ 82/119] Installing python3-nbformat-0:5.10.4-5.fc43.noarch                                                                                                                100% |  28.5 MiB/s | 583.8 KiB |  00m00s
[ 83/119] Installing python3-nbclient-0:0.10.2-9.fc43.noarch                                                                                                                100% |  17.9 MiB/s | 238.6 KiB |  00m00s
[ 84/119] Installing python3-pandocfilters-0:1.5.1-11.fc43.noarch                                                                                                           100% |  20.1 MiB/s |  41.2 KiB |  00m00s
[ 85/119] Installing python3-mistune-0:3.1.3-5.fc43.noarch                                                                                                                  100% |  57.7 MiB/s | 531.3 KiB |  00m00s
[ 86/119] Installing python3-jupyterlab_pygments-0:0.3.0-12.fc43.noarch                                                                                                     100% |  16.9 MiB/s |  69.2 KiB |  00m00s
[ 87/119] Installing python3-nbconvert-0:7.16.4-12.fc43.noarch                                                                                                              100% |  25.8 MiB/s |   1.3 MiB |  00m00s
[ 88/119] Installing python3-json-logger-0:3.3.0-5.fc43.noarch                                                                                                              100% |  21.7 MiB/s |  88.8 KiB |  00m00s
[ 89/119] Installing python3-jupyter-events-0:0.12.0-6.fc43.noarch                                                                                                          100% |   7.5 MiB/s | 108.0 KiB |  00m00s
[ 90/119] Installing python3-argon2-cffi-bindings-0:21.2.0-13.fc43.x86_64                                                                                                   100% |  18.0 MiB/s |  55.4 KiB |  00m00s
[ 91/119] Installing python3-argon2-cffi-0:23.1.0-8.fc43.noarch                                                                                                             100% |  26.0 MiB/s |  79.9 KiB |  00m00s
[ 92/119] Installing python3-websocket-client-0:1.8.0-7.fc43.noarch                                                                                                         100% |  29.6 MiB/s | 484.7 KiB |  00m00s
[ 93/119] Installing python3-send2trash-0:1.8.3-6.fc43.noarch                                                                                                               100% |   5.2 MiB/s |  80.4 KiB |  00m00s
[ 94/119] Installing python3-jupyter-server-0:2.17.0-2.fc43.noarch                                                                                                          100% |  76.2 MiB/s |   3.0 MiB |  00m00s
[ 95/119] Installing python3-jupyter-lsp-0:2.3.0-2.fc43.noarch                                                                                                              100% |  39.9 MiB/s | 489.9 KiB |  00m00s
[ 96/119] Installing python3-jupyterlab-server-0:2.27.3-8.fc43.noarch                                                                                                       100% |  53.7 MiB/s | 440.2 KiB |  00m00s
[ 97/119] Installing python3-notebook-shim-0:0.2.4-8.fc43.noarch                                                                                                            100% |  15.0 MiB/s |  76.8 KiB |  00m00s
[ 98/119] Installing python3-nest-asyncio-0:1.6.0-10.fc43.noarch                                                                                                            100% |  13.7 MiB/s |  28.1 KiB |  00m00s
[ 99/119] Installing python3-comm-0:0.2.3-3.fc43.noarch                                                                                                                     100% |  18.9 MiB/s |  38.8 KiB |  00m00s
[100/119] Installing python3-ipykernel-0:6.29.3-16.fc43.noarch                                                                                                              100% |  81.7 MiB/s |   1.0 MiB |  00m00s
[101/119] Installing python3-async-lru-0:2.0.5-5.fc43.noarch                                                                                                                100% |   9.9 MiB/s |  40.4 KiB |  00m00s
[102/119] Installing jupyterlab-0:4.4.10-2.fc43.noarch                                                                                                                      100% | 237.0 MiB/s |  35.1 MiB |  00m00s
[103/119] Installing pandoc-cli-0:3.6.4-38.fc43.x86_64                                                                                                                      100% | 627.9 MiB/s | 203.5 MiB |  00m00s
[104/119] Installing python3-xarray-0:2025.12.0-1.fc43.noarch                                                                                                               100% | 304.1 MiB/s |  21.6 MiB |  00m00s
[105/119] Installing python3-qt5-base-0:5.15.12-0.1.fc43.x86_64                                                                                                             100% | 305.7 MiB/s |  15.6 MiB |  00m00s
[106/119] Installing python3-gcsfs-0:2025.9.0-2.fc43.noarch                                                                                                                 100% |  71.5 MiB/s | 366.1 KiB |  00m00s
[107/119] Installing python3-openpyxl-0:3.1.5-4.fc43.noarch                                                                                                                 100% |  55.7 MiB/s |   2.0 MiB |  00m00s
[108/119] Installing python3-pyarrow-0:20.0.0-10.fc43.x86_64                                                                                                                100% | 318.3 MiB/s |  26.4 MiB |  00m00s
[109/119] Installing python3-tabulate+widechars-0:0.9.0-18.fc43.noarch                                                                                                      100% |  60.5 KiB/s | 124.0   B |  00m00s
[110/119] Installing python3-sqlalchemy-0:2.0.48-1.fc43.x86_64                                                                                                              100% | 264.1 MiB/s |  24.6 MiB |  00m00s
[111/119] Installing python3-tables-0:3.10.2-7.fc43.x86_64                                                                                                                  100% | 209.6 MiB/s |  10.3 MiB |  00m00s
[112/119] Installing python3-aiohttp+speedups-0:3.13.3-4.fc43.x86_64                                                                                                        100% | 121.1 KiB/s | 124.0   B |  00m00s
[113/119] Installing python3-xlsxwriter-0:3.2.9-1.fc43.noarch                                                                                                               100% |  87.2 MiB/s |   1.7 MiB |  00m00s
[114/119] Installing python3-xlrd-0:2.0.1-26.fc43.noarch                                                                                                                    100% |  69.5 MiB/s |   1.0 MiB |  00m00s
[115/119] Installing python3-PyMySQL-0:1.1.2-2.fc43.noarch                                                                                                                  100% |  81.2 MiB/s | 415.8 KiB |  00m00s
[116/119] Installing python3-psycopg2-0:2.9.10-4.fc43.x86_64                                                                                                                100% | 103.7 MiB/s | 637.4 KiB |  00m00s
[117/119] Installing python3-QtPy-0:2.4.3-6.fc43.noarch                                                                                                                     100% |  20.7 MiB/s | 719.3 KiB |  00m00s
[118/119] Installing xclip-0:0.13-25.git11cba61.fc43.x86_64                                                                                                                 100% |   4.9 MiB/s |  60.1 KiB |  00m00s
[119/119] Installing xsel-0:1.2.1-9.fc43.x86_64                                                                                                                             100% |  21.3 KiB/s |  49.3 KiB |  00m02s
Complete!
```

then I looked for launching executables, with the command:
```
edwbuck@fedora:~$ rpm -ql jupyterlab | grep bin
/usr/bin/jlpm
/usr/bin/jupyter-lab
/usr/bin/jupyter-labextension
```

and ran `/usr/bin/jupyter-lab` which opened an interface at `http://localhost:8888/lab` on my web browser.

Testing the web browser access from a different browser indicated that the second browser was missing the
authentication token, so setup for the system was performed using `https://jupyter-server.readthedocs.io/en/latest/operators/public-server.html`

First I verified the `jupyter` command existed, and then generated the default config file.
```
edwbuck@fedora:~/.jupyter$ which jupyter
/usr/bin/jupyter
edwbuck@fedora:~/.jupyter$ /usr/bin/jupyter server --generate-config
Writing default config to: {config_file!r}
edwbuck@fedora:~/.jupyter$ ls
jupyter_server_config.py  lab
```

a password was then set
```
edwbuck@fedora:~/.jupyter$ jupyter server password
Enter password: 
Verify password: 
[JupyterPasswordApp] Wrote hashed password to /home/edwbuck/.jupyter/jupyter_server_config.json
```

With this, the notebook was relaunched to ensure no config file damage was done.

Finally the notebook was tested with the following:

```
import sys;
print(sys.prefix);
```
which resulted in
```
/usr
```

Everything was then shutdown and a new python environemnt was created:
```
edwbuck@fedora:~/.jupyter$ pip install --user ipykernel
Requirement already satisfied: ipykernel in /usr/lib/python3.14/site-packages (6.29.3)
Requirement already satisfied: comm>=0.1.1 in /usr/lib/python3.14/site-packages (from ipykernel) (0.2.3)
Requirement already satisfied: ipython>=7.23.1 in /usr/lib/python3.14/site-packages (from ipykernel) (8.37.0)
Requirement already satisfied: jupyter-client>=6.1.12 in /usr/lib/python3.14/site-packages (from ipykernel) (8.6.1)
Requirement already satisfied: jupyter-core!=5.0.*,>=4.12 in /usr/lib/python3.14/site-packages (from ipykernel) (5.8.1)
Requirement already satisfied: matplotlib-inline>=0.1 in /usr/lib/python3.14/site-packages (from ipykernel) (0.1.7)
Requirement already satisfied: nest-asyncio in /usr/lib/python3.14/site-packages (from ipykernel) (1.6.0)
Requirement already satisfied: packaging in /usr/lib/python3.14/site-packages (from ipykernel) (25.0)
Requirement already satisfied: psutil in /usr/lib64/python3.14/site-packages (from ipykernel) (7.0.0)
Requirement already satisfied: pyzmq>=24 in /usr/lib64/python3.14/site-packages (from ipykernel) (27.1.0)
Requirement already satisfied: tornado>=6.1 in /usr/lib64/python3.14/site-packages (from ipykernel) (6.5.2)
Requirement already satisfied: traitlets>=5.4.0 in /usr/lib/python3.14/site-packages (from ipykernel) (5.14.3)
Requirement already satisfied: decorator in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (5.2.1)
Requirement already satisfied: jedi>=0.16 in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (0.19.2)
Requirement already satisfied: pexpect>4.3 in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (4.9.0)
Requirement already satisfied: prompt_toolkit<3.1.0,>=3.0.41 in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (3.0.41)
Requirement already satisfied: pygments>=2.4.0 in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (2.19.1)
Requirement already satisfied: stack_data in /usr/lib/python3.14/site-packages (from ipython>=7.23.1->ipykernel) (0.6.3)
Requirement already satisfied: wcwidth in /usr/lib/python3.14/site-packages (from prompt_toolkit<3.1.0,>=3.0.41->ipython>=7.23.1->ipykernel) (0.6.0)
Requirement already satisfied: parso<0.9.0,>=0.8.4 in /usr/lib/python3.14/site-packages (from jedi>=0.16->ipython>=7.23.1->ipykernel) (0.8.5)
Requirement already satisfied: python-dateutil>=2.8.2 in /usr/lib/python3.14/site-packages (from jupyter-client>=6.1.12->ipykernel) (2.9.0.post0)
Requirement already satisfied: platformdirs>=2.5 in /usr/lib/python3.14/site-packages (from jupyter-core!=5.0.*,>=4.12->ipykernel) (4.2.2)
Requirement already satisfied: ptyprocess>=0.5 in /usr/lib/python3.14/site-packages (from pexpect>4.3->ipython>=7.23.1->ipykernel) (0.7.0)
Requirement already satisfied: six>=1.5 in /usr/lib/python3.14/site-packages (from python-dateutil>=2.8.2->jupyter-client>=6.1.12->ipykernel) (1.17.0)
Requirement already satisfied: executing>=1.2.0 in /usr/lib/python3.14/site-packages (from stack_data->ipython>=7.23.1->ipykernel) (2.2.1)
Requirement already satisfied: asttokens>=2.1.0 in /usr/lib/python3.14/site-packages (from stack_data->ipython>=7.23.1->ipykernel) (3.0.0)
Requirement already satisfied: pure_eval in /usr/lib/python3.14/site-packages (from stack_data->ipython>=7.23.1->ipykernel) (0.2.3)
edwbuck@fedora:~/.jupyter$ python -m ipykernel install --user --name=rag_demo_hpe
Installed kernelspec rag_demo_hpe in /home/edwbuck/.local/share/jupyter/kernels/rag_demo_hpe
edwbuck@fedora:~/.jupyter$ cat /home/edwbuck/.local/share/jupyter/kernels/rag_demo_hpe
cat: /home/edwbuck/.local/share/jupyter/kernels/rag_demo_hpe: Is a directory
edwbuck@fedora:~/.jupyter$ cat /home/edwbuck/.local/share/jupyter/kernels/rag_demo_hpe/
kernel.json     logo-32x32.png  logo-64x64.png  logo-svg.svg    
edwbuck@fedora:~/.jupyter$ cat /home/edwbuck/.local/share/jupyter/kernels/rag_demo_hpe/kernel.json 
{
 "argv": [
  "/usr/bin/python",
  "-Xfrozen_modules=off",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "display_name": "rag_demo_hpe",
 "language": "python",
 "metadata": {
  "debugger": true
 }
}
```

The the system was modified to create a kernel that would launch in a .venv accoring to the instructions
at `https://ipython.readthedocs.io/en/stable/install/kernel_install.html#kernels-for-different-environments`

And verified again with the same program
```
import sys;
print(sys.prefix);
```
which resulted in
```
/home/edwbuck/.conda/envs/rag_example_hpe
```

### Ollama installation

Based on web page `https://docs.fedoraproject.org/en-US/quick-docs/ollama/`

```
sudo dnf install ollama
```

yeilding
```
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ sudo dnf install ollama
Updating and loading repositories:
Repositories loaded.
Package "ollama-0.9.4-4.fc43.x86_64" is already installed.

Nothing to do.
```

Test the installation

```
ollama serve &
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama serve
time=2026-03-30T15:36:20.921-05:00 level=INFO source=routes.go:1235 msg="server config" env="map[CUDA_VISIBLE_DEVICES: GPU_DEVICE_ORDINAL: HIP_VISIBLE_DEVICES: HSA_OVERRIDE_GFX_VERSION: HTTPS_PROXY: HTTP_PROXY: NO_PROXY: OLLAMA_CONTEXT_LENGTH:4096 OLLAMA_DEBUG:INFO OLLAMA_FLASH_ATTENTION:false OLLAMA_GPU_OVERHEAD:0 OLLAMA_HOST:http://127.0.0.1:11434 OLLAMA_INTEL_GPU:false OLLAMA_KEEP_ALIVE:5m0s OLLAMA_KV_CACHE_TYPE: OLLAMA_LLM_LIBRARY: OLLAMA_LOAD_TIMEOUT:5m0s OLLAMA_MAX_LOADED_MODELS:0 OLLAMA_MAX_QUEUE:512 OLLAMA_MODELS:/home/edwbuck/.ollama/models OLLAMA_MULTIUSER_CACHE:false OLLAMA_NEW_ENGINE:false OLLAMA_NOHISTORY:false OLLAMA_NOPRUNE:false OLLAMA_NUM_PARALLEL:0 OLLAMA_ORIGINS:[http://localhost https://localhost http://localhost:* https://localhost:* http://127.0.0.1 https://127.0.0.1 http://127.0.0.1:* https://127.0.0.1:* http://0.0.0.0 https://0.0.0.0 http://0.0.0.0:* https://0.0.0.0:* app://* file://* tauri://* vscode-webview://* vscode-file://*] OLLAMA_SCHED_SPREAD:false ROCR_VISIBLE_DEVICES: http_proxy: https_proxy: no_proxy:]"
time=2026-03-30T15:36:20.921-05:00 level=INFO source=images.go:476 msg="total blobs: 0"
time=2026-03-30T15:36:20.922-05:00 level=INFO source=images.go:483 msg="total unused blobs removed: 0"
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] HEAD   /                         --> github.com/ollama/ollama/server.(*Server).GenerateRoutes.func1 (5 handlers)
[GIN-debug] GET    /                         --> github.com/ollama/ollama/server.(*Server).GenerateRoutes.func2 (5 handlers)
[GIN-debug] HEAD   /api/version              --> github.com/ollama/ollama/server.(*Server).GenerateRoutes.func3 (5 handlers)
[GIN-debug] GET    /api/version              --> github.com/ollama/ollama/server.(*Server).GenerateRoutes.func4 (5 handlers)
[GIN-debug] POST   /api/pull                 --> github.com/ollama/ollama/server.(*Server).PullHandler-fm (5 handlers)
[GIN-debug] POST   /api/push                 --> github.com/ollama/ollama/server.(*Server).PushHandler-fm (5 handlers)
[GIN-debug] HEAD   /api/tags                 --> github.com/ollama/ollama/server.(*Server).ListHandler-fm (5 handlers)
[GIN-debug] GET    /api/tags                 --> github.com/ollama/ollama/server.(*Server).ListHandler-fm (5 handlers)
[GIN-debug] POST   /api/show                 --> github.com/ollama/ollama/server.(*Server).ShowHandler-fm (5 handlers)
[GIN-debug] DELETE /api/delete               --> github.com/ollama/ollama/server.(*Server).DeleteHandler-fm (5 handlers)
[GIN-debug] POST   /api/create               --> github.com/ollama/ollama/server.(*Server).CreateHandler-fm (5 handlers)
[GIN-debug] POST   /api/blobs/:digest        --> github.com/ollama/ollama/server.(*Server).CreateBlobHandler-fm (5 handlers)
[GIN-debug] HEAD   /api/blobs/:digest        --> github.com/ollama/ollama/server.(*Server).HeadBlobHandler-fm (5 handlers)
[GIN-debug] POST   /api/copy                 --> github.com/ollama/ollama/server.(*Server).CopyHandler-fm (5 handlers)
[GIN-debug] GET    /api/ps                   --> github.com/ollama/ollama/server.(*Server).PsHandler-fm (5 handlers)
[GIN-debug] POST   /api/generate             --> github.com/ollama/ollama/server.(*Server).GenerateHandler-fm (5 handlers)
[GIN-debug] POST   /api/chat                 --> github.com/ollama/ollama/server.(*Server).ChatHandler-fm (5 handlers)
[GIN-debug] POST   /api/embed                --> github.com/ollama/ollama/server.(*Server).EmbedHandler-fm (5 handlers)
[GIN-debug] POST   /api/embeddings           --> github.com/ollama/ollama/server.(*Server).EmbeddingsHandler-fm (5 handlers)
[GIN-debug] POST   /v1/chat/completions      --> github.com/ollama/ollama/server.(*Server).ChatHandler-fm (6 handlers)
[GIN-debug] POST   /v1/completions           --> github.com/ollama/ollama/server.(*Server).GenerateHandler-fm (6 handlers)
[GIN-debug] POST   /v1/embeddings            --> github.com/ollama/ollama/server.(*Server).EmbedHandler-fm (6 handlers)
[GIN-debug] GET    /v1/models                --> github.com/ollama/ollama/server.(*Server).ListHandler-fm (6 handlers)
[GIN-debug] GET    /v1/models/:model         --> github.com/ollama/ollama/server.(*Server).ShowHandler-fm (6 handlers)
time=2026-03-30T15:36:20.922-05:00 level=INFO source=routes.go:1288 msg="Listening on 127.0.0.1:11434 (version 0.0.0)"
time=2026-03-30T15:36:20.922-05:00 level=INFO source=gpu.go:217 msg="looking for compatible GPUs"
time=2026-03-30T15:36:20.944-05:00 level=INFO source=gpu.go:377 msg="no compatible GPUs were discovered"
time=2026-03-30T15:36:20.944-05:00 level=INFO source=types.go:130 msg="inference compute" id=0 library=cpu variant="" compute="" driver=0.0 name="" total="30.7 GiB" available="8.7 GiB"
^Z
[1]+  Stopped                    ollama serve
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ bg
[1]+ ollama serve &
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama list
[GIN] 2026/03/30 - 15:36:42 | 200 |      41.519µs |       127.0.0.1 | HEAD     "/"
[GIN] 2026/03/30 - 15:36:42 | 200 |     230.423µs |       127.0.0.1 | GET      "/api/tags"
NAME    ID    SIZE    MODIFIED 
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama --help
Large language model runner

Usage:
  ollama [flags]
  ollama [command]

Available Commands:
  serve       Start ollama
  create      Create a model from a Modelfile
  show        Show information for a model
  run         Run a model
  stop        Stop a running model
  pull        Pull a model from a registry
  push        Push a model to a registry
  list        List models
  ps          List running models
  cp          Copy a model
  rm          Remove a model
  help        Help about any command

Flags:
  -h, --help      help for ollama
  -v, --version   Show version information

Use "ollama [command] --help" for more information about a command.
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama run llama2
[GIN] 2026/03/30 - 15:37:11 | 200 |      32.365µs |       127.0.0.1 | HEAD     "/"
[GIN] 2026/03/30 - 15:37:11 | 404 |     356.639µs |       127.0.0.1 | POST     "/api/show"
pulling manifest ⠧ time=2026-03-30T15:37:12.533-05:00 level=INFO source=download.go:177 msg="downloading 8934d96d3f08 in 16 239 MB part(s)"
pulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         tpulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling manifest 
pulling manifest 
pulling 8934d96d3f08: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling 8c17c2ebb0ea: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 7.0 KB                         
pulling 7c23fb36d801: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏ 4.8 KB                         
pulling 2e0493f67d0c: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏   59 B                         
pulling fa304d675061: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏   91 B                         
pulling 42ba7f8a01dd: 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████▏  557 B                         
verifying sha256 digest 
writing manifest 
success 
[GIN] 2026/03/30 - 15:38:31 | 200 |   14.618587ms |       127.0.0.1 | POST     "/api/show"
time=2026-03-30T15:38:31.377-05:00 level=INFO source=server.go:135 msg="system memory" total="30.7 GiB" free="8.9 GiB" free_swap="0 B"
time=2026-03-30T15:38:31.377-05:00 level=INFO source=server.go:175 msg=offload library=cpu layers.requested=-1 layers.model=33 layers.offload=0 layers.split="" memory.available="[8.9 GiB]" memory.gpu_overhead="0 B" memory.required.full="8.3 GiB" memory.required.partial="0 B" memory.required.kv="4.0 GiB" memory.required.allocations="[8.3 GiB]" memory.weights.total="3.5 GiB" memory.weights.repeating="3.4 GiB" memory.weights.nonrepeating="102.6 MiB" memory.graph.full="560.0 MiB" memory.graph.partial="681.0 MiB"
llama_model_loader: loaded meta data with 23 key-value pairs and 291 tensors from /home/edwbuck/.ollama/models/blobs/sha256-8934d96d3f08982e95922b2b7a2c626a1fe873d7c3b06e8e56d7bc0a1fef9246 (version GGUF V3 (latest))
llama_model_loader: Dumping metadata keys/values. Note: KV overrides do not apply in this output.
llama_model_loader: - kv   0:                       general.architecture str              = llama
llama_model_loader: - kv   1:                               general.name str              = LLaMA v2
llama_model_loader: - kv   2:                       llama.context_length u32              = 4096
llama_model_loader: - kv   3:                     llama.embedding_length u32              = 4096
llama_model_loader: - kv   4:                          llama.block_count u32              = 32
llama_model_loader: - kv   5:                  llama.feed_forward_length u32              = 11008
llama_model_loader: - kv   6:                 llama.rope.dimension_count u32              = 128
llama_model_loader: - kv   7:                 llama.attention.head_count u32              = 32
llama_model_loader: - kv   8:              llama.attention.head_count_kv u32              = 32
llama_model_loader: - kv   9:     llama.attention.layer_norm_rms_epsilon f32              = 0.000010
llama_model_loader: - kv  10:                          general.file_type u32              = 2
llama_model_loader: - kv  11:                       tokenizer.ggml.model str              = llama
llama_model_loader: - kv  12:                      tokenizer.ggml.tokens arr[str,32000]   = ["<unk>", "<s>", "</s>", "<0x00>", "<...
llama_model_loader: - kv  13:                      tokenizer.ggml.scores arr[f32,32000]   = [0.000000, 0.000000, 0.000000, 0.0000...
llama_model_loader: - kv  14:                  tokenizer.ggml.token_type arr[i32,32000]   = [2, 3, 3, 6, 6, 6, 6, 6, 6, 6, 6, 6, ...
llama_model_loader: - kv  15:                      tokenizer.ggml.merges arr[str,61249]   = ["▁ t", "e r", "i n", "▁ a", "e n...
llama_model_loader: - kv  16:                tokenizer.ggml.bos_token_id u32              = 1
llama_model_loader: - kv  17:                tokenizer.ggml.eos_token_id u32              = 2
llama_model_loader: - kv  18:            tokenizer.ggml.unknown_token_id u32              = 0
llama_model_loader: - kv  19:               tokenizer.ggml.add_bos_token bool             = true
llama_model_loader: - kv  20:               tokenizer.ggml.add_eos_token bool             = false
llama_model_loader: - kv  21:                    tokenizer.chat_template str              = {% if messages[0]['role'] == 'system'...
llama_model_loader: - kv  22:               general.quantization_version u32              = 2
llama_model_loader: - type  f32:   65 tensors
llama_model_loader: - type q4_0:  225 tensors
llama_model_loader: - type q6_K:    1 tensors
print_info: file format = GGUF V3 (latest)
print_info: file type   = Q4_0
print_info: file size   = 3.56 GiB (4.54 BPW) 
load: special_eos_id is not in special_eog_ids - the tokenizer config may be incorrect
load: special tokens cache size = 3
load: token to piece cache size = 0.1684 MB
print_info: arch             = llama
print_info: vocab_only       = 1
print_info: model type       = ?B
print_info: model params     = 6.74 B
print_info: general.name     = LLaMA v2
print_info: vocab type       = SPM
print_info: n_vocab          = 32000
print_info: n_merges         = 0
print_info: BOS token        = 1 '<s>'
print_info: EOS token        = 2 '</s>'
print_info: UNK token        = 0 '<unk>'
print_info: LF token         = 13 '<0x0A>'
print_info: EOG token        = 2 '</s>'
print_info: max token length = 48
llama_model_load: vocab only - skipping tensors
time=2026-03-30T15:38:31.405-05:00 level=INFO source=server.go:438 msg="starting llama server" cmd="/usr/lib64/ollama/bin/ollama runner --model /home/edwbuck/.ollama/models/blobs/sha256-8934d96d3f08982e95922b2b7a2c626a1fe873d7c3b06e8e56d7bc0a1fef9246 --ctx-size 8192 --batch-size 512 --threads 6 --no-mmap --parallel 2 --port 38111"
time=2026-03-30T15:38:31.405-05:00 level=INFO source=sched.go:483 msg="loaded runners" count=1
time=2026-03-30T15:38:31.405-05:00 level=INFO source=server.go:598 msg="waiting for llama runner to start responding"
time=2026-03-30T15:38:31.406-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
time=2026-03-30T15:38:31.415-05:00 level=INFO source=runner.go:815 msg="starting go runner"
load_backend: loaded CPU backend from /usr/lib64/ollama/libggml-cpu-alderlake.so
time=2026-03-30T15:38:31.449-05:00 level=INFO source=ggml.go:104 msg=system CPU.0.SSE3=1 CPU.0.SSSE3=1 CPU.0.AVX=1 CPU.0.AVX_VNNI=1 CPU.0.AVX2=1 CPU.0.F16C=1 CPU.0.FMA=1 CPU.0.BMI2=1 CPU.0.LLAMAFILE=1 CPU.1.LLAMAFILE=1 compiler=cgo(gcc)
time=2026-03-30T15:38:31.450-05:00 level=INFO source=runner.go:874 msg="Server listening on 127.0.0.1:38111"
llama_model_loader: loaded meta data with 23 key-value pairs and 291 tensors from /home/edwbuck/.ollama/models/blobs/sha256-8934d96d3f08982e95922b2b7a2c626a1fe873d7c3b06e8e56d7bc0a1fef9246 (version GGUF V3 (latest))
llama_model_loader: Dumping metadata keys/values. Note: KV overrides do not apply in this output.
llama_model_loader: - kv   0:                       general.architecture str              = llama
llama_model_loader: - kv   1:                               general.name str              = LLaMA v2
llama_model_loader: - kv   2:                       llama.context_length u32              = 4096
llama_model_loader: - kv   3:                     llama.embedding_length u32              = 4096
llama_model_loader: - kv   4:                          llama.block_count u32              = 32
llama_model_loader: - kv   5:                  llama.feed_forward_length u32              = 11008
llama_model_loader: - kv   6:                 llama.rope.dimension_count u32              = 128
llama_model_loader: - kv   7:                 llama.attention.head_count u32              = 32
llama_model_loader: - kv   8:              llama.attention.head_count_kv u32              = 32
llama_model_loader: - kv   9:     llama.attention.layer_norm_rms_epsilon f32              = 0.000010
llama_model_loader: - kv  10:                          general.file_type u32              = 2
llama_model_loader: - kv  11:                       tokenizer.ggml.model str              = llama
llama_model_loader: - kv  12:                      tokenizer.ggml.tokens arr[str,32000]   = ["<unk>", "<s>", "</s>", "<0x00>", "<...
⠙ llama_model_loader: - kv  13:                      tokenizer.ggml.scores arr[f32,32000]   = [0.000000, 0.000000, 0.000000, 0.0000...
llama_model_loader: - kv  14:                  tokenizer.ggml.token_type arr[i32,32000]   = [2, 3, 3, 6, 6, 6, 6, 6, 6, 6, 6, 6, ...
llama_model_loader: - kv  15:                      tokenizer.ggml.merges arr[str,61249]   = ["▁ t", "e r", "i n", "▁ a", "e n...
llama_model_loader: - kv  16:                tokenizer.ggml.bos_token_id u32              = 1
llama_model_loader: - kv  17:                tokenizer.ggml.eos_token_id u32              = 2
llama_model_loader: - kv  18:            tokenizer.ggml.unknown_token_id u32              = 0
llama_model_loader: - kv  19:               tokenizer.ggml.add_bos_token bool             = true
llama_model_loader: - kv  20:               tokenizer.ggml.add_eos_token bool             = false
llama_model_loader: - kv  21:                    tokenizer.chat_template str              = {% if messages[0]['role'] == 'system'...
llama_model_loader: - kv  22:               general.quantization_version u32              = 2
llama_model_loader: - type  f32:   65 tensors
llama_model_loader: - type q4_0:  225 tensors
llama_model_loader: - type q6_K:    1 tensors
print_info: file format = GGUF V3 (latest)
print_info: file type   = Q4_0
print_info: file size   = 3.56 GiB (4.54 BPW) 
load: special_eos_id is not in special_eog_ids - the tokenizer config may be incorrect
load: special tokens cache size = 3
load: token to piece cache size = 0.1684 MB
print_info: arch             = llama
print_info: vocab_only       = 0
print_info: n_ctx_train      = 4096
print_info: n_embd           = 4096
print_info: n_layer          = 32
print_info: n_head           = 32
print_info: n_head_kv        = 32
print_info: n_rot            = 128
print_info: n_swa            = 0
print_info: n_swa_pattern    = 1
print_info: n_embd_head_k    = 128
print_info: n_embd_head_v    = 128
print_info: n_gqa            = 1
print_info: n_embd_k_gqa     = 4096
print_info: n_embd_v_gqa     = 4096
print_info: f_norm_eps       = 0.0e+00
print_info: f_norm_rms_eps   = 1.0e-05
print_info: f_clamp_kqv      = 0.0e+00
print_info: f_max_alibi_bias = 0.0e+00
print_info: f_logit_scale    = 0.0e+00
print_info: f_attn_scale     = 0.0e+00
print_info: n_ff             = 11008
print_info: n_expert         = 0
print_info: n_expert_used    = 0
print_info: causal attn      = 1
print_info: pooling type     = 0
print_info: rope type        = 0
print_info: rope scaling     = linear
print_info: freq_base_train  = 10000.0
print_info: freq_scale_train = 1
print_info: n_ctx_orig_yarn  = 4096
print_info: rope_finetuned   = unknown
print_info: ssm_d_conv       = 0
print_info: ssm_d_inner      = 0
print_info: ssm_d_state      = 0
print_info: ssm_dt_rank      = 0
print_info: ssm_dt_b_c_rms   = 0
print_info: model type       = 7B
print_info: model params     = 6.74 B
print_info: general.name     = LLaMA v2
print_info: vocab type       = SPM
print_info: n_vocab          = 32000
print_info: n_merges         = 0
print_info: BOS token        = 1 '<s>'
print_info: EOS token        = 2 '</s>'
print_info: UNK token        = 0 '<unk>'
print_info: LF token         = 13 '<0x0A>'
print_info: EOG token        = 2 '</s>'
print_info: max token length = 48
load_tensors: loading model tensors, this can take a while... (mmap = false)
load_tensors:          CPU model buffer size =  3647.87 MiB
⠹ time=2026-03-30T15:38:31.657-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠙ llama_context: constructing llama_context
llama_context: n_seq_max     = 2
llama_context: n_ctx         = 8192
llama_context: n_ctx_per_seq = 4096
llama_context: n_batch       = 1024
llama_context: n_ubatch      = 512
llama_context: causal_attn   = 1
llama_context: flash_attn    = 0
llama_context: freq_base     = 10000.0
llama_context: freq_scale    = 1
llama_context:        CPU  output buffer size =     0.28 MiB
llama_kv_cache_unified: kv_size = 8192, type_k = 'f16', type_v = 'f16', n_layer = 32, can_shift = 1, padding = 32
⠋ time=2026-03-30T15:38:37.389-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠸ time=2026-03-30T15:38:37.721-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠸ time=2026-03-30T15:38:45.700-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠴ time=2026-03-30T15:38:45.952-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠋ time=2026-03-30T15:38:46.403-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠙ time=2026-03-30T15:38:47.557-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠼ time=2026-03-30T15:38:51.795-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠦ time=2026-03-30T15:38:52.053-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠧ time=2026-03-30T15:39:08.275-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠏ time=2026-03-30T15:39:08.527-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠋ time=2026-03-30T15:39:14.617-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠇ time=2026-03-30T15:39:15.320-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠸ time=2026-03-30T15:39:16.833-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server not responding"
⠦ time=2026-03-30T15:39:17.088-05:00 level=INFO source=server.go:632 msg="waiting for server to become available" status="llm server loading model"
⠋ llama_kv_cache_unified:        CPU KV buffer size =  4096.00 MiB
llama_kv_cache_unified: KV self size  = 4096.00 MiB, K (f16): 2048.00 MiB, V (f16): 2048.00 MiB
llama_context:        CPU compute buffer size =   560.01 MiB
llama_context: graph nodes  = 1094
llama_context: graph splits = 1
⠙ time=2026-03-30T15:39:18.602-05:00 level=INFO source=server.go:637 msg="llama runner started in 47.20 seconds"
[GIN] 2026/03/30 - 15:39:18 | 200 | 47.256670412s |       127.0.0.1 | POST     "/api/generate"
>>> help
Of course! I'd be happy to help. Can you please provide more context or clarify what you need help with? Are you looking for general information, or do you have a specific problem you're trying to solve?[GIN] 2026/03/30 - 15:39:34 | 200 |  6.557393737s |       127.0.0.1 | POST     "/api/chat"


>>> \q
I apologize, but I'm not sure I understand what you are saying. Could you please provide more context or clarify your question? I'll do my best to help.[GIN] 2026/03/30 - 15:39:46 | 200 |  5.444104244s |       127.0.0.1 | POST     "/api/chat"


>>> exit
Thank you for using me! I'm here to help you with any questions or problems you might have. If you want to exit the chat, just type "goodbye" and I will end the conversation. Otherwise, feel free to ask me 
anything or start a new topic. Have a great day![GIN] 2026/03/30 - 15:39:58 | 200 |  9.158374471s |       127.0.0.1 | POST     "/api/chat"


>>> goodbye
Thank you for chatting with me! If you have any other questions or need help in the future, don't hesitate to reach out. Have a great day and goodbye![GIN] 2026/03/30 - 15:40:06 | 200 |  6.239668521s |       127.0.0.1 | POST     "/api/chat"


>>> goodbye
Goodbye! It was nice chatting with you. If you have any other questions or need help in the future, feel free to come back and ask me anything. Have a great day![GIN] 2026/03/30 - 15:40:22 | 200 |  5.624599747s |       127.0.0.1 | POST     "/api/chat"


>>> 
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama list
[GIN] 2026/03/30 - 15:40:33 | 200 |      27.402µs |       127.0.0.1 | HEAD     "/"
[GIN] 2026/03/30 - 15:40:33 | 200 |     292.692µs |       127.0.0.1 | GET      "/api/tags"
NAME             ID              SIZE      MODIFIED      
llama2:latest    78e26419b446    3.8 GB    2 minutes ago    
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama rm llama2
[GIN] 2026/03/30 - 15:40:50 | 200 |      35.765µs |       127.0.0.1 | HEAD     "/"
[GIN] 2026/03/30 - 15:40:50 | 200 |     692.849µs |       127.0.0.1 | POST     "/api/generate"
[GIN] 2026/03/30 - 15:40:50 | 200 |   30.187393ms |       127.0.0.1 | DELETE   "/api/delete"
deleted 'llama2'
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ ollama list
[GIN] 2026/03/30 - 15:40:55 | 200 |       19.13µs |       127.0.0.1 | HEAD     "/"
[GIN] 2026/03/30 - 15:40:55 | 200 |      73.742µs |       127.0.0.1 | GET      "/api/tags"
NAME    ID    SIZE    MODIFIED 
(rag_example_hpe) (base) edwbuck@fedora:~/rag_example_hpe/architecture$ 
```


