# GitHub Pages Website Skill

This repository shares a reusable Skill for publishing simple static websites with GitHub Pages.

## For New GitHub Users

If GitHub is new to you, think of it as a place to store website files online. GitHub Pages is GitHub's free way to turn simple website files, such as `index.html`, `styles.css`, and images, into a public web page.

### 1. Create a GitHub account

1. Go to [github.com](https://github.com).
2. Click **Sign up**.
3. Use an email address you can access, because GitHub will ask you to verify it.
4. Choose a username that you are comfortable showing publicly.
5. Keep your password and recovery method somewhere safe.

### 2. Finish Basic Account Setup

After the account is created:

- verify your email address
- turn on two-factor authentication if GitHub asks for it
- sign in on the browser you plan to use for publishing
- create your first repository, usually public, for the website files

For a simple website, a repository is just the online folder where your web page files live.

### 3. Upload Your Website

For a small static site:

1. Put your homepage in a file named `index.html`.
2. Keep related files, such as `styles.css`, scripts, logos, and images, in the same folder or an `assets/` folder.
3. Upload those files into a GitHub repository.
4. Open the repository's **Settings**.
5. Go to **Pages**.
6. Choose the branch and folder that contain `index.html`, often `main` and `/root`.
7. Wait a few minutes, then open the public GitHub Pages link.

If that sounds too technical, ask your AI coding agent to use this Skill and guide you step by step.

## What This Is

`publishing-github-pages-sites` helps an AI coding agent guide or perform the full GitHub Pages publishing flow:

- check whether a site is truly static
- prepare or inspect a GitHub repository
- choose branch-based Pages or Actions-based Pages
- handle push authentication safely
- verify the live URL, content, CSS, and image assets
- explain custom domain, DNS, ICP, and mainland China limitations

## Install

Copy the folder below into your personal Skills directory:

```text
publishing-github-pages-sites/
  SKILL.md
```

For Codex:

```text
~/.agents/skills/publishing-github-pages-sites/SKILL.md
```

For Claude Code:

```text
~/.claude/skills/publishing-github-pages-sites/SKILL.md
```

## Use

Ask your AI coding agent:

```text
Please use the publishing-github-pages-sites Skill to publish this website to GitHub Pages and verify the live URL.
```

Chinese prompt:

```text
请使用 publishing-github-pages-sites 这个 Skill，帮我把这个网页发布到 GitHub Pages，并验证真实网址可以打开。
```

## Notes

GitHub Pages is a good route for static previews, personal pages, company holding pages, lightweight landing pages, and project demos.

If the website needs a backend, database, login system, payment system, or a mainland China ICP filing host, GitHub Pages is probably not the final production route.

## Safety

This Skill does not include private keys, tokens, account-specific settings, or private project files. Keep it that way when modifying or sharing it.
