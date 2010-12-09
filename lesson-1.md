# Lesson 1: Repositories are Easy to Make  (Or, New Repositories and Committing)

One of the things I love about Git is that everything is fast. *Really* fast.
Let's say I'm starting a new project called "foobar". Here's what I'd usually
do:

	$ mkdir foobar
	$ cd foobar
	$ vim somefile

And then I'd work on the file, save, etc until I was done.

But let's say I make a mistake while editing, and I don't notice this until
later. It's a big one too, I have to try and undo a whole bunch of changes
I made. I'll end up spending time working on that, when I could be working
on new stuff!

Now, here's how I start a new project using Git:

	$ mkdir foobar
	$ cd foobar
	$ git init
	$ vim somefile

{{{

We can actually compress this into two lines, since `git init` takes a
directory name as one of the parameters.

	$ git init foobar
	$ vim foobar/somefile

}}}

Looks pretty much the same, right? Except now, I do this when I save:

	$ git add somefile
	$ git commit -m 'Added something'
	$ vim somefile

{{{

`git add` is an interesting command, as it doesn't necessarily do what you think
it would, especially if you're coming from other version control systems. We'll
explore this a bit later, but suffice to say for now, it tells git that you want
to include the file in the commit.

}}}

So, what's the advantage of this? Let's say I make that same mistake again. But,
this time, I can simply go back to that previous change by doing:

	$ git reset <commit>


The <commit> bit is replaced by the unique identifier for that change, called 
the "hash" of the commit. It's essentially a 40 character long string.

{{{

The hash is really the unique ID of the *changeset*. Git stores each commit as a
list of changes (essentially, a diff between a commit and the previous one).

}}}

But wait a second, I can't remember what it was! Curse those git designers and
their decision to use long strings! If only there were a way to look it up...

Suddenly, my command line takes control and begins typing by itself:

	$ git log
	...
	commit 64e9d4953ca1261b3186a5d920abce05291ae3e8
	...
		Added something

Aha! I've found it! But that's such a long string, I can't be bothered typing it
out. But that's OK, because git lets me only put in the unique bit of it. So,
instead of typing that out, let's try...

	$ git reset 64e9d4

Aha, it worked!

{{{

In general, be careful using `git reset`. If you use certain parameters, you can
easily nuke your repository.

}}}

So, by simply doing `git init` when I made the directory, I've managed to save
nyself a lot of time (after working out how to reset), and I can now get back
to programming. Awesome!

Here ends lesson one: every time you start something, make a git repository for
it. You'll never know when you'll need it.