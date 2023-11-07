---
title: "In 2 minutes: Sharing data with git subtree"
slug: in-2-minutes-sharing-data-with-git-subtree
date: 2022-06-22T16:27:00.000Z
date_updated: 2022-07-23T07:15:11.000Z
draft: true
excerpt: Git is of great use and provides version control to your research project, and makes collaboration easy. The often overlooked module git subtree allows you to publish a specific subfolder of your project, e.g. your data folder, to a separate GitHub repository.
---

While many data scientists are familiar with `git` and pushing your project into a repository, such as GitHub, we often overlook one useful feature of `git` : The subtree.

A subtree allows you to push a subdirectory of your project into another repository. This can be useful, e.g., if you want to share the data of your research project with colleagues, or make it open source. The advantage of a subtree is, that you can simply do this from the git repository already established for your research project. Hence, if your data changes in the future, or you add new data, you can update both repositories without going through the pain of having two git instances seeded within each other.

The graph below illustrates the project structure when there is a subtree: The whole project, including your subfolder (e.g., the data folder), goes into repository A. However, the subfolder *can* also be pushed into repo B.

To create such as subtree structure, we first need a git repository and link it to GitHub. In case you have not done that yet, see the code below.

    cd path/to/your/research_project
    
    git init
    git add *
    git commit -a -m 'Initial commit'
    git remote add origin git@github.com:great_researcher/repo.git  
    
    

Now, create a separate repository on GitHub, where your subfolder should live, here we will call it `sub_repo`.

Now, we can create the subtree. First, we create a folder with `git subtree add`. Everything in this folder is part of the subtree.

    git subtree add prefix=name_for_subfolder git@github.com:username/sub_repo.git branch
    

We planted a subtree! But how do we push things to the main repository and to the subtree repository now?

For our main repository, the procedure stays the same as before. The code below will push the changes to our main repository, including changes made to our subfolder.

    git add .
    git commit -m "great commit message"
    git push
    
    

To only push the subfolder to our `sub_repo`, we need to use the submodule `subtree` and specify the prefix (i.e., the subtree folder name), our subtree repository and the desired branch.

    git subtree push --prefix=name_for_subfolder git@github.com:username/sub_repo.git branch
    

> A subtree can be useful, if there is a specific subfolder in our project that we want to send to a separate remote repository. The version control of the main project remains intact, and we can even have the repository of our main project hosted in a private repository, while the subfolder can be published to a public repository. One example that comes to mind, is to root your data folder to a public GitHub repo, to make your data accessible to other researchers.