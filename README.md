step by step command line of what I did in new / empty repo.

1) create venv

➜  scratch (main) python3.10 -m venv ~/.venv/scratch --upgrade-deps
➜  scratch (main) source ~/.venv/scratch/bin/activate

2) setup requirements (my version of step 1 of docs)

(scratch) ➜  scratch (main) pip install runloop                                                                                       ✱
Collecting runloop
  Downloading runloop-0.0.4.tar.gz (3.9 kB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Building wheels for collected packages: runloop
  Building wheel for runloop (pyproject.toml) ... done
  Created wheel for runloop: filename=runloop-0.0.4-py3-none-any.whl size=4037 sha256=541733925d44c5945cb83174998bc609681b76efb68e24cb76dad795ba6e233d
  Stored in directory: /Users/wall/Library/Caches/pip/wheels/72/2f/33/5e4b9b5aaca0cde26579151d0281134bcff3d859e994efe179
Successfully built runloop
Installing collected packages: runloop
Successfully installed runloop-0.0.4
(scratch) ➜  scratch (main) pip freeze > requirements.txt

3) create echo