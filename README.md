<!--
  <<< Author notes: Header of the course >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses Creative Commons Attribution 4.0 International.
-->

<img src=https://repository-images.githubusercontent.com/139188904/57722780-586d-11ea-8e74-8484f7ff7b43 width=300 align=right>

# Resolving merge conflicts

_Merge conflicts are a normal part of working in Git. Learn why they happen and how to resolve them with ease._

<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

<details id=0 open>
<summary><strong>:golf: Start</strong></summary>

**To start this course: [<img width="150" alt="Use this template" src="https://user-images.githubusercontent.com/1221423/148581131-555c0fb8-5361-4450-a760-75fa6219a2fc.png">](https://github.com/githublearn/resolving-merge-conflicts/generate)**

> We recommend creating a public repository, as private repositories will [use Actions minutes](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).<br>
> After you make your own repository, wait about 20 seconds and refresh. I will go to the next step.

Merge conflicts happen when two people make changes to the same file on GitHub—a common occurrence when you’re working with others. While resolving differences might involve some discussion, merge conflicts don’t have to be scary. This course guides you through the steps to finding the best merge conflict solution, so your team can keep building.

- **Who is this for**: New developers, new GitHub users, users new to Git, students, managers, teams.
- **What you'll learn**: What merge conflicts are, how you resolve merge conflicts, how to reduce merge conflicts.
- **What you'll build**: We'll work with a short Markdown resume file in this course.
- **Prerequisites**: We recommend taking [Introduction to GitHub](https://lab.github.com/githubtraining/introduction-to-github) prior to this course.
- **How long**: This course is 3 steps and takes less than 30 minutes.

</details>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

<details id=1>
<summary><strong>:lotus_position: Step 1: Resolve a merge conflict</strong></summary>

### :wave: Welcome to "Managing Merge Conflicts"!

**What is a _merge conflict_**: A **Merge conflict** occurs when changes are made to the same part of the same file on two different branches. You usually find out about conflicts in a pull request.

This can be intimidating, but have no fear, Git is smart when it comes to merging! Git only needs a human to decide how to [resolve the conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line). Sometimes, the best way to resolve a merge conflict is to add content that's from both branches, or even something that isn't on either! This is why Git needs a human to look at the code and make the proper fixes.

### :keyboard: Activity: Resolve a merge conflict

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
1. Open the pull request we made for you, and we also made a conflict. Have no fear!
1. At the bottom of the page in the "This branch has conflicts that must be resolved" section of the pull request, click the **Resolve conflicts** button.
1. Look for the highlighted sections that begins with  `<<<<<<<  my-resume` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
1. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
1. Next, remove the merge conflict markers by deleting the following lines:
   ```
   <<<<<<< my-resume
   =======
   >>>>>>> main
   ```
1. With the merge conflict markers removed, click **Mark as resolved**.
1. Finally, click **Commit merge**.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the first step.
  Define terms and link to docs.github.com.
-->

<details id=2>
<summary><strong>:smiling_imp: Step 2: Create your own conflict</strong></summary>

### :tada: Good job! You've solved a merge conflict!

Resolving a conflict doesn't automatically merge the pull request in GitHub. Instead, it stores the resolution of the conflict in a merge commit and allows you and your team to keep working. To resolve a conflict, GitHub performs what is known as a *reverse merge*. This means that the changes from the `main` branch were  merged into your `my-resume` branch. With a reverse merge, only the `my-resume` branch is updated. This allows you to test the resolved code on your branch before you merge it into `main`. The `main` branch should be treated as production ready, bug-free code.

Now let's get a little evil. (Its for educational purposes!)

### :keyboard: Activity: Create your own conflict

We went ahead and pushed another change to `main` without updating your `my-resume` branch in the background.

1. Click on the **Files changed** tab in this pull request.
1. Click in the top right-hand corner of the `resume.md` file that had been previously modified.
1. Click **Edit file** to open the file editor.
1. Modify the contents of the last line.
1. Scroll to the bottom of the page and enter a commit message for your change.
1. Click the **Commit changes** button, making sure the "Commit directly to the `my-resume` branch" option is selected.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the first step.
  Define terms and link to docs.github.com.
-->

<details id=3>
<summary><strong>:shipit: Step 3: Merge your pull request</strong></summary>

### :heart: Almost there!

You can now [merge](https://docs.github.com/en/get-started/quickstart/github-glossary#merge) your pull request!

### :keyboard: Activity: Merge your pull request

1. First, resolve any remaining conflicts in your pull request.
   > Look back at step one if you need help.
1. Click **Merge pull request**.
1. Delete the branch `my-resume` (optional).
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Finish >>>
  Review what we learned, ask for feedback, provide next steps.
-->

<details id=X>
<summary><strong>:checkered_flag: Finish</strong></summary>

### Congratulations friend, you've completed this course!

<img src=https://octodex.github.com/images/benevocats.jpg alt=celebrate width=300 align=right>

Here's a recap of all the tasks you've accomplished in your repository:

- You learned why merge conflicts happen.
- You resolved a simple merge conflict.
- You created a merge conflict, and resolved it!

### What's next?

- Make your own Markdown resume site with GitHub Pages! Learn how in our [GitHub Pages](https://github.com/githublearn/github-pages) course.
- We'd love to hear what you thought of this course [in our community forum](https://github.community/c/education/github-learning-lab/34).
- [Take another GitHub Learn Course](https://github.com/githublearn).
- [Read the GitHub Getting Started docs](https://docs.github.com/en/get-started).
- To find projects to contribute to, check out [GitHub Explore](https://github.com/explore).

</details>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our community forum](https://github.community/c/education/github-learning-lab/34) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2022 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [CC-BY-4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode)
