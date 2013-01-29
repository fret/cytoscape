Cytoscape
=========

Entire Cytoscape 3 projects.

# How to build Cytoscape 3

## Requirments

You need the following software to build Cytoscape 3:

* JDK 6 or later
* Maven 3
* Git

If you are a core developer, you also need:

* [git-flow](https://github.com/nvie/gitflow)
  * Cytoscape 3 Core Projects are managed by following this branching rule:
    * [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)

If you want to clone all sub-projects at once, you also need:

* [Repo](http://code.google.com/p/git-repo/)

## Cytoscape 3 Project Structure
* API
* Impl
* Support
* GUI-Distribution
* Headless-Distribution
* APP-Developer
* Samples

## Clone All Cytoscape 3 Sub-Projects

```
repo init -u git@github.com:cytoscape/cytoscape.git
repo sync
```

Then, you need to create local branches

```
repo start master api impl gui-distribution support parent headless-distribution

repo start develop master api impl gui-distribution support parent headless-distribution
```

### For Core Developer
Before start development, you need to initialize your repo with git flow:

For each sun-project, run the following command:

```
git flow init -d
git checkout develop
```

You need write permission to push your code.  The following is for impl bundle:

```
git remote set-url origin git@github.com:cytoscape/cytoscape-impl.git
```

Make sure you are on the right branch.

```
git branch -a
```

You can clone Cytoscape 3 project manually if you want.

## Build
From the top directory, type:
```
mvn clean install
```
