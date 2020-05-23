# sandbox_githubpage-nuxt

Test Deploying a Nuxt project on Github Page using the `nuxt.config.js`file, `gh-pages` package, and `push-dir` package.

Source: https://nuxtjs.org/faq/github-pages/

---

> The `nuxt.config.js` specifies the PublicPath project name. It must be located at the root of the project

> The `gh-pages` and `push-dir` are the official helper packages specially made to push to Github Page

### Steps to deploying Nuxt project on Github Page

1. Run `npm install gh-pages`
2. Create `nuxt.config.js` and configure it as follow:

```js
/* nuxt.config.js */
// only add `router.base = '/<repository-name>/'` if `DEPLOY_ENV` is `GH_PAGES`
const routerBase =
  process.env.DEPLOY_ENV === "GH_PAGES"
    ? {
        router: {
          base: "/sandbox_githubpage-nuxt/",
        },
      }
    : {};

export default {
  ...routerBase,
};
```

3. Ensure `package.json` contains the following:

```json
{
  "homepage": "http://<GITHUB_USERNAME>.github.io/<GITHUB_PROJECTNAME>",
  "script": {
    "build": "nuxt build",
    "build:gh-pages": "DEPLOY_ENV=GH_PAGES nuxt build",
    "generate": "nuxt generate",
    "generate:gh-pages": "DEPLOY_ENV=GH_PAGES nuxt generate",
    "deploy": "push-dir --dir=dist --branch=gh-pages --cleanup"
  }
}
```

4. Run `npn run build`

5. Push Repo to Github, **make sure nothing remains uncommit**

6. Run `npm install push-dir`
7. Run `npm run generate`
8. Run `npm run deploy`

DONE: The build version of the project should be accessible via Github Page URL of the repo

---
