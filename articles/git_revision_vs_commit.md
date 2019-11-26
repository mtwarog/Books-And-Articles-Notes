# Git: Revision vs Commit
* "revision" refers to the id you can use as a parameter to reference an object in git (usually a commit).
* Following rev parameters doesn't reference a commit: <rev>:<path>, e.g. HEAD:README, :README, master:./README
	* A suffix : followed by a path names the blob or tree at the given path in the tree-ish object named by the part before the colon.
* More detailed answer: https://stackoverflow.com/a/11792712/6708274