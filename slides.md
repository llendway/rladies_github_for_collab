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

<div class="tenor-gif-embed" data-postid="21632152" data-share-method="host" data-width="50%" data-aspect-ratio="1.0"><a href="https://tenor.com/view/im-no-expert-saturday-night-live-im-not-apro-im-not-an-expert-iam-not-that-expert-with-it-gif-21632152">Im No Expert Saturday Night Live GIF</a> from <a href="https://tenor.com/search/imnoexpert-gifs">Imnoexpert GIFs</a></div><script type="text/javascript" async src="https://tenor.com/embed.js"></script>

</center>

## But I want to learn!

* I want to share code with others so they can use it.  
* I want my code backed up somewhere other than on my computer.  
* I hate keeping track of different versions of code and other files.  
* I also hate the terminal so will try to avoid it at any cost.

Git/Github can help us with this! How many of you already use Github? 


## What we should already have set up


* Created an account on https://github.com/.
* Install and configure git - I have basic instructions here: https://github.com/llendway/github_for_collaboration/blob/master/github_for_collaboration.md#install--configure-git (I'll share this in the chat).  
* Set up a PAT (personal access token) - see the previous link.  
* In R Studio, install the following packages: usethis (for nice interactions with Git/Github) and gitcreds (if you haven't yet set up a PAT, there's some functions in here that help) ... I think that's it. I'm going to keep the R code REALLY simple.


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


## Branching







