




---

# Welcome to Managing Merge Conflicts :tada:

Hello, and welcome! If you're here to learn about and practice resolving merge conflicts, you're in the right place.

In this course, you'll learn why merge conflicts happen and solve a few of them. The merge conflicts in this course are simple enough to solve from GitHub.com. But, if you'd prefer, you can solve them using the command line or other local tools.

As an added bonus, the project we are using for this course is a resume hosted on [GitHub Pages](https://help.github.com/en/categories/github-pages-basics)! So, if you want to keep working after you complete this course, please feel free!

Before starting this course, we recommend completing the [Introduction to GitHub Learning Lab]({{ host }}/{{ course.Owner.login }}/introduction-to-github) first. 

> Note: You may notice that some branches and pull requests already exist. We'll be using them in later activities in this course.

### How merge conflicts happen

A **Merge conflict** occurs when changes are made to the same part of the same file on two different branches. You usually find out about conflicts in a pull request. 

This can be intimidating, but have no fear, Git knows how to handle this! It only needs a human to decide how to resolve the conflict.

## Step 1: Resolve a simple conflict

You may merge a lot of pull requests before you encounter your first merge conflict. That’s because Git is smart when it comes to merging. Unless you're paying close attention to other branches, you won't know about conflicts until you create a pull request.

This branch is a great example. In this scenario, two of our friends have been working in this repository. They both created branches, made changes to the `_config.yml` file, and opened pull requests. One pull request was merged to `main` without problems, but now the other pull request has a conflict.

The history of `main` and this branch look something like this:

![deviated branches](https://user-images.githubusercontent.com/13326548/36703493-b8f4d5ee-1b10-11e8-9f95-4ec9993fe704.png)

Because this pull request changes the same lines in the `_config.yml` file, there is a merge conflict. 

Let's help our friends resolve this conflict.

### :keyboard: Activity: Resolving your first merge conflict

1. At the bottom of the page in the "This branch has conflicts that must be resolved" section of the Pull Request, click the **Resolve conflicts** button.
2. Look for the highlighted sections that begins with  `<<<<<<<  update-config` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
3. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
4. Next, remove the merge conflict markers by deleting the following lines:

       <<<<<<< update-config
       =======
        >>>>>>> main

5. With the merge conflict markers removed, click **Mark as resolved**.
6. Finally, click **Commit merge**.

> Sometimes, the best way to resolve a merge conflict is to add content that's from both branches, or even something that isn't on either! This is why Git needs a human to look at the code and make the proper fixes.

<hr>
<h3 align="center">Watch below for my response.</h3>



## Conflicting change

This pull request adds changes to the `_data/education.yml` file. It's the same file that you just changed in your pull request.

After this pull request is merged, your pull request will have a merge conflict. That's because there will have been changes on two different branches to the same part of the same file.


## Step 3: Resolve more complex conflicts

Just like your first conflict, this pull request is already conflicted.

This time, however, I've made it a bit more complicated.

- Instead of one conflict, you get three!
- Instead of conflicts in one file only, you get two!  
- One of your files actually has some leftover merge conflict markers. This can happen if someone forgets to remove the markers while resolving a conflict.

### :keyboard: Activity: Resolve these conflicts

1. Click **Resolve conflicts**.
2. On the left, you will notice two files listed: `_data/experience.yml` and `_data/interests.yml`. Let's start with `_data/experience.yml`.
3. Remove the conflict markers and pick your desired content. 
4. With the merge conflicts resolved and the markers removed in the `_data/experience.yml` file, click **Mark as resolved**.
5. GitHub will present the next file with conflicts, `_data/interests.yml`.
6. Remove the conflict markers and pick your desired content. 
7. When you are finished, click **Mark as resolved**.
8. Click **Commit merge**.
   




## Step 5: Create your own conflict

So far, this pull request doesn't have any conflicts. I have added some new branch protections to prevent you from merging before you're ready.

In the last activity, you solved a merge conflict that someone else created. This time, you'll create the merge conflict yourself.

### :keyboard: Activity: Make changes on this branch

1. Click on the **Files changed** tab in this pull request.
1. Click ![octicon-kebab-horizontal] in the top right-hand corner of the `_data/education.yml` file that had been previously modified.
1. Click **Edit file** to open the file editor.
1. Modify the content in the `degree:`, `uni:`, `year:`, and `summary:` lines.
1. Scroll to the bottom of the page and enter a commit message for your change.
1. Click the **Commit changes** button, making sure the "Commit directly to the **add-education** branch" option is selected.





You did it, @{{ user.username }}! Nice job resolving the conflict. Most conflicts in your day to day experience should be pretty simple, as in that activity. You may need to discuss the resolution with your peers. If your team is working together and reviewing pull requests, resolving conflicts is easy.

### What just happened?

Resolving a conflict doesn't automatically merge the Pull Request in GitHub. Instead, it stores the resolution of the conflict in a merge commit and allows you and your team to keep working.

To resolve a conflict, GitHub performs what is known as a *reverse merge*. This means that the changes from the `main` branch were  merged into your `update-config` branch. 

With a reverse merge, only the `update-config` branch is updated. This allows you to test the resolved code on your branch before you merge it into `main`. The `main` branch should be treated as production ready, bug-free code.







## Where do conflicts come from?

In a real world scenario, it's possible that a peer or colleague will have edited the same file in the same place as your pull request.

To demonstrate, I'll stand in as your colleague :wave:. In this other pull request {{ secondPR }}, you'll see that the education file has been changed. The other pull request was just merged to `main`, which means there's now a conflict in your pull request.


