## A Bit About Git

[Git](https://git-scm.com/) is a [free and open source](https://git-scm.com/about/free-and-open-source) distributed version control system (VCS) designed to handle everything from small to very large projects with speed and efficiency.

A Version Control System (VCS) is a system that records changes to a file or set of files over time so that you can recall specific versions later.

If you are a graphic or web designer and want to keep every version of an image or layout (which you would most certainly want to), a Version Control System is a very wise thing to use. It allows you to revert files back to a previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more. Using a VCS also generally means that if you make a mess of your work or lose files, you can easily recover. In addition, you get all this for very little overhead.

Many people’s version-control method of choice is to copy files into another directory (perhaps a time-stamped directory, if they’re clever). This approach is very common because it is so simple, but it is also incredibly error prone. It is easy to forget which directory you’re in and accidentally write to the wrong file or copy over files you don’t mean to.

To deal with this issue, programmers long ago developed local VCSs that had a simple database that kept all the changes to files under revision control. In a Distributed Version Control Systems (DVCSs), such as Git, Mercurial, Bazaar or Darcs, clients don’t just check out the latest snapshot of the files: they fully mirror the repository. Thus if any server dies, and these systems were collaborating via it, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.

Furthermore, many of these systems deal pretty well with having several remote repositories they can work with, so you can collaborate with different groups of people in different ways simultaneously within the same project. This allows you to set up several types of workflows that aren’t possible in centralized systems, such as hierarchical models.

## Getting Started

Before you start using Git, you have to make it available on your computer. Even if it’s already installed, it’s probably a good idea to update to the latest version. You can either install it as a package or via another installer, or download the source code and compile it yourself.

---

NATHANIAL:

Please add section here:

1. we at SRC use GitHub as a Git front-end
3. to use GitHub, create an account
2. set up ssh keys to connect without always entering a password 


some useful resources

* https://modulesunraveled.com/very-basics-git/creating-account-github-and-setting-ssh-keys
* https://help.github.com/articles/generating-ssh-keys/
* https://help.github.com/articles/set-up-git/


---


### [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

#### Installing on Linux

If you want to install Git on Linux via a binary installer, you can generally do so through the basic package-management tool that comes with your distribution. If you’re on Fedora for example, you can use yum:

`$ sudo yum install git`
If you’re on a Debian-based distribution like Ubuntu, try apt-get:

`$ sudo apt-get install git`
For more options, there are instructions for installing on several different Unix flavors on the Git website, at http://git-scm.com/download/linux.

### Initializing a Git Folder

Create a git repo locally just by making a folder, `cd` into it and execute  `git init`.


Understand what commits and branches are and use them as necessary.

### Adding Content to a Git Folder / Staging Changes



### Committing Your Additions / Changes

http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History


To see a history of commits, run `git log`.

Explore `git log` flags.  For example, `-p` shows the diff introduced in each commit; `-2` limits the output to only the last two entries.

Sometimes it's easier to review changes on the word level rather than on the line level. There is a --word-diff option available in Git, that you can append to the git log -p command to get word diff instead of normal line by line diff. Word diff format is quite useless when applied to source code, but it comes in handy when applied to large text files, like books or your dissertation.


### Branches 

Good references for learning about branches are [the git-scm branching overview](http://git-scm.com/book/en/Git-Branching-What-a-Branch-Is) and [detailed discussion of branching and merging](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging). Use them. A half-hour read will help you save time and work more efficiently. To get the most out of the references, experiment.

There is a lot of over complicated stuff on the web about using this or that branching strategy, but think in simple terms:

There is a master branch which should be the main-line of development. It should aim to be stable at all times and its head is always the 'latest stable build'.

If there is a 'release', create a tag for it.

If there are release fixes or updates, branch from the tag (a tag is just a label for a commit).

Other than that, make branches for whatever is convenient. If you want branch history (e.g. to identify a set of commits as relating to each other) be sure not to fast forward back int master (use git merge --no-ff ...) so that the branch knowledge is retained. If that makes no sense to you, go back and read the above guides again ;)

Once production becomes live and changes less frequently, we might tag the production builds but with just one target website, this is generally overkill. The current commit on the production working copy is our tag - the only advantage of creating a named tag is that we can easily go back to that tagged state if necessary.

## GitHub Labels

| Label | Meaning |
|-------|---------|
| bug | |
| data | |
| duplicate | |
| enhancement | |
| help wanted | |
| high priority | |
| invalid | |
| low priority | |
| question | |
| urgent | |
| wontfix | |


## References:

* https://git-scm.com/about
* https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control


