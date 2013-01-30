Cytoscape 3
=========

This is the top-level project for Cytoscape 3.  If you want to build the entire Cytoscpae 3 project, you need to follow this instruction.


# Cytoscape 3 Project Structure
Cytoscape 3 currently consists of the following sub-projects:

* API
* Impl
* Support
* GUI-Distribution
* Headless-Distribution
* APP-Developer
* Samples

If you just want to build the Desktop version of Cytoscape 3, you just need to clone and build *GUI-Distribution* subproject.

# How to build Cytoscape 3

## Requirments

You need the following software packages to build Cytoscape 3:

* JDK 6 or later
* Maven 3
* Git
  * There are several good GUI frontend for git:
    * Atlassian [SourceTree](http://www.sourcetreeapp.com/)

If you are a core developer, you also need:

* [git-flow](https://github.com/nvie/gitflow)
  * Cytoscape 3 Core Projects are managed by following this branching rule:
    * [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)

If you want to clone all sub-projects at once, you also need:

* [Repo](http://code.google.com/p/git-repo/) - Collection of Python scripts to manage multiple git repositoris.




## Clone Cytoscape 3 Sub-Projects

There are two ways to clone Cytoscape projects:

1. Use regular git commands and clone each subproject one by one.
1. Use repo to clone all subprojects at once.


### Clone with repo
You need to install repo before you run the following command.

```
repo init -u git@github.com:cytoscape/cytoscape.git
repo sync
```

At this point, your Then, you need to create local branches

```
repo start master api impl gui-distribution support parent headless-distribution
repo start develop master api impl gui-distribution support parent headless-distribution
```

Finally, switch to the develop branch:

```
repo checkout develop
```

#### For Core Developer
Before start development, you need to initialize your repo with git flow:

For each sun-project, run the following command:

```
git flow init -d
```

You need write permission to push your code.  The following is for impl bundle:

```
git remote set-url origin git@github.com:cytoscape/cytoscape-impl.git
```

Now you can push your changes to the upstream.


### Clone with git commands
Of course, you can clone Cytoscape 3 subprojects manually.  First, you need to clone this top-level project to 

```
git clone git://github.com/cytoscape/cytoscape.git
```

Then, you can clone each subproject:

```
cd cytoscape
git clone git://github.com/cytoscape/cytoscape-api.git
git clone git://github.com/cytoscape/cytoscape-impl.git
git clone git://github.com/cytoscape/cytoscape-support.git
.
.
.

```


## Build

Make sure you are on *develop* branch.

```
git branch -a
```

From the top directory, just type:

```
mvn clean install

```
