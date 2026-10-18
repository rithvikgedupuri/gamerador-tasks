# 🎮 Rithvik's Gaming Network — Games.fun & GameRadar

Welcome to my gaming development project! This repository documents how to build, deploy, and manage my gaming websites using GitHub Pages and a custom domain.

The project includes two websites:

1. **Games.fun** — A gaming portal and educational arcade.
2. **GameRadar** — A gaming discovery website featuring game search, recommendations, rankings, and community reviews.

---

## 📌 Project Overview

| Website   | GitHub Organization | Repository                  | Custom Domain                     |
| --------- | ------------------- | --------------------------- | --------------------------------- |
| Games.fun | `rithvikgedupuri`   | `rithvikgedupuri.github.io` | `games.fun.rithvikgedupuri.space` |
| GameRadar | `rithvikgedupuri`   | `coolboy`                   | `gameradar.rithvikgedupuri.space` |

**Root domain:** `rithvikgedupuri.space`

**GitHub organization:** `rithvikgedupuri`

**Default GitHub Pages hostname:** `rithvikgedupuri.github.io`

> **Important:** These are the intended website addresses. They are not confirmed live until GitHub Pages, DNS, and HTTPS have been tested.

---

# 🚀 Mission 1: Set Up the GitHub Organization

## Step 1: Create or open the organization

1. Visit [GitHub](https://github.com/).
2. Sign in to your GitHub account.
3. Open the organization named `rithvikgedupuri`.
4. Confirm that you have permission to create repositories and configure GitHub Pages.

## Step 2: Create the Games.fun repository

Create a repository with this exact name:

`rithvikgedupuri.github.io`

Recommended settings:

* Visibility: Public, if you want the source code to be publicly accessible.
* Initialize with a README file.
* Use `index.html` as the homepage.
* Enable GitHub Pages after adding the website files.

For an organization Pages site, the repository name must match the organization's GitHub Pages hostname.

## Step 3: Create the GameRadar repository

Create a second repository:

`coolboy`

Recommended settings:

* Visibility: Public, if you want the source code to be publicly accessible.
* Initialize with a README file.
* Add an `index.html` file containing the GameRadar website.
* Configure GitHub Pages separately from the Games.fun repository.

---

# 🌐 Mission 2: Purchase and Configure the Custom Domain

The root domain is:

`rithvikgedupuri.space`

The two intended website addresses are:

* `games.fun.rithvikgedupuri.space`
* `gameradar.rithvikgedupuri.space`

Manage DNS records through your domain registrar, such as GoDaddy, where the domain is registered.

## Step 1: Configure the root domain

Open your registrar's DNS management page for `rithvikgedupuri.space`.

Create the following four A records:

| Type | Host | Points to         | TTL     |
| ---- | ---- | ----------------- | ------- |
| A    | `@`  | `185.199.108.153` | Default |
| A    | `@`  | `185.199.109.153` | Default |
| A    | `@`  | `185.199.110.153` | Default |
| A    | `@`  | `185.199.111.153` | Default |

These are GitHub Pages IPv4 addresses for an apex/root domain.

Do not create multiple conflicting A records for the same host.

## Step 2: Configure the Games.fun subdomain

Create this CNAME record:

| Field           | Value                       |
| --------------- | --------------------------- |
| Type            | `CNAME`                     |
| Host/Name       | `games.fun`                 |
| Points to/Value | `rithvikgedupuri.github.io` |
| TTL             | Default or 1 hour           |

This should resolve to:

`games.fun.rithvikgedupuri.space`

## Step 3: Configure the GameRadar subdomain

Create this CNAME record:

| Field           | Value                       |
| --------------- | --------------------------- |
| Type            | `CNAME`                     |
| Host/Name       | `gameradar`                 |
| Points to/Value | `rithvikgedupuri.github.io` |
| TTL             | Default or 1 hour           |

This should resolve to:

`gameradar.rithvikgedupuri.space`

**DNS notes:**

* The host names above are relative to `rithvikgedupuri.space`.
* Do not enter the full domain in the Host field if your registrar automatically appends the root domain.
* A CNAME target should be the GitHub Pages hostname, not the name of an individual repository.
* A DNS record only directs traffic; it does not publish website files.
* Remove conflicting records for the same host if they prevent the intended configuration.
* DNS propagation can take up to 24 hours.

---

# ⚙️ Mission 3: Configure GitHub Pages for Games.fun

1. Open the `rithvikgedupuri.github.io` repository.

2. Select **Settings**.

3. Open **Pages** under the Code and automation section.

4. Under Build and deployment, select the appropriate publishing source.

5. If using a branch, select the branch containing `index.html` and the root folder.

6. Under Custom domain, enter:

   `games.fun.rithvikgedupuri.space`

7. Click **Save**.

8. Wait for GitHub to verify the DNS configuration.

9. Enable **Enforce HTTPS** once it becomes available.

The website should ultimately open at:

`https://games.fun.rithvikgedupuri.space`

Official documentation:

* [GitHub Pages](https://docs.github.com/en/pages)
* [Managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)

---

# ⚙️ Mission 4: Configure GitHub Pages for GameRadar

1. Open the `coolboy` repository in the `rithvikgedupuri` organization.

2. Select **Settings**.

3. Open **Pages**.

4. Configure the publishing source to use the branch and directory containing `index.html`.

5. Under Custom domain, enter:

   `gameradar.rithvikgedupuri.space`

6. Click **Save**.

7. Wait for DNS verification and certificate provisioning.

8. Enable **Enforce HTTPS** when available.

The intended website address is:

`https://gameradar.rithvikgedupuri.space`

Keep the custom domain configuration separate for each repository. One custom hostname should not be assigned to both Pages sites.

---

# 🎮 Mission 5: Build the Games.fun Educational Arcade

The Games.fun website can contain four browser-based games.

## Game 1: Clicker Mania

**File:** `clicker.html`

Features:

* Click a button to increase the score.
* Display the current score.
* Add a timer and high-score feature as future improvements.

## Game 2: Reflex Tester

**File:** `reaction.html`

Features:

* Start a reaction test.
* Wait for the target to turn green.
* Click the target as quickly as possible.
* Display the measured reaction time.
* Add a best-time tracker as a future improvement.

## Game 3: Math Attack

**File:** `math.html`

Features:

* Generate addition questions.
* Check submitted answers.
* Award experience points for correct answers.
* Expand the number range or add multiplication challenges.

## Game 4: Number Wizard

**File:** `guess.html`

Features:

* Generate a secret number between 1 and 50.
* Tell the player to guess higher or lower.
* Count attempts.
* Add a reset button and input validation as future improvements.

## Recommended repository structure

```text
rithvikgedupuri.github.io/
├── README.md
├── index.html
├── clicker.html
├── reaction.html
├── math.html
└── guess.html
```

The `index.html` file should contain the main arcade homepage with links to all four games.

---

# 📡 Mission 6: Build GameRadar

The GameRadar website is a gaming discovery and review portal.

## Planned features

### 1. Search the game database

Users can search by game title or genre.

Example games include:

* PUBG Mobile
* Minecraft
* Roblox
* EA Sports FC Mobile
* Among Us
* Fortnite
* Valorant
* Minecraft
* Elden Ring
* Rocket League
* Stardew Valley
* Genshin Impact
* Terraria
* Forza Horizon 5

The database can be expanded over time.

### 2. Game Finder Quiz

Users select a preferred genre, such as:

* Sandbox and Survival
* Open World and Adventure
* Action and Shooter
* Party and Multiplayer
* Mobile and Sports
* Horror and Survival
* Fighting and Arcade
* Racing and Sports

The recommendation logic should filter the game database and show matching games, rather than displaying only a generic message.

### 3. Top Five Games

Create a list of favorite games with a short explanation of why each one is worth playing.

The list should be updated as the project evolves.

### 4. Community Reviews

Users can submit a game title and review.

For a basic static website, reviews can be stored locally in the user's browser using `localStorage`.

For shared reviews visible to other visitors, integrate a backend database or review service.

**Security requirements:**

* Validate submitted fields.
* Display user-submitted text using safe DOM APIs such as `textContent`.
* Do not insert untrusted review content directly through `innerHTML`.
* Consider spam prevention and moderation if public submissions are enabled.

### 5. Community Voting

A voting link may be added to an external polling service.

Verify the poll URL before publishing it and ensure that the link opens the intended poll.

## Recommended GameRadar repository structure

```text
coolboy/
├── README.md
├── index.html
├── assets/
│   ├── images/
│   └── icons/
└── css/
```

For a simple static site, CSS and JavaScript can also remain inside `index.html`.

---

# 💾 Mission 7: Back Up and Maintain the Website

Before making significant changes:

1. Open the repository on GitHub.
2. Open the file you plan to edit.
3. Copy the existing code.
4. Save a local backup, for example `index_backup.txt`.
5. Make your changes.
6. Preview and test the website.
7. Commit the updated files.

A Git commit provides version history, so a separate local backup is useful but not the only recovery option.

Use descriptive commit messages, such as:

* `Add GameRadar homepage`
* `Create Math Attack game`
* `Add custom domain configuration`
* `Improve game search and reviews`

---

# 🧪 Mission 8: Test the Websites

After configuring GitHub Pages and DNS, test both website addresses.

## Games.fun checklist

* [ ] Repository `rithvikgedupuri.github.io` exists.
* [ ] `index.html` is present in the configured publishing directory.
* [ ] GitHub Pages deployment succeeds.
* [ ] Custom domain is configured.
* [ ] DNS resolves correctly.
* [ ] HTTPS works.
* [ ] All four game links open.
* [ ] Games work on desktop and mobile.

## GameRadar checklist

* [ ] Repository `coolboy` exists.
* [ ] `index.html` is present in the configured publishing directory.
* [ ] GitHub Pages deployment succeeds.
* [ ] Custom domain is configured.
* [ ] DNS resolves correctly.
* [ ] HTTPS works.
* [ ] Game search returns matching results.
* [ ] Genre recommendations display relevant games.
* [ ] Reviews validate user input.
* [ ] Review content is displayed safely.
* [ ] Mobile layout is usable.

---

# 🔒 Mission 9: Security and Maintenance

* Enable HTTPS for both websites.
* Keep the repository and DNS configuration documented.
* Do not store passwords, API secrets, or private credentials in public repositories.
* Validate all user-submitted content.
* Test website changes before announcing a release.
* Keep backups of important content.
* Check GitHub Pages deployment status after significant commits.
* Review third-party links before publishing them.

Remember that GitHub Pages is a static hosting service. Features requiring shared accounts, centralized review storage, private data, or server-side processing need an appropriate backend or external service.

---

# 🏆 Project Status

Use this section to track actual progress. Do not mark deployment tasks complete until they have been verified.

| Task                                        | Status    |
| ------------------------------------------- | --------- |
| GitHub organization configured              | To verify |
| Games.fun repository configured             | To verify |
| GameRadar repository configured             | To verify |
| Root domain DNS configured                  | To verify |
| Games.fun CNAME configured                  | To verify |
| GameRadar CNAME configured                  | To verify |
| Games.fun GitHub Pages deployment           | To verify |
| GameRadar GitHub Pages deployment           | To verify |
| HTTPS enabled on both websites              | To verify |
| Four educational games tested               | To verify |
| GameRadar search and recommendations tested | To verify |
| Community review handling tested            | To verify |

## 🎉 Final Goal

Build and maintain two independent gaming websites:

* **Games.fun:** `https://games.fun.rithvikgedupuri.space`
* **GameRadar:** `https://gameradar.rithvikgedupuri.space`

Both sites should have their own GitHub repositories, publishing settings, custom domains, and HTTPS configuration.

**Project owner:** Rithvik

**GitHub organization:** `rithvikgedupuri`

**Root domain:** `rithvikgedupuri.space`

Keep building, testing, and improving. 🚀🎮
