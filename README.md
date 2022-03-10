# Committing to our project

Every change to our project has to be designed that way: a holistic container - branch consists of smaller changes - commits.

For each and every change a new branch shall be created and then merged (**only by a pull request**) into the **develop** branch.
After a successful merge such branch shall be deleted.

## Naming conventions

There are two types of work that us, developers, carry out: hotfixes and features.
Thus, every branch shall follow strict naming conventions:

- branch names shall begin with the keywords: *hotfix* or *feature*;
- after a keyword a slash should appear
- after a slash please provide a task / story number from jira
- if a task / story that would be suitable and match your branch didn't exist in jira, create a new one :D

E.g.: *feature/add-component-main*

## Commit rules
- first line of the commit message should comprise a short description - like a title
- second line should be blank
- start a detailed description from the third line

E.g.:
```angular2html
add a new component

The purpose of this commit is to include a new 
component - test1 - and two unit tests that 
asses code correctness.
```

## Merge rules
- manual branch merging is strictly forbidden
- merging can only take place through a pull request
- to merge a pull request three conditions must be fulfilled:
  - the pull request must receive approvals from at least 2 developers
  - all the CI test must pass
  - all the code review threads must be resolved
- ```hotfix/``` and ```feature/``` branches **cannot** be merged into the main branch directly
- ```hotfix/``` and ```feature/``` branches can be merged to the ```develop``` branch
- the ```develop``` branch shall be merged into the ```main``` branch (aka. ```release```) on an established CI meeting as a team effort

# Continuous Integration Effort

Every time a Pull Request for main and develop branches a CI workflow (pipeline) is run by a Jenkins docker.

In order to merge the branches from the pull request, all the tests have to pass.

Every time a Pull Request is merged, the new content is automatically published on our VPS.