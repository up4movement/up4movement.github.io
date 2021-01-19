## Important info

- Two branches are in play, the `master` branch that has the source code, and the `gh-pages` branch that has the build code
- They must be kept apart at all times

## Helpful link

https://medium.com/@stefanneculai/how-to-build-a-free-static-website-with-jekyll-and-github-pages-707e1cd5ffc3

- Stop at 'Use a custom domain'
- Don't use the pre-deploy script (causes bugs)

## Workflow (to develop on the site)

1. Create new branch off of master

- Use working_up4movement_master folder on computer
  (or pull from master on github and branch from that - this approach probably requires `git i` to setup node_modules)

2. Test all local changes by running development -> `jekyll serve` + look at localhost:4000

3. When happy, then save all files, commit and push branch to branch with same name on Github

4. Create pull request between that branch and Master (default)

- merge them

---- production build -----

NB: The `_site` folder continuously regenerates itself, doesn't require a `jekyll build` command, this actually creates bugs (don't use that command!)

5. `npm run deploy` (from the branch you finished working on) runs the script that deploys the `_site` folder to `gh-pages` branch, which is what the site is running on
   NB: Haven't had bugs with `npm run deploy`, but if there are, then the local master branch is working and I can pull from master (the latest changes) and run `npm run deploy` from there

1. For some reason, after every deploy to `gh-pages`, Github usually re-publishes the site to `up4movement.github.io`, so visiters to the site get 404 errors.

- Under 'settings' of the repo, scroll down to GitHub Pages and type in `up4movement.com` in the Custom domain field and click Save. The site is up again in 2 seconds.
