# Sync-Test
Git sync testing project between GitHub and GitLab. 

## Goal

I want to use GitHub and GitLab concurrently, particularly for personal projects. I'm going to be experimenting with adding GitLab as a secondary URL in `origin`.

## Code

`git remote set-url ––add origin https://gitlab.com/user/repo.git`

This should be showing up on the GitLab... 

And it did!

## Permissions and Protection

When you make your first commit to both repositories at once, there will be no shared histories between the two and there will be differences in their pre-push state. You need to do `git push --force origin`, but that is disallowed on the master branch of GitLab repositories by default (called 'protection'). 

To __un-protect__ the branch, go to `Settings -> Repository -> Protected Branches` and __un-protect__ master. Do your `--force` push to sync the repositories, then re-protect the master branch to stick to best practices as well as possible.
