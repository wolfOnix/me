# wolfonix-me

Hello!

This project features:
- Vue (via Vite)
- GitHub Pages

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

## Configure GitHub Pages

- create a new **public** repo for the project - arbitrary name or `{{username}}.github.io`
- create a new Vue (or React, ...) project via Vite locally from the IntelliJ or via the npm commands in your favourite folder
- add the property `base: "/{{repo_name}}/"` or `base: "/"` to the `defineConfig` in the file `vite.config.js`
- commit and push local to GitHub
- now, GitHub pages runs static webpages and that means that we need to build the Vue project beforehand; and there are approximately two ways of doing that:
1. Via GitHub actions (this is the variant I tried)
- (no need to execute the build command (at least it would be for purposeless))
- in GitHub, go to the repo > Settings > Pages > Source: GitHub Actions > Press `create your own`
- a new page with an editor will be opened; erase the whole content and paste in the content from the [Vite documentation - Deploying a Static Site # GitHub Pages](https://vitejs.dev/guide/static-deploy.html#github-pages), section 2
- give the new file the name `deploy.yml` and commit it with any message (the file will be created at `.github/workflows/deploy.yml`)
- go back to the repo > Actions (on the same line with Pull Requests and Settings) > Deploy static content to Pages > Run workflow > Select the right branch (`master`, probably) > Run workflow; wait for the deploy to end
- if we now go back to repo > Settings > Pages, we should see `Your site is live at https://{{username}}.github.io/{{repo_name}}/` - this means the site is **_LIVE!_**
2. Via manual build (not really tried yet)
- the build has to be done locally by running the `npm run build` command
- a folder `dist` will be created and **only that** folder needs to be on the branch used by the GitHub pages; so it would be a really must-have to somehow create a separate branch where to have only that `dist` folder content
- so, in GitHub, go to the repo > Settings > Pages > Source: Deploy from a branch > Select the branch with the `dist` content
- and in this view, on the top of the page, the URL should appear if the page is live