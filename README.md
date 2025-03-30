# Alpha Bits blog

## Development Setup

**Recommended VSCode extensions:**

- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Astro](https://marketplace.visualstudio.com/items?itemName=astro-build.astro-vscode)

### Installation

1. Clone the repository:

```bash
git clone git@github.com:AlphaBitsCode/blog.git
```

2. Install dependencies:

```bash
pnpm install
```

3. Start development server:

```bash
pnpm dev
```

## Configuration

### Basic Settings

- Update `src/data/site.config.ts` for blog metadata
- Modify files in `/public` directory:
  - `favicon.svg` - Site icon
  - `robots.txt` - Update sitemap URL
  - `open-graph.png` - Social sharing image

### Content Management

1. **Categories**: Edit `src/data/categories.ts`

```ts
export const CATEGORIES = ['Technology', 'Programming', 'Web Development'] as const
```

2. **Posts**: Add Markdown/MDX files to `src/content/blog`
   - Filename becomes URL slug
   - Required frontmatter:
     - title
     - description
     - pubDate
     - heroImage
     - category

### Development Commands

| Command        | Description                    |
| -------------- | ------------------------------ |
| `pnpm dev`     | Start local development server |
| `pnpm build`   | Build production version       |
| `pnpm preview` | Preview production build       |
| `pnpm format`  | Format code with Prettier      |
| `pnpm lint`    | Run ESLint checks              |

## Content Authoring

### Draft Mode

Add `draft: true` to post frontmatter to hide from production:

```md
---
title: 'Working Draft'
draft: true
---
```

### Frontmatter Options

- **Required**:
  - title
  - description
  - pubDate
  - heroImage
  - category
- **Optional**:
  - tags
  - draft

Schema validation configured in `src/content/config.ts`
