# sandbox_githubpage-nuxt

Test Deploying a Nuxt project on Github Page using the `vue.config.js` and `deploy.sh`. Both files must be created at the root of the project and configured according to source link below.

Source: https://cli.vuejs.org/guide/deployment.html#github-pages

---

> The `vue.config.js` specifies the PublicPath project name

> The `deploy.sh` contains the script command for deploying at the right Github Page URL

### Steps to deploying Vue project on Github Pages

1. Run `npm run build`
2. Create `vue.config.js` and `deploy.sh`
3. Follow the instruction found at: https://cli.vuejs.org/guide/deployment.html#github-pages
4. Add `"deploy": "bash deploy.sh"` as a new property of the "scripts" object
5. Run `npm run deploy`

---
