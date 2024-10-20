<h1 align="center">✨ Dev Diary</h1>
<p align="center">
  <i>A re-usable aggregated portfolio and blog site for developers</i><br>
  <b><a href="https://khulnasoft.com/">khulnasoft.com</a></b>
</p>
<p align="center">
  <a href="https://devdiary.netlify.app">
    <img width="700" src="https://raw.githubusercontent.com/khulnasoft-lab/devdiary/master/static/screenshot.png" />
  </a>
</p>


## Intro

This is my personal website. It's configurable, so feel free to use it, or any parts of it for yourself :)

**About**<br>
A self-hosted developer homepage, to showcase your projects, posts, coding stats, and more.<br>
Data is fetched from external sources (GitHub, RSS, social platforms...), so no need for a CMS.<br>
Crafted with SvelteKit + TypeScript- prioritising SEO, performance, accessibility, and compatibility.<br>

**Contents**
- [Intro](#intro)
  - [Pages](#pages)
  - [Tech](#tech)
- [Developing](#developing)
- [Deploying](#deploying)
  - [Manual Deploy](#manual-deploy)
  - [Quick Deploy](#quick-deploy)
  - [Docker Deploy](#docker-deploy)
- [Configuring](#configuring)
  - [Basic Data](#basic-data)
  - [Secrets](#secrets)
  - [Styles](#styles)
  - [Languages](#languages)
  - [More](#more)
- [Community](#community)
  - [Report an Issue](#report-an-issue)
  - [Contributing](#contributing)
  - [Support](#support)
  - [Credits](#credits)
    - [Sponsors](#sponsors)
    - [Contributors](#contributors)
    - [Stargazers](#stargazers)
- [Status](#status)
- [License](#license)

<sub>A tutorial, for how to build something similar is available on **[DEV.to](https://dev.to/khulnasoft-lab/sveltekit-10-build-an-blog-fetching-posts-from-your-dev-profile-29f)**</sub>

<sup>A mirror of this repository is available at **[codeberg.org/khulnasoft/devdiary](https://codeberg.org/khulnasoft/devdiary)**</sup>


### Pages

<details>
  <summary><b>Portfolio Page</b> - Displays projects from GitHub</summary>

The portfolio page displays the projects you've built. Data is fetched from your GitHub profile, with optional extra fields added in the config.

Each project can include: name, description, thumbnail, language, star/fork/issue count, license, size, date create/updated and links to the repo and project website. Featured projects can be made to span multiple cells, in order to display more info. When a thumbnail is present, the user can hover over the card to view full details. There's sorting and filtering options, useful if you've got a few hundred projects. Data is fetched dynamically from GitHub, but you can add or override any project data in the config file, as well as manually add more projects.

<p align="center">
  <img width="800" src="https://i.ibb.co/nmwLZTr/projects-page.gif" />
</p>

</details>

<details>
  <summary><b>Blog Page</b> - Displays articles from RSS</summary>

The blog page displays posts that you've published. Data is fetched and aggregated from one or more RSS feeds defined in the config. Post content is rendered as HTML, as well as metadata including author, date, link to original and optional thumbnail. The user can start typing to filter results, and use the keyboard to navigate posts.

<p align="center">
<img width="800" src="https://i.ibb.co/XVC9YZy/blog-page-gif.gif" />
</p>

</details>

<details>
  <summary><b>Contact Page</b> - Contact form, and social media summary</summary>
  
The contact page includes links to social profiles, a contact form, and space for GPG keys. Hover over the social media links, to show relevant user stats, like follower count, karma/ rep, join date and more. The contact form let's users write you a message, and include their name + mail address. Upon sending, the message will be emailed to you, using [EmailJS](https://emailjs.com). There's also space for including PGP key, and links to encrypted messenger apps.

<p align="center">
  <img width="400" src="https://i.ibb.co/xSvJRbZ/social-previews.gif" />
  <img width="600" src="https://i.ibb.co/Chm3LCD/Screenshot-from-2023-02-12-15-00-01.png?" />
</p>

</details>

<details>
  <summary><b>About Page</b> - Displays bio, work experience, tech stack</summary>

The about page has space for a short bio, profile image, work experience and tech stack.

<p align="center">
<img width="800" src="https://i.ibb.co/2MrSN7F/about-page.png" />
</p>


</details>

### Tech

<details>
  <summary><b>Quality Gates</b></summary>

✅ Localized with multi-language support<br>
✅ Unit tested<br>
✅ Fast load speeds<br>
✅ Server-side rendering for good SEO<br>
✅ Meets accessibility standards<br>
✅ Fully responsive<br>


</details>

<details>
  <summary><b>Tech Stack</b></summary>

Built with Svelte, using SvelteKit (1.0.0) and written in TypeScript.
The build system is Vite/ Rollup, with dependencies managed with PNPM.
Standards implemented with ESLint and Prettier, with testing done using Vitest and Playwright.
Styles are composed in SCSS with CSS variables for theming.
There's an optional Dockerfile with a Deno web server.

</details>

---

## Developing

```bash
# 1. Clone the repo and cd into it (update username if you've forked)
git clone git@github.com:khulnasoft-lab/devdiary.git && cd devdiary

# 2. Install dependencies
pnpm install

# 3. Start the development server
pnpm run dev -- --open
```

---

## Deploying

### Manual Deploy

- Fork the repo, then follow the steps above to clone and install dependencies
- Make any desired changes (see [Configuring](#configuring) below)
- Push changes to your repository
- Enable the build action, to deploy to a service of your choice

You can also build the site yourself `npm run build`, then either run `node build` to start the server, or use an appropriate [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

### Quick Deploy

Use the 1-click deploy to get up and running in seconds.

[![Depoly Devdiary to Netlify](https://img.shields.io/badge/Deploy-Netlify-%2330c8c9?style=for-the-badge&logo=netlify&labelColor=1e0e41 'Deploy Devdiary to Netlify, via 1-Click Script')](https://app.netlify.com/start/deploy?repository=https://github.com/khulnasoft-lab/devdiary 'Deploy Devdiary to Render, via 1-Click Script')

[![Depoly Devdiary to Render](https://img.shields.io/badge/Deploy-Render-%236c83fa?style=for-the-badge&logo=render&labelColor=1e0e41&logoColor=6c83fa)](https://render.com/deploy?repo=https://github.com/khulnasoft-lab/devdiary 'Deploy Devdiary to Render, via 1-Click Script')

[![Deploy Devdiary to Railway](https://img.shields.io/badge/Deploy-Railway-%23853bce?style=for-the-badge&logo=railway&labelColor=1e0e41&logoColor=853bce)](https://railway.app/new/template/hROvhb 'Deploy Devdiary to Railway, via 1-Click Script')

[![Deploy Devdiary to Vercel](https://img.shields.io/badge/Deploy-Vercel-%23ffffff?style=for-the-badge&logo=vercel&labelColor=1e0e41)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fkhulnasoft-lab%2Fdevdiary&env=GITHUB_TOKEN,TWITTER_TOKEN&project-name=devdiary&repository-name=devdiary_My-Developer-Portfolio 'Deploy Devdiary to Vercel, via 1-Click Script')

Once you've got a fork of the repository, you can make changes to the [`config.ts`](https://github.com/khulnasoft-lab/devdiary/blob/master/src/helpers/config.ts) (and any other files) to customize the site, and once commited, this will be reflected in your live version.

### Docker Deploy

There's a multi-arch [`Dockerfile`](https://github.com/khulnasoft-lab/devdiary/blob/master/Dockerfile) published on DockerHub under [`khulnasoft-lab/devdiary`](https://hub.docker.com/r/docker/khulnasoft-lab/devdiary) using [this workflow](https://github.com/khulnasoft-lab/devdiary/blob/master/.github/workflows/docker-build-publish.yml)

To run the container directly from DockerHub or GHCR, use: `docker run -p 3000:80 khulnasoft-lab/devdiary`

You'll likley want to make your own configuration file, use [`config.ts`](https://github.com/khulnasoft-lab/devdiary/blob/master/src/helpers/config.ts) as a template, and pass it to the container with `-v ./my-config.ts:/app/src/helpers/config.ts`. To rebuild the app, or run any other commands, use `docker exec -it [container-id] yarn build` (where container ID can be found with `docker ps`).

Alternatively, use the [`docker-compose.yml`](https://github.com/khulnasoft-lab/devdiary/blob/master/docker-compose.yml) as a template, and run `docker compose up`

[![Test on PWD](https://img.shields.io/badge/Try-Play_with_Docker-%232496ED?style=for-the-badge&logo=docker&labelColor=1e0e41)](https://labs.play-with-docker.com/?stack=https://raw.githubusercontent.com/khulnasoft-lab/devdiary/master/docker-compose.yml 'Deploy Devdiary to PWD, via 1-Click Script')

---

## Configuring

### Basic Data

All site data is located in [`config.ts`](https://github.com/khulnasoft-lab/devdiary/blob/master/src/helpers/config.ts). Here you can specify site name, URLs to RSS feeds, GitHub username to fetch projects from, contact details, etc.

### Secrets

Sensitive data, like API keys are set as environmental variables. These can either be set in the [`.env`](https://github.com/khulnasoft-lab/devdiary/blob/master/.env) file, or in the admin panel for your hosting provider (e.g. for Netlify: Site settings --> Environmental Variables)

Accepted Values

- `GITHUB_TOKEN` - A scoped API key for fetching repositories, and displaying social stats on the contact page. Optional, but you may experience rate limits if not specified
- `TWITTER_TOKEN` - Bearer token for showing follower count on the contact page.

### Styles

Style values are managed with CSS variables, for easy configuration. These values are defined in the SCSS files within [`styles/`](https://github.com/khulnasoft-lab/devdiary/tree/master/src/styles). For more advanced theming, you can edit the content of the `<style>` blocks within individual routes and components.

Variables are split into the following files:

- `color-palette.scss` - Colors
- `dimensions.scss` - Sizes
- `media-queries.scss` - Breakpoints
- `typography.scss` - Fonts

### Languages

The app is fully translatable, with all hard-coded copy located in [`locales`](#). The users language can be detected automatically based on browser/ OS preference, or manually set using the dropdown in the UI. To add a new language, simply create a new file named by your locale's ISO code, populate the contents (use `en` as a template), then import it in [`app`](#).

Currently, the following languages are supported:

- English (`en-GB`)

### More

If you'd like to configure anything else, then it should be pretty straight-forward by directly editing the specific routes or components. If you need any help with any of this, feel free to raise an issue :)

---

## Community

### Report an Issue

Found something that's not working? [Open an issue](https://github.com/khulnasoft-lab/devdiary/issues/new/choose), and describe the problem, steps to reproduce alond with expected and actual output. If relevant, also include details about your environment. I'll try and fix / respond to any tickets within 48-hours.

### Contributing

Contributions of any kind are very welcome, and would be much appreciated.
For Code of Conduct, see [Contributor Convent](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).

To get started, fork the repo, make your changes, add, commit and push the code, then come back here to open a pull request. If you're new to GitHub or open source, [this guide](https://www.freecodecamp.org/news/how-to-make-your-first-pull-request-on-github-3#let-s-make-our-first-pull-request-) or the [git docs](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) may help you get started, but feel free to reach out if you need any support.

[![Submit a PR](https://img.shields.io/badge/Submit_a_PR-GitHub-%23060606?style=for-the-badge&logo=github&logoColor=fff)](https://github.com/khulnasoft-lab/devdiary/compare)

### Support

[![Sponsor khulnasoft-lab on GitHub](https://img.shields.io/badge/Sponsor_on_GitHub-khulnasoft-lab-%23ff4dda?style=for-the-badge&logo=githubsponsors&logoColor=ff4dda)](https://github.com/sponsors/khulnasoft-lab)

### Credits

#### Sponsors

<!-- readme: sponsors -start -->
<table>
</table>
<!-- readme: sponsors -end -->

#### Contributors

<!-- readme: contributors -start -->
<table>
<tr>
    <td align="center">
        <a href="https://github.com/liss-bot">
            <img src="https://avatars.githubusercontent.com/u/87835202?v=4" width="80;" alt="liss-bot"/>
            <br />
            <sub><b>Alicia Bot</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/FortiShield">
            <img src="https://avatars.githubusercontent.com/u/161459699?v=4" width="80;" alt="FortiShield"/>
            <br />
            <sub><b>Fortishield</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/gitworkflows">
            <img src="https://avatars.githubusercontent.com/u/118260833?v=4" width="80;" alt="gitworkflows"/>
            <br />
            <sub><b>Gitworkflows</b></sub>
        </a>
    </td></tr>
</table>
<!-- readme: contributors -end -->

#### Stargazers

[![Recent Star Gazers](https://reporoster.com/stars/dark/khulnasoft-lab/devdiary)](https://github.com/khulnasoft-lab/devdiary/stargazers)

---

## Status

[![🐳 Build + Publish Multi-Platform Image](https://github.com/khulnasoft-lab/devdiary/actions/workflows/docker-build-publish.yml/badge.svg)](https://github.com/khulnasoft-lab/devdiary/actions/workflows/docker-build-publish.yml) [![🏷️ Tag new Versions](https://github.com/khulnasoft-lab/devdiary/actions/workflows/tag-versions.yml/badge.svg)](https://github.com/khulnasoft-lab/devdiary/actions/workflows/tag-versions.yml) [![🪞 Mirror to Codeberg](https://github.com/khulnasoft-lab/devdiary/actions/workflows/sync-mirror.yml/badge.svg)](https://github.com/khulnasoft-lab/devdiary/actions/workflows/sync-mirror.yml) [![💓 Inserts Contributor & Sponsors](https://github.com/khulnasoft-lab/devdiary/actions/workflows/insert-contributors.yml/badge.svg)](https://github.com/khulnasoft-lab/devdiary/actions/workflows/insert-contributors.yml)

---

## License

> _**[khulnasoft-lab/Devdiary](https://github.com/khulnasoft-lab/devdiary)** is licensed under [MIT](https://gist.github.com/khulnasoft-lab/143d2ee01ccc5c052a17) © [Dev Diary](https://khulnasoft.com) 2022._<br> > <sup align="right">For information, see <a href="https://tldrlegal.com/license/mit-license">TLDR Legal > MIT</a></sup>

<details>
<summary>Expand License</summary>

```
The MIT License (MIT)
Copyright (c) Dev Diary <khulnasoft@omg.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sub-license, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished
to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included install
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANT ABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NON INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

</details>

---

<!-- License + Copyright -->
<p  align="center">
  <i>© <a href="https://khulnasoft.com">Dev Diary</a> 2023</i><br>
  <i>Licensed under <a href="https://gist.github.com/khulnasoft-lab/143d2ee01ccc5c052a17">MIT</a></i><br>
  <a href="https://github.com/khulnasoft-lab"><img src="https://i.ibb.co/4KtpYxb/octocat-clean-mini.png" /></a><br>
  <sup>Thanks for visiting :)</sup>
</p>

<!-- Dinosaur -->
<!--
                        . - ~ ~ ~ - .
      ..     _      .-~               ~-.
     //|     \ `..~                      `.
    || |      }  }              /       \  \
(\   \\ \~^..'                 |         }  \
 \`.-~  o      /       }       |        /    \
 (__          |       /        |       /      `.
  `- - ~ ~ -._|      /_ - ~ ~ ^|      /- _      `.
              |     /          |     /     ~-.     ~- _
              |_____|          |_____|         ~ - . _ _~_-_
-->
