# Enternships Guides
A set of commonly agreed upon practices and style guides to follow when working on Enternships projects.

This is not a definitive guide and is susceptible to be updates.

Open a pull request with your recommended updates to contribute.


## Git branching model
We have simplified the original The [git-flow](http://nvie.com/posts/a-successful-git-branching-model/) to be less cumbersome. 

Branches involved:
- **production** (reflects what is deployed in production)
- **staging** (reflects what is deployed in staging)
- feature_ (prefix for feature branches)
- bugfix_ (prefix for bugfix branches)

### Creating a new feature
Branch of the latest version of **staging** and prefix your branch name with **feature_**. When the feature is completed create a pull request to merge the feature into **staging**.

```
staging                 o---o----------o
                             \        /
feature_user_profofile        ---o---o

```

### Deploying to production
It is as simple as merging **staging** into **production**.

```
production               o---o-----o
                                  /
staging                  o---o---o

```

### Creating a bugfix
Branch of the latest version of **production** and prefix your branch name with **bugfix_**. When the bug is fixed create a pull request to merge the bugfix into **production**. You also merge the **bugfix_** branch in **staging**.

```
production              o---o----------o
                             \        /
bugfix_user_signout           ---o---o
                                      \
staging                 o------o-------o

```
