# [JENKINS-11337](https://issues.jenkins-ci.org/browse/JENKINS-11337) Multiple branches ignored

A [git-flow branching workflow](http://nvie.com/posts/a-successful-git-branching-model/)
was not detecting changes when Jochen Ulrich defined "Branches to Build" as
"**" and added the additional behavior to prune stale remote-tracking
branches.

Steps I took trying to duplicate the problem:

* Install git-flow on my Ubuntu development machine
* Initialize the git-flow branching
```
# Create a master branch
git checkout -b JENKINS-11337/master

# Create a develop branch
git checkout -b JENKINS-11337/develop

# Initialize git flow branching (answers in comment)
git flow init
# [gitflow "branch"]
# 	master = JENKINS-11337/master
# 	develop = JENKINS-11337/develop
# [gitflow "prefix"]
# 	feature = JENKINS-11337/feature/
# 	release = JENKINS-11337/release/
# 	hotfix = JENKINS-11337/hotfix/
# 	support = JENKINS-11337/support/
# 	versiontag = JENKINS-11337-

# Start a feature branch named bug-check-1
git flow feature start bug-check-1
```
