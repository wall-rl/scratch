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

3) create echo (following step 3 of docs)

(scratch) ➜  scratch (main) pbpaste > echo.py                                                                                       ✭ ✱
(scratch) ➜  scratch (main) cat echo.py                                                                                             ✭ ✱
import runloop

@runloop.loop
def echo(metadata: dict[str, str], greeting: list[str]) -> tuple[list[str], dict[str, str]]:
    return [f"hello runloop! {greeting[0]}"], metadata
(scratch) ➜  scratch (main) pbpaste > runloop.toml                                                                                  ✭ ✱
(scratch) ➜  scratch (main) cat runloop.toml                                                                                        ✭ ✱
[module]
path = "."
name = "echo"
(scratch) ➜  scratch (main)

4) poosh to main

(scratch) ➜  scratch (main) gtcp                                                                                                      ✈
DO NOT COMMIT TO MAIN!
(scratch) ➜  scratch (main) git commit -am "jsut do it"                                                                               ✈
[main 4972945] jsut do it
 6 files changed, 74 insertions(+), 1 deletion(-)
 create mode 100644 #README.md#
 create mode 120000 .#README.md
 create mode 100644 echo.py
 create mode 100644 requirements.txt
 create mode 100644 runloop.toml
(scratch) ➜  scratch (main) adb
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (8/8), 1.52 KiB | 1.52 MiB/s, done.
Total 8 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:wall-rl/scratch.git
   5bcc8e8..4972945  HEAD -> main
the branch to compare 'main' is the default branch

5) back to the browser!

- installed scratch ==>


- fireworks on dashboard for URL: https://docs.runloop.ai/lab?installation_id=46770048&setup_action=update