---
title: "Git Cheat Sheet"
date: 2013-11-17
comments: true
sharing: true
footer: true
tags: [git, reference]
author: "Ramjee Ganti"
---

A few months back we migrated from [svn](http://svnbook.red-bean.com/) to [git](http://git-scm.com/book) at office. If there is one thing I regret in my work at [Justeat.in](http://justeat.in), it is why did I not move to git earlier. The move significantly reduced our time to resolve conflicts and release code to production. I will talk about my experiences with git in a different post. I have commited most used commands to memory. In here, I am documenting some of the other commands which I keep looking up once in a while.

<pre>
<code class="language-bash">
###bash Git Cheat Sheet
#List all local and remote branches
	git branch -a
#List all remote branches
	git  branch -r
#List all local branches
	git branch
#Delete local branches
	git branch -d &lt;branch name&gt;
#Checkout a remote branch and track it
	git checkout -b &lt;remote branch name&gt;
#Show the remote root
	git remote show
#Show the mapping between local and remote branches
	git remote show origin
#Set global value
	git config --global user.name "Ramjee Ganti"
	git config --global user.email &lt;email address&gt;
	git config --global core.mergetool meld
	git config --global core.difftool meld
	git config --global core.editor vim
	git config --global color.ui true
#Set project specific value
	git config user.name "Ramjee Ganti"
	git config user.email <email address>
#Set global alias
	git config --global alias.st status
#Set project specific alias
	git config alias.st status
#Show all git operations performed
	git reflog
#Revert to particular commit in past
	git reset --hard &lt;commit&gt;
#Revert changes to a staged file
	git checkout -- &lt;file name&gt;
#Commit without invoking pre commit hooks
	git commit --no-verify
#Push a branch to a remote server
	git push origin &lt;branch name&gt;
#Delete a branch from remote server
	git push --delete origin &lt;branch name&gt;
#Configure an upstream repository.(1)
	git remote add upstream git://upstream.url.here
	git fetch upstream
#Change the remote repository
	git remote set-url origin git://new.url.here
#Git Alias to list tags using along with tag
git config --global alias.tag-date "for-each-ref --sort='*authordate' --format='%(taggerdate) %(tag)' refs/tag"
</code>
</pre>
These are apart from the basic commands without which we cannot use git. For someone looking for a more coomprehensive git cheat sheet head [here](http://www.git-tower.com/blog/git-cheat-sheet-detail/)

(1): When a repository is cloned, it has a default remote called origin that points to your fork on remote repository, not the original repository it was forked from. To keep track of the original repository, you need to add another remote named upstream.
