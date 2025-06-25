## Step 3: Create your own conflict

_Good job! You've solved a merge conflict! :tada:_

Resolving a conflict doesn't automatically merge the pull request in GitHub. Instead, it stores the resolution of the conflict in a merge commit and allows you and your team to keep working. To resolve a conflict, GitHub performs what is known as a _reverse merge_. This means that the changes from the `main` branch were merged into your `my-resume` branch. With a reverse merge, only the `my-resume` branch is updated. This allows you to test the resolved changes on your branch before you merge it into `main`.

Now, let's get a little evil. (It's for educational purposes!)

### :keyboard: Activity: Create your own conflict

We went ahead and added a new file called `references.md` and pushed that change to `main`, without updating your `my-resume` branch.

1. Browse and switch to the `my-resume` branch.
1. Click the `Add file` dropdown menu and then on `Create new file`.
1. Create a file named `references.md`.
1. Enter some text that conflicts with what we added for `references.md` in the `main` branch.
1. Click the **Commit changes** button at the top right of the editor. In the Commit message modal that appears:
    - Enter a commit message (e.g., Create references.md).
    - Make sure the "Commit directly to the `my-resume` branch" option is selected.
    - Click the green "Commit changes" button to finish.
1. Now that you've created a new conflict, Mona should already be busy checking your work. Give her a moment and keep watch in the comments. You will see her respond with progress info and the next lesson.
