# learn-git
## What is git?
If you’re reading this, then obviously you’ve heard of Git, and obviously GitHub. The two are not the same thing. Git is a version control system, created by Linus Torvalds (also of Linux fame); GitHub is a website that acts as a hosting service for version control that uses git - usually for software code, but not exclusively. 

## Lets git going
First things first, you're going to need access to this repository on your local machine. A repository is where files are stored, in other words, what you're looking at right now. 
In order to copy this repository (also known as a repo), you will need to do the following:
1. Open up your terminal
2. Navigate to the folder that you want to copy the repo into
3. Enter the command `git clone https://github.com/laurahw/learn-git.git`

## Branching
When you work in Git, you work on branches. Each branch can contain a different version of the files, and can be merged. Using branches is especially helpful when working in teams as it can help prevent overlap of people working on the same thing. 
To create your first branch, in the terminal, enter:
` git checkout -b my-branch`
To explain this a little further:
`git checkout` moves you from whatever branch you are currently on
The `-b` tag indicates that you are creating a new branch, and the `my-branch` is the name of your branch.
If you wanted to move to an existing branch, you'd simply enter `git checkout existing-branch`, where `existing-branch` is the name of the branch you're trying to move to. 

## Making your first commit
Now that you have your own branch, let's get you to make some changes to a file and commit them. Committing is what happens when you are satisfied with your changes and want to save them on your branch. 
Using a text editor or IDE, open up the file `hello-world.html`.
You'll see I've already entered some basic HTML code. 
Add your name to the list of people by adding `<li> Your Name </li>` directly below the last `</li>`.
Save this in your text editor/IDE.
Return to your terminal, now we're going to commit. 
### Adding files
Sometimes, you may not want to add all the files you've changed to your commit, especially if some are still work in progress. 
To cherry pick which files you want to add, you need to type `git add <filename>`.
You can see a list of changed files by entering `git status`.
To add all changed files, `git add *`.
In this instance, you're going to enter `git add hello-world.html`

### Making a Commitment
Now you've added the files, you're ready to commit. 
When we commit files, we add a little message so anyone reviewing commits can see clearly what is contained in that commit. 
Different companies and teams have their own practices and guidelines for this, but to keep things as simple as possible, lets just go with a small message. 
In your terminal, type `git commit -m "Added <your name> to the list"`
The `-m` tag here indicates that what follows is the message, and the quote marks encapsulate your message. 

That's it, now you've committed your files!

## Push it
What happens next? You've made your changes, made your commit, now you want to get it onto the repo so your team or anyone else working on the same files can see your work. 
In the terminal, you'll need to enter `git push origin <branch-name>`. Whatever you called your branch initially, enter this in place of `<branch-name>`. The `origin` refers to the origin of the code, in other words, this repository. 

If you've forgotten what you called your branch, no worries, just type `git branch` into the terminal. This will show you a list of the local branches on your machine. The one with a star next to it is your current branch. 

One you push it, you should be able to come back to this page and see that a new commit to your branch has appeared.
You can continue making changes locally, and add, commit and push changes as this step and the previous have outlined. 

## Merging
Okay, so you've done your work and you're ready to have it added to the main branch. Usually, most development teams will have a `master` branch that holds all the code and files that are currently in production, and a `develop` branch that has all the files that are in a releasable state. 
When you feel your code/files are ready to be added to the main branches, you create what is called a pull request (and no, that's not something that happens in a nightclub).
You can do this from the terminal, but GitHub makes it super easy to review changes and approve them right here in your browser. 
At the top of the list of files, you should see a button labelled *New Pull Request*, click it. 
The *base* is the branch you want to merge your work into, the *compare* is the work you want to merge. Make sure these are correct. 
Since the code we have here is really simple, it should give you a *Ready to merge* notice. 
If there were clashes, for example if someone else had edited the same line of the same file as you, it would say *Unable to merge automatically*. This is what we call a *conflict*
