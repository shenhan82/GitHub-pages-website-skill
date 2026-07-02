# GitHub Pages Website Skill

This repository shares a reusable Skill for publishing simple static websites with GitHub Pages.

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

