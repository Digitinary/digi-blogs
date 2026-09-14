---
title: 'Testing the Digitinary Markdown Blog'
author: 'Malek Shehadeh'
date: '2026-09-14'
excerpt: 'A complete test article for validating Markdown rendering, navigation, formatting, and reading time on the Digitinary website.'
coverImage: 'https://editing.services/img/blog/post/postbg97550.webp'
tags:
  - Testing
  - Markdown
  - Digitinary
subtitle: 'A practical example covering the supported Markdown elements'
authorRole: 'Software Engineer'
authorBio: 'A member of the Digitinary team testing the GitHub-backed blog publishing workflow.'
featured: false
slug: 'digitinary-markdown-test'
---

This article is a test for the GitHub-backed Digitinary blog. It verifies that Markdown content is loaded, validated, sanitized, and displayed correctly on the website.

## Introduction

The blog reads this file directly from the public content repository. The title, author, date, excerpt, tags, and other information above come from the YAML front matter.

The expected article URL is:

[https://digitinary.com/blog/digitinary-markdown-test](https://digitinary.com/blog/digitinary-markdown-test)

## Text Formatting

This paragraph contains **bold text**, *italic text*, and ~~strikethrough text~~.

You can also include inline code such as `npm run build` or link to the [Digitinary website](https://digitinary.com).

> This is a blockquote. It can be used to highlight an important statement, customer quote, or key takeaway.

## Lists

### Unordered List

- Open Banking solutions
- API management platforms
- Business process automation
- Secure financial integrations

### Ordered List

1. Create the Markdown file.
2. Add valid front matter.
3. Review the article content.
4. Publish the file to the `main` branch.
5. Wait up to five minutes for the website cache to refresh.

### Task List

- [x] Add the required front matter
- [x] Add headings and paragraphs
- [x] Add a table and code example
- [ ] Replace the test content with the final article

## Table Example

| Feature | Status | Notes |
| --- | --- | --- |
| Front matter | Working | Provides the article metadata |
| Markdown body | Working | Provides the article content |
| Table of contents | Working | Uses level-two and level-three headings |
| Reading time | Automatic | Calculated at approximately 200 words per minute |

## Code Example

The following fenced code block verifies code rendering. Its contents are excluded from the reading-time calculation.

```typescript
interface BlogPost {
  title: string;
  author: string;
  date: string;
  excerpt: string;
  tags: string[];
}

function publishPost(post: BlogPost): string {
  return `${post.title} by ${post.author}`;
}
```

## Special Characters

The renderer should safely display characters such as `&`, `<`, `>`, quotation marks, and apostrophes without allowing unsafe scripts or event handlers.

### Duplicate Heading Test

This heading is included to test the generated table-of-contents anchor.

### Duplicate Heading Test

This second heading has the same text. The renderer should automatically generate a unique anchor so both entries work correctly.

## Final Checklist

When this article appears on the website, confirm the following:

- The title and excerpt appear in the blog listing.
- The author and date are displayed correctly.
- The URL ends with `/digitinary-markdown-test`.
- Level-two and level-three headings appear in the table of contents.
- The table, lists, blockquote, link, and code block render correctly.
- The reading time appears automatically.
- No broken cover image is displayed because `coverImage` is intentionally omitted.

## Conclusion

If every section above renders correctly, the Markdown publishing flow is working as expected. This test post can then be removed or replaced with production content.