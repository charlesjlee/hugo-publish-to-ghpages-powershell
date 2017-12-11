# hugo-publish-to-ghpages-powershell
This is a Powershell rewrite of the [bash script](https://gohugo.io/hosting-and-deployment/hosting-on-github/#deployment-from-your-gh-pages-branch) from the Hugo docs to deploy sites hosted on gh-pages. The script uses the `git worktree` feature to checkout gh-pages as /public so the generated code can be conveniently be committed.

## How to use
![example of using script to commit a change](/example.gif)
1. Setup your project structure so that Hugo code lives in the master branch and the genearated files live in the gh-pages branch. Details in the docs [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/#deployment-from-your-gh-pages-branch).
2. Put deploy at the root of the master branch.
3. Make changes to the master branch and test using `hugo server`.
4. Open Powershell, navigate to the master branch directory, and execute `deployHugo.ps1`. The script will abort if there are no changes to commit.
5. The script will ask for a commit message. This commit message will be used in both master and gh-pages