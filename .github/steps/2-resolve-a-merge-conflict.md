## Step 2: Resolve a merge conflict

_Good start! Now let's look deeper at a merge conflict! :mag:_

This can be intimidating, but have no fear, Git is smart when it comes to merging! Git only needs a human to decide how to [resolve the conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line). Sometimes, the best way to resolve a merge conflict is to add content that's from both branches, or even something that isn't on either! This is why Git needs a human to look at the code and make the proper fixes.

### :keyboard: Activity: Resolve a merge conflict

1. Open the pull request that you just created, we created a conflict for you. Have no fear!
1. At the bottom of the page, under "This branch has conflicts that must be resolved", click the **Resolve conflicts** button.
1. Look for the highlighted sections that begins with `<<<<<<< my-resume` and ends with `>>>>>>> main`. These markers are added by Git to show you the content that is in conflict.
1. Remove the changes made on the main branch by deleting all of the content below the `=======` and above `>>>>>>> main`.
1. Next, remove the merge conflict markers by deleting the following lines:
   ```
   <<<<<<< my-resume
   =======
   >>>>>>> main
   ```
1. With the merge conflict markers removed, click **Mark as resolved**.
1. Finally, click **Commit merge**.
1. Now that the conflict is resolved, Mona should already be busy checking your work. Give her a moment and keep watch in the comments. You will see her respond with progress info and the next lesson.
