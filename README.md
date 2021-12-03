### **Github Notes**

- [Getting Started With New Project](#getting-started-with-new-project)
- [Getting Started With Existing Project](#getting-started-with-existing-project)

---

### Getting Started With New Project

1. Create a [new repository](https://github.com/new) and clone the repo. For example, for the [github_notes project](https://github.com/afrontendperson/github_notes), click the clone button for the SSH KEY (That's the current setup of authentication). It will provide the corresponding url git@github.com:afrontendperson/github_notes.git.
2. Now clone the repo locally to your repository. You will see it has all the content of the repository.

```bash
$ git clone git@github.com:afrontendperson/github_notes.git
$ cd github_notes
$ ls
LICENSE		README.md
# this opens the code on editor using VSCode
$ code .
```

3. Now we introduce the concept of adding files & committing them & pushing them.

```bash
$ git checkout -b my-change
$ git status
On branch my-change
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	sample.txt
# there's a couple flavors of commit. We go over them
# 1) this means we want to start tracking all changes done with this file
$ git add sample.txt
# 2) this means we add all untracked & tracked files
$ git add .
# 3) this means tracking any files that's already tracked (git status tells which file is tracked vs untracked)
$ git add -u
# this commit your changes. This is now recorded locally on your machine. 
$ git commit -m "this is a sample commit message"
# this pushes the code to github on a branch
$ git push origin -u my-change
# let's take a look at our current state. As you can see from (HEAD -> my-change, origin/my-change)
# your code is pushed to github!
$ git branch
  main
* my-change
$ git log
commit e6efd66ce08828f760a49b22b78fa2d569ff2fee (HEAD -> my-change, origin/my-change)
Author: guest1 <guest1@hwws.local>
Date:   Thu Dec 2 21:51:31 2021 -0800

    this is a commit message

commit 23cf4d03236b7231faf2dda34525818295a102cb (origin/main, origin/HEAD, main)
Author: afrontendperson <95462678+afrontendperson@users.noreply.github.com>
Date:   Thu Dec 2 21:27:45 2021 -0800

    Initial commit
```

4. Now create a PR (Pull Request) based on the review. This allows people to comment and give feedbacks. Go to the [github page](https://github.com/afrontendperson/github_notes). It will have a message talking about a pull request. Create it. You will have something like [this](https://github.com/afrontendperson/github_notes/pull/1). Clikc the Merge pull request button once you're ready.

5. Congratulation you have done your first commit. Make sure to delete the branch (click the Delete branch) button once you're done. This is the [commit](https://github.com/afrontendperson/github_notes/commit/ed179c49e273c1f731600928abd97d80cbc78778).

TLDR: The workflow takes you from writing code to tracking it (add, commit), to pushing it to a branch for individual development where every developer works on their own branch (push), to getting feedback on your proposed changes from other engineers (PR), and, lastly, to pushing your change to master where everyone can use it. 
In terms of time spent, most of your time will be adding and committing new changes locally until you feel you're comfortable with publishing your new feature/new fix. Then you push your code, and spend the second largest amount of time getting reviews (address them), and then merging with master.

### Getting Started With Existing Project

The below instructions are inspired by [Contributing to projects](https://docs.github.com/en/get-started/quickstart/contributing-to-projects). We go over contributing to existing projects.

1. Go to the repo you want to contribute to. For example, let's use [awesome react](https://github.com/enaqx/awesome-react) as the example. Go to [this link](https://github.com/enaqx/awesome-react) and the click the Fork button on the top right corner. If you can't find it, use CTRL+F and search 'Fork' on the browser.

2. Now it will lead you here `https://github.com/afrontendperson/awesome-react`. This is your own fork (your own alternate reality) of the repository.

3. Set up the repo on your computer
```
$ git clone git@github.com:afrontendperson/awesome-react
$ cd awesome-react
$ code .
```

4. Make some changes
```
$ touch sample.txt
$ echo "a small change, but don't push" > sample.txt
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	sample.txt

nothing added to commit but untracked files present (use "git add" to track)
hwws:awesome-react guest1$ git add .
hwws:awesome-react guest1$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   sample.txt

$ git add .
$ git commit -m "don't actually commit this"
[master 77315c3] don't actually commit this
 Committer: guest1 <guest1@hwws.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 sample.txt
$ git push origin master
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 347 bytes | 347.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:afrontendperson/awesome-react
   d65dde3..77315c3  master -> master
hwws:awesome-react guest1$ 

```

5. Go to your [forked repo](https://github.com/afrontendperson/awesome-react). Click `Contribute` then click the dropdown `Open pull request`. Get your review, make your changes, and push to master.






