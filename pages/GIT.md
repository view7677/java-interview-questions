## GIT
*******



#### 822. How can we see n most recent commits in GIT?

We can use git log command to see the latest commits. To see the
three most recent commits we use following command:
`git log -3`

#### 823. How can we know if a branch is already merged into master in GIT?

We can use following commands for this purpose:

`git branch --merged master` : This prints the branches merged into
master.

`git branch --merged lists` : This prints the branches merged into
HEAD (i.e. tip of current branch)

`git branch --no-merged` : This prints the branches that have not been
merged

By default this applies only to local branches.
We can use -a flag to show both local and remote branches.
Or we can use -r flag to show only the remote branches.

#### 824. What is the purpose of git stash drop?

In case we do not need a specific stash, we use git stash drop
command to remove it from the list of stashes.

By default, this command removes to latest added stash

To remove a specific stash we specify as argument in the git stash
drop <stashname> command.

#### 825. What is the HEAD in GIT?

A HEAD is a reference to the currently checked out commit. It is a symbolic reference to the branch that we have checked out. At any given time, one head is selected as the ‘current head’ This head is also known as HEAD (always in uppercase).


#### 826. What is the most popular branching strategy in GIT?

There are many ways to do branching in GIT. One of the popular
ways is to maintain two branches:

**master**: This branch is used for production. In this branch HEAD is
always in production ready state.

**develop**: This branch is used for development. In this branch we
store the latest code developed in project. This is work in progress
code.

Once the code is ready for deployment to production, it is merged
into master branch from develop branch.

#### 827. What is SubGit?

SubGit is software tool used for migrating SVN to Git. It is very
easy to use. By using this we can create a writable Git mirror of a
Subversion repository.

It creates a bi-directional mirror that can be used for pushing to Git
as well as committing to Subversion.

SubGit also takes care of synchronization between Git and
Subversion.

#### 828. What is the use of git instaweb?


Git-instaweb is a script by which we can browse a git repository in
a web browser.

It sets up the gitweb and a web-server that makes the working
repository available online.

#### 829.What are git hooks?

Git hooks are scripts that can run automatically on the occurrence of
an event in a Git repository. These are used for automation of
workflow in GIT.

Git hooks also help in customizing the internal behavior of GIT.
These are generally used for enforcing a GIT commit policy.


#### 830. What is GIT?

GIT is a mature **D**istributed **V**ersion **C**ontrol **S**ystem (DVCS). It is
used for **S**ource **C**ode **M**anagement (SCM).

It is open source software. It was developed by Linus Torvalds, the creator of Linux operating system.

GIT works well with a large number of IDEs (**I**ntegrated **D**evelopment **E**nvironments) like- Eclipse, InteliJ etc. GIT can be used to handle small and large projects.


#### 831. What is a repository in GIT?

A repository in GIT is the place in which we store our software
work.

It contains a sub-directory called .git. There is only one .git
directory in the root of the project.

In .git, GIT stores all the metadata for the repository. The contents
of .git directory are of internal use to GIT.

#### 832. What are the main benefits of GIT?

There are following main benefits of GIT:

Distributed System: GIT is a **D**istributed **V**ersion **C**ontrol
**S**ystem (DVCS). So you can keep your private work in version control but completely hidden from others. You can work offline as well.

1. **Flexible Workflow**: GIT allows you to create your own workflow. You can use the process that is suitable for your project. You can go for centralized or master-slave or any other workflow.

2. **Fast**: GIT is very fast when compared to other version control systems.

3. **Data Integrity**: Since GIT uses SHA1, data is not easier to corrupt.

4. **Free**:  It is free for personal use. So many amateurs use it for their initial projects. It also works very well with large size project.

5. **Collaboration**: GIT is very easy to use for projects in which collaboration is required. Many popular open source software across the globe use GIT.

#### 833. What are the disadvantages of GIT?

GIT has very few disadvantages. These are the scenarios when GIT
is difficult to use. Some of these are:

**Binary Files**: If we have a lot binary files (non-text) in our
project, then GIT becomes very slow. E.g. Projects with a
lot of images or Word documents.

**Steep Learning Curve**: It takes some time for a newcomer
to learn GIT. Some of the GIT commands are non-intuitive
to a fresher.

**Slow remote speed**: Sometimes the use of remote
repositories in slow due to network latency. Still GIT is
better than other VCS in speed.


#### 834. What are the main differences between GIT and SVN?

The main differences between GIT and SVN are:

1. **Decentralized**: GIT is decentralized. You have a local
copy that is a repository in which you can commit. In SVN
you have to always connect to a central repository for
check-in.
2. **Complex to learn**: GIT is a bit difficult to learn for some
developers. It has more concepts and commands to learn.
SVN is much easier to learn.
3. **Unable to handle Binary files**: GIT becomes slow when it
deals with large binary files that change frequently. SVN
can handle large binary files easily.
4. **Internal directory**: GIT creates only .git directory. SVN
creates .svn directory in each folder.
5. **User Interface**: GIT does not have good UI. But SVN has
good user interfaces.

#### 835. How will you start GIT for your project?

We use git init command in an existing project directory to start
version control for our project.

After this we can use git add and git commit commands to add files
to our GIT repository.

#### 836. What is git clone in GIT?

In GIT, we use git clone command to create a copy of an existing
GIT repository in our local.
This is the most popular way to create a copy of the repository
among developers.

It is similar to svn checkout. But in this case the working copy is a
full-fledged repository.

#### 837. How will you create a repository in GIT?



#### 838. What are the different ways to start work in GIT?



#### 839. GIT is written in which language?



#### 840. What does ‘git pull’ command in GIT do internally?



#### 841. What does ‘git push’ command in GIT do internally?



#### 842. What is git stash?



#### 843. What is the meaning of ‘stage’ in GIT?



#### 844. What is the purpose of git config command?



#### 845. How can we see the configuration settings of GIT installation?



#### 846. How will you write a message with commit command in GIT?



#### 847. What is stored inside a commit object in GIT?



#### 848. How many heads can you create in a GIT repository?



#### 849. Why do we create branches in GIT?



#### 850. What are the different kinds of branches that can be created in GIT?



#### 851.How will you create a new branch in GIT?



#### 852. How will you add a new feature to the main branch?



#### 853. What is a pull request in GIT?



#### 854. What is merge conflict in GIT?



#### 855. How can we resolve a merge conflict in GIT?



#### 856. What command will you use to delete a branch?



#### 857. What command will you use to delete a branch that has unmerged changes?



#### 858. What is the alternative command to merging in GIT?



#### 859. What is Rebasing in GIT?



#### 860. What is the ‘Golden Rule of Rebasing’ in GIT?



#### 861. Why do we use Interactive Rebasing in place of Auto Rebasing?



#### 862. What is the command for Rebasing in Git?



#### 863. What is the main difference between git clone and git remote?



#### 864. What is GIT version control?



#### 865. What GUI do you use for working on GIT?



#### 866. What is the use of git diff command in GIT?



#### 867. What is git rerere?



#### 868. What are the three most popular version of git diff command?



#### 869. What is the use of git status command?



#### 870. What is the main difference between git diff and git status?



#### 871. What is the use of git rm command in GIT?872.What is the command to apply a stash?



#### 873. Why do we use git log command?



#### 874. Why do we need git add command in GIT?



#### 875. Why do we use git reset command?



#### 876. What does a commit object contain?



#### 877. How can we convert git log messages to a different format?



#### 878. What are the programming languages in which git hooks can be written?



#### 879. What is a commit message in GIT?



#### 880. How GIT protects the code in a repository?



#### 881. How GIT provides flexibility in version control?



#### 882. How can we change a commit message in GIT? 



#### 883. Why is it advisable to create an additional commit instead of amending an existing commit?



#### 884. What is a bare repository in GIT?



#### 885. How do we put a local repository on GitHub server?



#### 886. How will you delete a branch in GIT?



#### 887. How can we set up a Git repository to run code sanity checks and UAT tests just before a commit?



#### 888. How can we revert a commit that was pushed earlier and is public now?



#### 889. In GIT, how will you compress last n commits into a single commit?



#### 890. How will you switch from one branch to a new branch in GIT?



#### 891. How can we clean unwanted files from our working directory in GIT?



#### 892. What is the purpose of git tag command?



#### 893. What is cherry-pick in GIT?



#### 894. What is shortlog in GIT?



#### 895. How can you find the names of files that were changed in a specific commit?



#### 896. How can we attach an automated script to run on the event of a new commit by push command?



#### 897. What is the difference between pre-receive, update and post-receive hooks in GIT?



#### 898. Do we have to store Scripts for GIT hooks within same repository?



#### 899. How can we determine the commit that is the source of a bug in GIT?



#### 900. How can we see differences between two commits in GIT?



#### 901. What are the different ways to identify a commit in GIT?



#### 902. When we run git branch <branchname>, how does GIT know the SHA-1 of the last commit?



#### 903. What are the different types of Tags you can create in GIT?



#### 904. How can we rename a remote repository?



#### 905. Some people use git checkout and some use git co for checkout. How is that possible?



#### 906. How can we see the last commit on each of our branch in GIT?



#### 907. Is origin a special branch in GIT?



#### 908. How can we configure GIT to not ask for password every time?



#### 909. What are the four major protocols used by GIT for data transfer?910.What is GIT protocol?



#### 911.  How can we work on a project where we do not have push access?



#### 912. What is git grep?



#### 913. How can your reorder commits in GIT?



#### 914. How will you split a commit into multiple commits?



#### 915. What is filter-branch in GIT?



#### 916. What are the three main trees maintained by GIT?



#### 917. What are the three main steps of working GIT?

GIT has following three main steps in a simple workflow:

1. Checkout the project from HEAD to Working Directory.
2. Stage the files from Working Directory to Index.
3. Commit the changes from Index to HEAD.


#### 918. What are ours and theirs merge options in GIT?

In GIT, we get two simple options for resolving merge conflicts: ours and theirs

These options tell the GIT which side to favor in merge conflicts.

In ours, we run a command like git merge -Xours branchA

As the name suggests, in ours, the changes in our branch are favored over the other branch during a merge conflict.


#### 919. How can we ignore merge conflicts due to Whitespace?



#### 920. What is git blame?



#### 921. What is a submodule in GIT?