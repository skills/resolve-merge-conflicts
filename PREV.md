# Managing merge conflicts

_Merge conflicts are a normal part of working in Git. Learn why they happen and how to resolve them with ease._

![](https://repository-images.githubusercontent.com/139188904/57722780-586d-11ea-8e74-8484f7ff7b43)

**Tags**: Git, Merge conflicts, GitHub

---

Merge conflicts happen when two people make changes to the same file on GitHub—a common occurrence when you’re working with other developers. While resolving differences might involve some discussion, merge conflicts don’t have to be scary. 

This course guides you through the steps to finding the best merge conflict solution, so your team can keep building. 

## What you'll learn

We'll answer common questions like:
- What is a merge conflict and what causes them?
- How do you resolve merge conflicts?
- How do you reduce merge conflicts?

And when you're done you'll be able to:
- Understand how merging happens and what causes merge conflicts
- Resolve simple and complex merge conflicts with ease
- Share best practices to reduce merge conflicts with your team

## What you'll build
![resume](https://user-images.githubusercontent.com/57373296/75482124-2c253080-5972-11ea-8384-cbf7dbec0992.png)

- Completed [source repository](https://github.com/githubtraining/merge-conflicts-demo)
- Completed [resume](https://githubtraining.github.io/merge-conflicts-demo/) deployed to GitHub Pages.

## Prerequisites
We recommend taking [Introduction to GitHub](https://lab.github.com/githubtraining/introduction-to-github) prior to this course. 

## Projects used
This makes use of the following open source projects. Consider exploring these repos and maybe even making contributions!
- [resume-template](https://github.com/jglovier/resume-template): A simple Jekyll + GitHub Pages powered resume template
- [Jekyll](https://github.com/jekyll/jekyll): a simple, blog-aware, static site generator.

## Audience

New developers, new GitHub users, users new to Git, students, managers, teams


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

{% if preferences.gitTool == 'cli' %}

1. Open your preferred command line interface, which we'll call your shell from now on.
1. Clone this repository:
      ```shell
     git clone {{ thePayload.repository.clone_url }}
      ```
1. Navigate to the repository in your shell:
      ```shell
      cd {{ thePayload.repository.name }}
      ```
1. Checkout to the `update-config` branch and ensure it is up to date:
    ```shell
    git checkout update-config
    git pull
    ```
1. Merge the `main` branch into the `update-config` branch. To ensure that you're working with an up to date copy of `main`, we'll use its remote tracking branch:
    ```shell
    git merge origin/main
    ```
1. In Git's response, you'll see the file with the conflict. Open it in your text editor.
1. Look for the marked hunks that begin with  `<<<<<<<  update-config` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
1. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
1. Next, remove the merge conflict markers by deleting the following lines:

       <<<<<<< update-config
       =======
        >>>>>>> main

1. Save and close the file. Stage and commit your changes:
    ```shell
    git add .
    git commit -m "merge main into update-config"
    ```
1. Push your merged branches to GitHub:
    ```shell
    git push
    ```

{% elsif preferences.gitTool == 'desktop' %}

1. First, make sure you have [GitHub Desktop](https://desktop.github.com/) installed and [configured](https://help.github.com/en/desktop/getting-started-with-github-desktop/authenticating-to-github). 
1. On the `code` tab of this repository, click the green **Clone or download** button. Click **Open in Desktop**. 
1. In GitHub Desktop, confirm the blue **Clone** button in the pop up window. 
1. Checkout to the `update-config` branch by clicking **Current branch**, and selecting `update-config`. 
1. Merge `main` into the `update-config` branch by clicking **Current branch**, and selecting **Choose a branch to merge into update-config**. 
1. Select the `main` branch, and click **Merge main into update-config**.
1. You'll be prompted about the merge conflict, and asked if you'd like to resolve it in your default editor. Click the button to open the file in your default editor. 
1. Look for the marked hunks that begin with  `<<<<<<<  update-config` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
1. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
1. Next, remove the merge conflict markers by deleting the following lines:

       <<<<<<< update-config
       =======
        >>>>>> main

1. Save and close the file.
1. Back in GitHub Desktop, click **Commit merge**.
1. Push your changes back to the remote by clicking **Push origin**.

{% else %}

1. At the bottom of the page in the "This branch has conflicts that must be resolved" section of the Pull Request, click the **Resolve conflicts** button.
2. Look for the highlighted sections that begins with  `<<<<<<<  update-config` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
3. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
4. Next, remove the merge conflict markers by deleting the following lines:

       <<<<<<< update-config
       =======
        >>>>>>> main

5. With the merge conflict markers removed, click **Mark as resolved**.
6. Finally, click **Commit merge**.

{% endif %}

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

{% if preferences.gitTool == 'cli' %}

1. Checkout to the `add-experience` branch and ensure it is up to date:
    ```shell
    git checkout add-experience
    git pull
    ```
1. Merge the `main` branch into the `add-experience` branch. To ensure that you're working with an up to date copy of `main`, we'll use its remote tracking branch:
    ```shell
    git merge origin/main
    ```
1. In Git's response, you'll see two files with conflicts: `_data/experience.yml` and `_data/interests.yml`.
1. Open `_data/experience.yml` in your text editor.
1. Remove the conflict markers and pick your desired content. 
1. With the merge conflicts resolved and the markers removed in the `_data/experience.yml` file, stage the file:
    ```shell
    git add _data/experience.yml
    ```
1. Open the next file in your text editor: `_data/interests.yml`.
1. Remove the conflict markers and pick your desired content. 
1.  Close the file. Stage it and commit your changes:
    ```shell
    git add _data/interests.yml
    git commit -m "merge main into add-experience"
    ```
11. Push your merged branches to GitHub:
    ```shell
    git push
    ```

{% elsif preferences.gitTool == 'desktop' %}

1. Checkout to the `add-experience` branch by clicking **Current branch**, and selecting `add-experience`. 
1. Merge `main` into the `add-experience` branch by clicking **Current branch**, and selecting **Choose a branch to merge into update-config**. 
1. Select the `main` branch, and click **Merge main into update-config**.
1. You'll be prompted about the merge conflict, and asked if you'd like to resolve it in your default editor. Click the button to open each file in your default editor. 
1. Remove the conflict markers and pick your desired content for each file. 
1. Save and close the files.
1. Back in GitHub Desktop, click **Commit merge**.
1. Push your changes back to the remote by clicking **Push origin**.
   
{% else %}

1. Click **Resolve conflicts**.
2. On the left, you will notice two files listed: `_data/experience.yml` and `_data/interests.yml`. Let's start with `_data/experience.yml`.
3. Remove the conflict markers and pick your desired content. 
4. With the merge conflicts resolved and the markers removed in the `_data/experience.yml` file, click **Mark as resolved**.
5. GitHub will present the next file with conflicts, `_data/interests.yml`.
6. Remove the conflict markers and pick your desired content. 
7. When you are finished, click **Mark as resolved**.
8. Click **Commit merge**.
   
{% endif %}

<hr>
<h3 align="center">Watch below for my response.</h3>



## Step 5: Create your own conflict

So far, this pull request doesn't have any conflicts. I have added some new branch protections to prevent you from merging before you're ready.

In the last activity, you solved a merge conflict that someone else created. This time, you'll create the merge conflict yourself.

### :keyboard: Activity: Make changes on this branch

{% if preferences.gitTool == 'cli' %}

1. Check out to this branch:
    ```shell
    git checkout add-education
    ```
1. Open `_data/education.yml` in your text editor.
1. Modify the content in the `degree:`, `uni:`, `year:`, and `summary:` lines.
1. Stage and commit the changes:
    ```shell
    git add _data/education.yml
    git commit -m "<YOUR-MESSAGE>"
    ```
1. Push your changes to GitHub:
    ```shell
    git push
    ```

{% elsif preferences.gitTool == 'desktop' %}

1. Checkout to the `add-education` branch.
1. Merge `main` into the `add-education` branch.
1. Open the `_data/education.yml` file in your default editor. 
1. Modify the content in the `degree:`, `uni:`, `year:`, and `summary:` lines.
1. Save and close the file.
2. Back in GitHub Desktop, see that your changes are staged for commit because the box next to the title is checked on the left side. 
1. Enter a short and descriptive commit message, and click **Commit to add-education**. 
3. Push your changes back to the remote by clicking **Push origin**.
   
{% else %}

1. Click on the **Files changed** tab in this pull request.
1. Click ![octicon-kebab-horizontal] in the top right-hand corner of the `_data/education.yml` file that had been previously modified.
1. Click **Edit file** to open the file editor.
1. Modify the content in the `degree:`, `uni:`, `year:`, and `summary:` lines.
1. Scroll to the bottom of the page and enter a commit message for your change.
1. Click the **Commit changes** button, making sure the "Commit directly to the **add-education** branch" option is selected.

{% endif %}

<hr>
<h3 align="center">Watch below for my response.</h3>

[octicon-kebab-horizontal]: https://unpkg.com/octicons/build/svg/kebab-horizontal.svg


Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



You did it, @{{ user.username }}! Nice job resolving the conflict. Most conflicts in your day to day experience should be pretty simple, as in that activity. You may need to discuss the resolution with your peers. If your team is working together and reviewing pull requests, resolving conflicts is easy.

### What just happened?

Resolving a conflict doesn't automatically merge the Pull Request in GitHub. Instead, it stores the resolution of the conflict in a merge commit and allows you and your team to keep working.

To resolve a conflict, GitHub performs what is known as a *reverse merge*. This means that the changes from the `main` branch were  merged into your `update-config` branch. 

With a reverse merge, only the `update-config` branch is updated. This allows you to test the resolved code on your branch before you merge it into `main`. The `main` branch should be treated as production ready, bug-free code.

## Step 2: Merge the first resolved pull request

Go ahead and merge this pull request now.

> I have already approved this pull request, so if you still see "Review required" in the merge view, try refreshing the page.
> 
### :keyboard: Activity: Merge this pull request

1. Click **Merge pull request** below.
1. Click **Confirm merge**.
1. Click **Delete branch** and get ready for your next activity.

{% if preferences.gitTool == 'cli' %}
You can also merge locally:
1. Checkout to the main branch:
    ```shell
    git checkout main
    ```
1. Ensure the main branch is up to date:
    ```shell
    git pull
    ```
1. Merge the `{{ branch }}` branch:
    ```shell
    git merge {{ branch }}
    ```
1. Enter a commit message, if asked.
1. Push your merged branches up to GitHub:
    ```shell
    git push
    ```
{% elsif preferences.gitTool == 'desktop' %}
You can also merge locally:
1. Checkout to the `main` branch by clicking **Current branch**, and selecting `main`.
1. Ensure the branch is up to date by clicking **Fetch origin**. 
2. Merge `{{ branch}} ` into the `main` branch by clicking **Current branch**, and selecting **Choose a branch to merge into main**. 
3. Select the `{{ branch }}` branch, and click **Merge {{ branch }} into main**.
4. Push your changes back to the remote by clicking **Push origin**.
{% endif %}

<hr>
<h3 align="center">Watch below for my response.</h3>



Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



Good job! You've solved your first merge conflict.

<hr>
<h3 align="center">Go to <a href="{{ url }}">the next pull request</a> now.</h3>


Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



## Step 4: Merge pull request

Great job, @{{ user.username }}, your pull request is free of conflicts. :tada:

### :keyboard: Activity: Merge this pull request

Go ahead and merge this pull request now.

1. Click **Merge pull request** below.
2. Click **Confirm Merge**.
3. Click **Delete branch**.

{% if preferences.gitTool == 'cli' %}
You can also merge locally:
1. Checkout to the main branch:
    ```shell
    git checkout main
    ```
1. Ensure the main branch is up to date:
    ```shell
    git pull
    ```
1. Merge the `{{ branch }}` branch:
    ```shell
    git merge {{ branch }}
    ```
1. Enter a commit message, if asked.
1. Push your merged branches up to GitHub:
    ```shell
    git push
    ```
{% elsif preferences.gitTool == 'desktop' %}
You can also merge locally:
1. Checkout to the `main` branch by clicking **Current branch**, and selecting `main`.
1. Ensure the branch is up to date by clicking **Fetch origin**. 
2. Merge `{{ branch}} ` into the `main` branch by clicking **Current branch**, and selecting **Choose a branch to merge into main**. 
3. Select the `{{ branch }}` branch, and click **Merge {{ branch }} into main**.
4. Push your changes back to the remote by clicking **Push origin**.
{% endif %}

<hr>
<h3 align="center">Watch below for my response.</h3>


Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



Good job! You've solved more merge conflicts.

<hr>
<h3 align="center">Go to <a href="{{ url }}">the next pull request</a> now.</h3>


Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



## Where do conflicts come from?

In a real world scenario, it's possible that a peer or colleague will have edited the same file in the same place as your pull request.

To demonstrate, I'll stand in as your colleague :wave:. In this other pull request {{ secondPR }}, you'll see that the education file has been changed. The other pull request was just merged to `main`, which means there's now a conflict in your pull request.

## Step 6: Resolve new conflicts

### :keyboard: Activity: Resolve the conflict

{% if preferences.gitTool == 'cli' %}
1. Make sure main is up to date by checking out to `main`, and typing `git pull`. 
1. Resolve the conflicts locally by checking out to the `add-education` branch, merging `main`, and repeating your previous steps.
{% elsif preferences.gitTool == 'desktop' %}
1. Get any new changes by clicking **Fetch origin**.
1. Resolve the conflicts locally by checking out to the `add-education` branch, merging `main`, and repeating your previous steps.
{% else %}
1. In the "This branch has conflicts that must be resolved" section of the pull request, click **Resolve conflicts**.
{% endif %}

Because you created the conflict, feel free to resolve this conflict as you wish.

<hr>
<h3 align="center">Return to this pull request for next steps.</h3>


Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



## Step 7: Merge the  pull request

Great job, @{{ user.username }}, your pull request is free of conflicts. :tada: Go ahead and merge this pull request now. 
 
### :keyboard: Activity: Merge this pull request


1. Click **Merge pull request** below.
2. Click **Confirm Merge**.
3. Click **Delete branch**.

{% if preferences.gitTool == 'cli' %}
You can also merge locally:
1. Checkout to the main branch:
    ```shell
    git checkout main
    ```
1. Ensure the main branch is up to date:
    ```shell
    git pull
    ```
1. Merge the `{{ branch }}` branch:
    ```shell
    git merge {{ branch }}
    ```
1. Enter a commit message, if asked.
1. Push your merged branches up to GitHub:
    ```shell
    git push
    ```
{% elsif preferences.gitTool == 'desktop' %}
You can also merge locally:
1. Checkout to the `main` branch.
2. Ensure the branch is up to date by clicking **Fetch origin**. 
3. Merge `{{ branch}} ` into the `main` branch by clicking **Current branch**, and selecting **Choose a branch to merge into main**. 
4. Select the `{{ branch }}` branch, and click **Merge {{ branch }} into main**.
5. Push your changes back to the remote by clicking **Push origin**.
{% endif %}

<hr>
<h3 align="center">Watch below for my response.</h3>



Uh oh @{{ user.username }}, something went wrong! I wasn't expecting this change. Please go over the instructions again and make sure you've followed them as exactly as you can.

If this is a pull request, you might close it so you can start fresh. Keep trying, you'll get there!

If you would like help troubleshooting, create a post on the [GitHub Community]({{ communityBoard }}) board. You might also want to search for your issue to see if other people have resolved it in the past.



## Nice work

![celebrate](https://octodex.github.com/images/benevocats.jpg)

Congratulations @{{ user.username }}, you've completed this course!

### What went well

Before I say good-bye, here's a recap of all the tasks you've accomplished in your repository:

- You learned why merge conflicts happen
- You resolved a simple merge conflict
- You resolved a multi-file merge conflict 
- You created a merge conflict, and resolved it!

### What's next?

Here are some instructions you can use to keep working on your resumé:

<details>
 <summary>Finishing the resume</summary>
 <hr>
 
  #### Finishing the resume
 
  To update the other sections of the resume, create a new branch and edit the files found in the `_data` folder.

  For example, to modify the "Projects" section, edit the `_data/projects.yml` file. After making your changes, create a new pull request and merge your changes.
 
 <hr>
</details>

<details>
 <summary>Changing the picture</summary>
 <hr>
 
  #### Changing the picture
 
  If you would like to change the image used on your resume, you need to make a few changes to the files.

 1. Create a new branch, maybe name it something like `new-avatar`.
 1. Navigate to the `images` directory and click the **Upload files** button.
 1. [Drag and drop your image](https://help.github.com/articles/adding-a-file-to-a-repository/).
 1. Commit your change by clicking **Commit changes**.
 1. On the `new-avatar` branch, open the `_layouts/resume.html` file and edit line 16. Replace `images/bob-avatar.jpg` with `images/YOURFILENAME`.
 1. Create a pull request.
 1. Merge the pull request, and delete the branch.
 
 <hr>
</details>

<details>
 <summary>Enabling GitHub Pages</summary>
 <hr>
 
  #### Enabling GitHub Pages
 
  When you are happy with your resume, you will need to publish it with GitHub Pages. This resume is ready for GitHub Pages, you just need to turn it on. Follow these steps to enable GitHub Pages when you are ready to publish your resume:

 1. Click on the [**Settings**]({{ repoUrl }}/settings) tab.
 1. Scroll to the "GitHub Pages" section.
 1. In the "Source" drop-down, select **main branch**.
 1. Click **Save**.
 1. :construction: Warning! :construction: Make sure you don't see any [errors after you select save](https://user-images.githubusercontent.com/13326548/36769372-bc9b43d4-1bf8-11e8-8050-2b08cf8d146b.png). If you do, your page won't build correctly and this step will be incomplete.
 
Your GitHub Pages resumé site will be live very shortly at [the proper URL](https://help.github.com/en/articles/user-organization-and-project-pages). 
 <hr>
</details>

### Keep Learning

Want to work on resolving merge conflicts using the command line? Check out [this documentation](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/).

Want to keep learning? Feel free to [check out our other courses]({{ host }}/courses)?

<hr>
<h3 align="center">I won't respond to this issue, go ahead and close it when finished!</h3>



Yay! You've done it! You've resolved all of the conflicts. I have a few pointers for completing your resume, so I've opened one last issue for that information.

<hr>
<h3 align="center">Check out the final issue <a href="{{ url }}">here</a>!</h3>

