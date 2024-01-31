step by step command line of what I did in new / empty repo.

1) create venv
```
➜  scratch (main) python3.10 -m venv ~/.venv/scratch --upgrade-deps
➜  scratch (main) source ~/.venv/scratch/bin/activate
```
2) setup requirements (my version of step 1 of docs)
```
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
```
3) create echo (following step 3 of docs)
```
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
```
4) poosh to main
```
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
```
5) back to the browser!

- installed scratch ==>
![Screenshot 2024-01-31 at 7 44 09 AM](https://github.com/wall-rl/scratch/assets/151564827/e0a8eb5e-05e7-4f61-876b-cc96a26404e5)

- fireworks on dashboard for URL: https://docs.runloop.ai/lab?installation_id=46770048&setup_action=update
![Screenshot 2024-01-31 at 7 44 24 AM](https://github.com/wall-rl/scratch/assets/151564827/87b3d65d-c247-4b1c-9bf7-e73c9395b795)

6) in the logs?
```
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]15:46:41.830 [JettyServerThreadPool-28] INFO  a.r.s.b.c.GithubWebhookRestHandler - handleWebhook event=push hookId=448990357 delivery=ed776c42-c04f-11ee-8b0b-8619b42d55ae
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]15:46:41.835 [JettyServerThreadPool-28] ERROR a.r.s.b.c.p.GithubPushEventController - Error in HandlePushWebhookWorkflow
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]java.util.NoSuchElementException: null
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at com.google.common.collect.AbstractIndexedListIterator.next(AbstractIndexedListIterator.java:80)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at com.google.common.collect.Iterators.getOnlyElement(Iterators.java:309)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at com.google.common.collect.Iterables.getOnlyElement(Iterables.java:263)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at ai.runloop.server.db.model.control.repo.RepoDao.loadByOwnerAndName(RepoDao.java:21)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at ai.runloop.server.bundler.controllers.push.GithubPushEventController.handle(GithubPushEventController.java:88)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at ai.runloop.server.bundler.controllers.push.GithubPushEventController.handle(GithubPushEventController.java:30)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at ai.runloop.server.bundler.controllers.GithubWebhookRestHandler$ContextHandler.executeHandler(GithubWebhookRestHandler.java:79)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at ai.runloop.server.bundler.controllers.GithubWebhookRestHandler.handle(GithubWebhookRestHandler.java:58)
2024-01-31T15:46:41Z app[9080e19df507e8] sea [info]	at io.javalin.routing.HandlerEntry.handle(HandlerEntry.kt:19)
```
