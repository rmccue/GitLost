# Lesson 3: Hey Everyone, Look at What I Made!         (Or, Remotes and Pushing)

So, I've been working on the foobar project for a couple of weeks now, and it's
gone from being a simple one-file project to something I'm proud of. I'm finally
ready to release it out into the world.

I've decided that [GitHub][] is going to be the place I want to publish to, so
I've signed up there and created a repository there called "foobar".

	[GitHub]: http://github.com/

Now, I have to get my content from my computer to GitHub. But how do we do this?
Like this:

	$ git remote add origin git@github.com:rmccue/foobar.git
	$ git push origin master

Whoa, slow down cowboy! Let's walk through what just happened:

	$ git remote add origin git@github.com:rmccue/foobar.git

Git has a system of creating names for other repositories, called "remotes".
These refer to repositories set up just like yours.

{{{

If you've previously used a centralised version control system, like CVS or SVN,
this may be a bit weird to you. Unlike those, Git is a distributed VCS, meaning
that every copy is a full copy. While with CVS/SVN, you need to contact the
server to view logs, etc, every Git repository contains all the history.

}}}

So, we tell Git to call the repository at `git@github.com:rmccue/foobar.git` by
the name of `origin`.

{{{

The convention in git is to call your main remote by the name of "origin".

}}}

Remotes can be anywhere, and involve many different protocols. For example, you
can add a remote pointing to another repository on your computer if you want.

We then tell git to "pull" from our newly added remote. This says to git, "I
want to fetch the latest changes from the repository at origin, and then merge
them into my own code".

{{{

Where did this `master` come from?

`master` refers to a "branch" in the Git repository. For now, you don't really
need to know what it does, but we'll go into the topic of branches in depth in
a later lesson.

}}}

So, now that we know what this does, let's keep working for a bit. I've
committed some more stuff to my repository, and I want to send my new commits
to GitHub again.

	$ git push origin master

And I'm done! Simple.

{{{

It can be annoying to have to type "origin master" every time. You can set it up
to "track" automatically by doing:

	$ git branch --track master origin/master

}}}

Here ends lesson three: remotes refer to other repositories, and you can push
commits to them.