---
layout: post
title: "Beginner's Guide to Creating a Blog on GitHub"
date: 2026-08-10
---

*Understanding Git, GitHub, GitHub Pages, Markdown, and Jekyll*

## What is Git?

Git is a program that tracks changes to your files over time. Think of it like a "super undo button" combined with a history book — every time you save a set of changes (called a **commit**), Git remembers exactly what changed, when, and you can go back to any previous version.

**Example:** You write a blog post, then edit it three times. Git can show you all three versions and let you go back to any one of them.

## What is GitHub?

GitHub is a website that stores your Git projects online. Git is the tool, while GitHub is the place where you keep a copy of your project so others (or your future self) can access it from anywhere.

**Analogy:** Git is like Google Docs' "version history" feature. GitHub is like Google Drive — the place where the file actually lives online.

## What is a GitHub Repository?

A **repository** (or "repo") is just a project folder that Git is tracking, stored on GitHub. Your blog lives inside one repository — one folder containing all of your website's files (HTML, CSS, blog posts, images, etc.).

## What is GitHub Pages?

GitHub Pages is a free feature of GitHub that takes the files in your repository and turns them into a live website with a public web address (URL). No separate hosting company is needed because GitHub provides the hosting.

Example URL:https://yourusername.github.io/your-repo-name
## What is a Static Website?

A **static website** means the pages are plain files (HTML/CSS/JS) that do not need a server running a database or backend code. The browser simply downloads and displays them directly.

This is perfect for a blog because there is no complicated setup, and it is exactly the type of website that GitHub Pages supports.

## What do HTML, CSS, and JavaScript do?

| Technology | Job | Analogy |
|---|---|---|
| HTML | Structure/content of the page (text, headings, images, links) | The skeleton of a body |
| CSS | Styling — colors, fonts, layout, spacing | The skin, clothes, and makeup |
| JavaScript | Interactivity — things that respond to clicks, animations, etc. | The muscles/nervous system that make it move |

For a simple blog, you will use HTML and CSS a lot, and JavaScript very little (maybe not at all at first).

## What is Markdown?

Markdown is a super simple way to write formatted text using plain symbols instead of complicated HTML tags.

Example:
Markdown is what you will use to write your actual blog posts — much easier than writing HTML for every post.

## What is a Blog Post in This Context?

Technically, a blog post here is just a Markdown file (`.md`) containing your article's text, with a little bit of information at the top (called **front matter**) such as the title and date.

A tool automatically turns it into a nice web page.

## What is Jekyll?

Jekyll is a free tool that works with GitHub Pages. You write blog posts in simple Markdown, and Jekyll automatically converts them into styled HTML pages, builds your blog listing page, and handles a lot of the repetitive work for you.

**Analogy:** Instead of hand-building every single web page yourself, Jekyll is like a template machine — you feed it your article, and it produces the finished page using a consistent design.

## My Recommendation

Here is a quick comparison of the main approaches:

| Approach | Beginner-friendly? | Markdown support? | Maintenance effort |
|---|---|---|---|
| Plain HTML/CSS | Medium (write every page by hand) | No (hand-code each post) | High — repetitive |
| Jekyll + GitHub Pages | Yes — built in, no installs needed | Yes — native | Low — write Markdown, it builds the page |
| Other static blog themes (Hugo, Gatsby, etc.) | Low (extra tools, more setup) | Yes | Medium–High |

### Conclusion

For a beginner who wants to create a personal blog using GitHub, **Jekyll + GitHub Pages** is a simple and practical starting point.

The basic workflow is:

**Write in Markdown → Commit with Git → Push to GitHub → GitHub Pages builds the website**

Once the basic blog is working, you can gradually learn HTML, CSS, Git, and Jekyll to customize the appearance and functionality of your website.