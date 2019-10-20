# Zuul - Project Gating System  
* Zuul is a program that drives continuous integration, delivery, and deployment systems with a focus on project gating and interrelated projects.
## Zuul concepts
* Based on pipelines
	* For instance, a “check” pipeline might describe the actions which should cause newly proposed changes to projects to be tested.
	* A “gate” pipeline might implement Project Gating to automate merging changes to projects only if their tests pass. A “post” pipeline might update published documentation for a project when changes land.
	* Once a pipeline has been defined, any number of projects may be associated with it, each one specifying what jobs should be run for that project in a given pipeline.
	* Pipelines have associated triggers which are descriptions of events which should cause something to be enqueued into a pipeline. For example, when a patchset is uploaded to Gerrit, a Gerrit patchset-created event is emitted.
* Project Gating
	* In traditional Continous Delivery projects broken mainline is often an issue. Especially when number of contributors is big. To prevent that Project Gating is introduced.
	* The process of gating attempts to prevent changes that introduce regressions from being merged. This keeps the mainline of development open and working for all developers, and only when a change is confirmed to work without disruption is it merged.
## Zuul can maintain multiple projects. It also supports: 
* Testin in parallel
* Cross Project Testing (to be sure that projects are tested against correct versions of themselves)
* Cross-Proejct Dependencies 