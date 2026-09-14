# Digitinary Blog Authoring Instructions for AI Agents


## Purpose

Create and maintain blog posts that can be read directly by the Digitinary website. Follow this
contract exactly. A malformed post is skipped by the website and will not be published.

## Repository Structure

```text
content/
└── 2026-09-14-example-post.md
media/
└── example-cover.webp
```

- Store every blog post directly inside `content/`.
- Store blog images and other media inside the root-level `media/` directory.
- Do not put posts inside nested directories.
- Only files ending in `.md` are treated as blog posts.
- Every valid Markdown file on the `main` branch is published. There is no draft or status field.
- Do not modify website source code from this repository.

## File Naming

Use this recommended format:

```text
YYYY-MM-DD-short-descriptive-title.md
```

Example:

```text
2026-09-14-open-banking-in-jordan.md
```

File names must:

- use lowercase English letters, numbers, and hyphens;
- contain no spaces, underscores, or special characters;
- end with `.md`;
- be unique within `content/`.

Always provide an explicit `slug` in frontmatter so the public URL remains clean and does not
include the date from the filename.

## Required Frontmatter

Every post must start at the first line with valid YAML frontmatter enclosed by `---`.

```yaml
---
title: 'A Clear and Descriptive Blog Title'
author: 'Author Full Name'
date: '2026-09-14'
excerpt: 'A concise summary of the article for cards, search results, and social previews.'
tags:
  - 'Open Banking'
  - 'Fintech'
slug: 'clear-descriptive-blog-slug'
---
```

The following fields are required:

| Field     | Rule                                                                      |
| --------- | ------------------------------------------------------------------------- |
| `title`   | A non-empty string.                                                       |
| `author`  | The real author name. Do not invent an author.                            |
| `date`    | A real calendar date in exact `YYYY-MM-DD` format.                        |
| `excerpt` | A short, non-empty summary suitable for a blog card.                      |
| `tags`    | A YAML list containing at least one non-empty tag.                        |
| `slug`    | Strongly required by this authoring guide; lowercase URL-safe kebab-case. |

The website technically allows `slug` to be omitted and then uses the filename, but agents must
include it to produce a predictable public URL.

Valid slug:

```text
open-banking-in-jordan
```

Invalid slugs:

```text
Open Banking
open_banking
open-banking!
/open-banking
```

The slug must match this pattern:

```regex
^[a-z0-9]+(?:-[a-z0-9]+)*$
```

Before creating a post, inspect the existing posts and make sure the slug is unique.

## Optional Frontmatter

```yaml
subtitle: 'An optional supporting subtitle'
authorRole: 'Software Engineer'
authorBio: 'A short, factual biography approved for public display.'
coverImage: '/blog-media/example-cover.webp'
featured: false
```

Rules for optional fields:

- `subtitle` falls back to `excerpt` when omitted.
- `authorRole` and `authorBio` must not be invented. Omit them if they were not provided.
- `featured` must be the YAML boolean `true` or `false`, not a quoted string.
- Only set `featured: true` when explicitly requested.
- `coverImage` can be a `/blog-media/...` path or an absolute `https://` image URL.
- Omit `coverImage` if no valid image was provided.

Do not add `readTime`. The website calculates reading time automatically from the Markdown body at
approximately 200 words per minute.

Fields such as `status`, `publishedAt`, `seoTitle`, and `seoDescription` are not part of the current
contract and are ignored by the website.

## Images and Media

Preferred workflow:

1. Add the media file under the root-level `media/` directory.
2. Reference it using `/blog-media/<filename>`.

Frontmatter example:

```yaml
coverImage: '/blog-media/open-banking-cover.webp'
```

Markdown example:

```markdown
![Open Banking architecture diagram](/blog-media/open-banking-architecture.webp)
```

For files in a media subdirectory:

```text
media/diagrams/payment-flow.webp
```

Use:

```markdown
![Payment flow diagram](/blog-media/diagrams/payment-flow.webp)
```

Media rules:

- Use descriptive lowercase filenames with hyphens.
- Provide meaningful image alt text.
- Prefer optimized WebP, PNG, JPEG, or SVG images.
- Do not reference a local media path unless the corresponding file exists.
- Absolute external image URLs must use HTTPS and come from an approved source.
- Do not embed secrets, private documents, tracking pixels, or unlicensed media.
- A media file must not exceed 25 MB.

## Markdown Body Rules

- Start the article body after the closing `---` line.
- Do not add an `# H1` heading in the body; the website already renders the frontmatter title as the
  page H1.
- Use `##` for main article sections and `###` for subsections.
- The table of contents is generated automatically from `##` and `###` headings.
- Use standard Markdown or GitHub Flavored Markdown for paragraphs, lists, tables, links,
  blockquotes, task lists, and fenced code blocks.
- Add a language name to fenced code blocks when known.
- Use descriptive link text instead of raw URLs when practical.
- Keep paragraphs reasonably short and make headings descriptive.
- Do not include scripts, iframes, forms, inline event handlers, or executable HTML.
- Raw HTML is not supported as article content and may be removed by the renderer.
- Do not copy copyrighted content or invent facts, quotations, statistics, people, roles, or company
  claims.

## Complete Post Template

```markdown
---
title: 'A Clear and Descriptive Blog Title'
author: 'Author Full Name'
date: '2026-09-14'
excerpt: 'A concise summary that explains what readers will learn from this article.'
tags:
  - 'Fintech'
  - 'Open Banking'
slug: 'clear-descriptive-blog-slug'
subtitle: 'Optional supporting subtitle'
authorRole: 'Optional verified role'
authorBio: 'Optional verified short biography.'
coverImage: '/blog-media/example-cover.webp'
featured: false
---

Opening paragraph introducing the topic and explaining why it matters.

## First Main Section

Write the section content here.

### Supporting Subsection

Add supporting details, examples, or evidence here.

## Key Takeaways

- First takeaway.
- Second takeaway.
- Third takeaway.

## Conclusion

Summarize the article and provide an appropriate next step.
```

Remove optional fields from the template when their values were not supplied. Never leave
placeholder text in a published post.

## Pre-Publish Validation Checklist

Before finishing any blog-authoring task, verify all of the following:

- [ ] The post is a `.md` file directly inside `content/`.
- [ ] The filename is lowercase, hyphenated, unique, and preferably date-prefixed.
- [ ] Frontmatter begins on line 1 and has matching `---` delimiters.
- [ ] `title`, `author`, `date`, `excerpt`, `tags`, and `slug` are present and valid.
- [ ] The date is a real date in exact `YYYY-MM-DD` format.
- [ ] The slug matches the required pattern and is not used by another post.
- [ ] At least one tag is present.
- [ ] Any author role, biography, claims, links, and dates are factual and verified.
- [ ] Referenced `/blog-media/...` files exist under the root-level `media/` directory.
- [ ] Every image has useful alt text.
- [ ] The body starts with prose or `##`, not a duplicate H1.
- [ ] There is no `readTime`, draft/status field, placeholder text, secret, or unsafe HTML.
- [ ] The Markdown file is below 512 KB.
- [ ] Existing unrelated posts and media were not changed.

## Publishing Behavior

After a valid post is merged or pushed to `main`:

- it appears in the website blog listing at `/blogs`;
- its detail page appears at `/blogs/<slug>`;
- its metadata and body are loaded from the same Markdown file;
- reading time is calculated automatically;
- changes may take up to approximately five minutes to appear because of website caching;
- no website rebuild is normally required.

An invalid post is skipped without preventing other valid posts from loading.

## Agent Operating Rules

- Read this file and inspect relevant existing posts before making changes.
- Change only the requested post and its required media unless the user explicitly expands scope.
- Preserve the author's meaning and tone when editing existing content.
- Ask for missing required factual information, especially the author identity or publication date.
- You may draft an excerpt and tags from supplied article content, but do not invent factual claims.
- Do not delete, rename, commit, merge, or push files unless the user explicitly requests that action.
- At completion, report the created or modified files, the final slug, the expected public URL, and
  any information that still requires human verification.
