---
title: "Using Git and Github with R Studio projects"
subtitle: "A journey with a non-expert"
author: "Lisa Lendway, PhD"
output: 
  ioslides_presentation:
    keep_md: true
    widescreen: true
    df_print: paged
---



## WARNING!!!

I am NOT a Git/Github expert!

<center>

<div class="tenor-gif-embed" data-postid="21632152" data-share-method="host" data-width="40%" data-aspect-ratio="1.0"><a href="https://tenor.com/view/im-no-expert-saturday-night-live-im-not-apro-im-not-an-expert-iam-not-that-expert-with-it-gif-21632152">Im No Expert Saturday Night Live GIF</a> from <a href="https://tenor.com/search/imnoexpert-gifs">Imnoexpert GIFs</a></div><script type="text/javascript" async src="https://tenor.com/embed.js"></script>

</center>

## But I want to learn!

* I want to share code with others so they can use it.  
* I want my code backed up somewhere other than on my computer.  
* I hate keeping track of different versions of code and other files.  
* I also hate the terminal so will try to avoid it at any cost.

Git/Github can help us with this! How many of you already use Github? 

## Why learn this from me?

* Git/Github were really intimidating to me at first - they still are!  
* I didn't feel like I had a place where I could try things out and make mistakes.  
* When things didn't work out the way they showed in online resources, I had no idea what to do!  

I hope to give you a comfortable format to try things and learn. Please, ask questions and interrupt when I do something too quickly or that you don't fully follow. There are no stupid questions!


## What we should already have set up

* Created an account on https://github.com/.
* Install and configure git - I have basic instructions here: https://github.com/llendway/github_for_collaboration/blob/master/github_for_collaboration.md#install--configure-git (I'll share this in the chat).  
* Set up a PAT (personal access token) - see the previous link.  
* In R Studio, install the following packages: usethis (for nice interactions with Git/Github), gitcreds (if you haven't yet set up a PAT, there's some functions in here that help), gert, credentials, and gh. I'm going to keep the R code REALLY simple.


## Review of the Git/Github with R Project basics 

For images and more detail, see: https://github.com/llendway/github_for_collaboration/blob/master/github_for_collaboration.md

1. Create repo on https://github.com/, checking the box to add a README and probably add a license (I usually choose MIT but do not trust me to explain any of the legality of this).  
2. Clone the repo to your computer: click the green code button and copy the link, in R Studio File --> New Project --> Version Control --> Git --> Paste link and put it in the desired location.  
3. Stage, Commit, and Push the .Rproj file.  
4. Add a new .Rmd file and stage, commit, and push that.

We will do these steps together!

## Adding a collaborator

Now, let's explore how we can work with others on a project by adding a collaborator.

1. On https://github.com/, go to your repository page for the repository you just created. 
2. Choose Settings (the gear-like icon).  
3. Go to Manage access. 
4. Search for your collaborator's Github account and choose Invite a collaborator.  
5. They will get an email and must accept your invitation to collaborate. 
6. Once accepted, they will have equal access to everything in the repository.  
7. They should clone the repo to their computer. Make sure the initial person creates the Rproj first, otherwise you can run into weird issues.

## Adding a collaborator

Let's do this together! Would someone volunteer to be my collaborator?

## Adding a collaborator

Once we have our collaborator(s), we'll add some steps to our usual process. 

* When we reopen the project, Pull in new work! (the turquoise down arrow on the Git tab).
* Communicate!!! Talk to your collaborators about what you're working on and when. You'll likely run into issues if you all are collaborating on the same file at the same time. 

Which brings us to ....

## Merge conflicts! Arg!

If you and a collaborator are working on a file at the same time, you'll likely run into a merge conflict at some point. This means you've tried to push out new work, but in the mean time a collaborator has already pushed out more new work that you hadn't pulled in. Sometimes Git can resolve them on its own but often it can't.

When that happens, you need to resolve it by editing the file where the merge conflict occurred. You can see details of how to do that here: https://github.com/llendway/github_for_collaboration/blob/master/github_for_collaboration.md#merge-conflicts

Let's create a merge conflict together!

## Branching

According to Github [documents](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches) (which I probably should read more of), "Branches allow you to develop features, fix bugs, or safely experiment with new ideas in a contained area of your repository." 

You can experiment in a branch and then later merge it with your "main" branch (or with another branch). 

This can be a safer way to collaborate with others.


## Branching

Let's add a branch (we'll do this together in a moment).

Click on the "branch" in the Git tab.  


![](images/branch.png){width="50%"}



## Branching

Give it a name and create. You'll see this after you do. 

![](images/branch_created.png){width="50%"}

You can also see the new branch on Github. Let's do these steps together.

## Branching

Now that we have a branch, let's use it. Make a change to a file in the new branch (we'll just use the README). Commit and push the changed file. On Github, you'll see a message like this:

![](images/branch_compare_pr.png){width="90%"}

If I'm collaborating, the collaborator can pull in changes to see the new branch. 

Let's do this together. Make a few commits and pushes.


## Branching - merging to main

Once we are satisfied with the work we did in our branch, we'll want to merge it back to the main branch. Go out to Github and click on the Compare & pull request button in the new branch. This is creating a pull request - asking someone (in this case yourself) to pull in the changes you're about to merge. Fill in the fields and click Create pull request.

![](images/branch_pr.png){width="50%"}

## Branching - merging to main

I could keep making changes, committing, and pushing. If I'm finished, and since I didn't make any difficult changes, it can be merged automatically - this won't always be the case.

![](images/branch_merge.png){width="90%"}

Click Merge pull request.

## Branching - merging to main w/ conflict

What if I (or my collaborator) made changes to the same file in the main branch, while I was making changes to it in the new branch? We'll have a merge conflict to resolve! Let's see those steps. First, we each make our changes and save, commit, and push.

<div class="columns-2">
![Change in new branch](images/1_change_in_new_branch.png){width="90%"}

![Change in main branch](images/2_change_in_main_branch.png){width="90%"}

</div>


## Branching - merging to main w/ conflict

In Github, click on the Compare & pull request button. This time, you'll see a screen like this - notice the red X message. Still click create pull request.

![](images/3_no_auto_merge.png){width="70%"}

## Branching - merging to main w/ conflict

On this screen, you can click the Resolve conflict button.

![](images/4_resolve_conflict.png){width="70%"}

## Branching - merging to main w/ conflict

An editor will open where you can make changes ... in this case, it's pretty easy to do it here, but I imagine this could get pretty complicated. I guess that's a good reason to do small steps in the branches so you don't run into those :)

![](images/5_conflict_editor.png){width="70%"}

## Branching - merging to main w/ conflict

Resolve the conflict and click Mark as resolved. Now you should be able to merge pull request as before and follow to the next steps as if you didn't have a merge conflict!

![](images/6_conflict_resolved.png){width="70%"}

## Branching - merging to main

Confirm that you really do want to merge the new branch with the main branch.

![](images/branch_confirm_merge.png){width="90%"}

## Branching - merging to main

If you don't need the branch anymore, you can delete it. 

![](images/branch_delete.png){width="90%"}

Then, go back to R Studio and pull in the changes, from the main branch.Note that it still shows up in R Studio so be careful you don't do work there (I can't figure out how to get rid of it).

## Pull requests (PRs)

Once you're comfortable using these tools on your own and with some trusted collaborators, you may want to start making suggestions to other people's code - maybe add a feature in your favorite package or even just suggesting a typo fix in some documentation. That's a pull request! 

We are going to use the instructions here: https://usethis.r-lib.org/articles/articles/pr-functions.html

And we're going to make pull requests to a PR practice repo I created: https://github.com/llendway/pr_practice

## Pull requests (PRs)

We will need to load the usethis library. You should also have the gert, credentials, and gh packages installed. (If anyone gets an error like this: "Error in validate_gh_pat(new_gh_pat(x)) : A GitHub PAT must consist of 40 hexadecimal digits", update the gh package or reinstall, see [this post](https://community.rstudio.com/t/usethis-use-github-error-in-validate-gh-pat/105737)).


```r
library(usethis)
```


## Pull requests - fork and clone

You are going to fork and clone the repo. Forking is putting it in your own Github repo and cloning it puts it on your computer. This function also sets the upstream remote to the original repo. This example uses my "other" GitHub account, which is pretty much a garbage account for me to practice with. 


```r
create_from_github("proflendway/test_pr")
```

You can change the default location, using `destdir` argument. If you are making a PR to your own repo, it won't fork it (since you already own it).

## Pull requests - fork and clone

After you run the code, you will see something like this, and I new RStudio window will open with this project open.

![](images/7_pr_fork.png){width="50%"}

## Pull requests - create branch

Next, we create a branch so changes we make take place outside of the main branch. In the `pr_init()` function, name your branch. Do this in the project that was just opened - you may need to reload the usethis library first.


```r
pr_init(branch = "expand_readme")
```

![](images/8_pr_branch.png){width="70%"}

## Pull requests - change, commit

It may take a second for the new branch to show up in RStudio. Make sure you are in that new branch (it says you are but double check). Make a small change, save, and commit the file.

![](images/8_pr_change_file.png){width="70%"}


## Pull requests - submit it!

Once you're finished making changes, use the `pr_push()` function (no arguments) to push out the changes to your copy of the repo on github. That will open a Github page and sets you up to make a PR!

<div class="columns-2">

![](images/9_pr_submit.png){width="95%"}

\
\
\


![](images/9_pr_makeit.png){width="95%"}

</div>

## Pull requests - message to maintainer

After creating the pull request, you can (and should!) write a message about the changes you are proposing.

![](images/9_pr_message.png){width="70%"}

## Pull requests - maintainer side

They could merge in Github, or [fancier things](https://usethis.r-lib.org/articles/articles/pr-functions.html#review-of-the-pull-request).

![](images/9_pr_maintainer.png){width="60%"}

## Pull request

Let's do it!

We're going to make pull requests to a PR practice repo I created: https://github.com/llendway/pr_practice

## Using the terminal ... queue scary music

I don't like the terminal, but sometimes I'm forced to use it. When I have to do that, my palms get sweaty, and I sometimes close my eyes and peak through my fingers after hitting return while I wait in fear to see what sort of mistake I might have made. I've learned a few Git commands that I feel comfortable enough to share.

There's a video of me doing these same things here: https://lisalendway.netlify.app/posts/2021-02-24-gitinrstudio/#i-use-the-terminal-and-come-out-alive

## Using the terminal

This first one doesn't actually require the terminal (yay!).

You save a file, but don't want those changes. You can right-click on the file in the Git tab and choose revert. You can also choose diff to see how it has changed from its last version. This will change the file back to the previous commit. So, if you've saved a lot and not committed, that could be a lot of changes.

## Using the terminal

You committed something you didn't actually want to commit. Or maybe you committed something that's too large to push to Github (that's usually my mistake). So, I need to "un-commit", which means heading to the terminal. In the terminal, run `git reset HEAD~1` which will bring back all the files you just committed as if they were never committed - you may need to refresh the Git pane. 

Then, you can make the changes you want, even deleting a file, and re-commit.

## Using the terminal

This time you committed and pushed. You may have made additional commits that you DO NOT CARE ABOUT. To revert to an old commit, use `git revert --no-commit <SHA>..HEAD` in the terminal, where `<SHA>` is the alpha numeric string that defines that commit. You can find the `<SHA>` in the history (the clock icon) in the Git tab.

## Using the terminal

This time you committed something, pushed it, and made more commits along the way.

We can go back to a previous commit and keep our new commits by using `git revert <SHA>` in the terminal. This will likely lead to a merge conflict (which you can resolve in RStudio) or put you in the VIM window (I don't even know what that means) where you should push `:q` as quickly as possible to escape.


## Resources

These slides: https://github.com/llendway/rladies_github_for_collab

My blog post, with video (thank you to my sister, Heather): https://lisalendway.netlify.app/posts/2021-02-24-gitinrstudio/

Happy Git with R by Jenny Bryan: https://happygitwithr.com/ - an amazing resource, especially after you're a little more comfortable with using Git and Github

The usethis Pull request helpers article: https://usethis.r-lib.org/articles/articles/pr-functions.html

Melanie Frazier's Guide, *GitHub: A beginner's guide to going back in time (aka fixing mistakes)*: https://ohi-science.org/news/github-going-back-in-time






