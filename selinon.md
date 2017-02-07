Selinon - distributed computing in Python
=========================================

Use celery, a distributed task queue.

Celery primitives:
 - Group
 - Chain
 - Chord
 - etc

Pitfalls
 - hard-coded flow
 - failures ?
 - flow visualization

Selinon solves that

flow logic in yaml files, grouping tasks into flows representing graph of
dependencies

you can use condition. eg if a field exists in env, or if a value is present
in result

Pluggable with any storage engine with subclassing and configuration

Fallbacks:
You can define tasks to run if some other task(s) fail

You can use flows as block of other flows

Yaml configuration file for reusability, visibility and clarity

Other features
--------------

Cache
Throttling
prioritization
Tracepoints

Selinon in a nutshell
---------------------

Built on top of celery
simple yaml config
separation of task logic and result storing
conditional task execution
group tasks into flows
advanced task flow handling
