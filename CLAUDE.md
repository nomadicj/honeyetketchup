# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands
- Start Jekyll locally: `docker-compose up`
- Stop Jekyll: `docker-compose down`
- Build site: `docker-compose run jekyll bundle exec jekyll build`
- Install dependencies: `docker-compose run jekyll bundle install`

## Testing
- Preview site locally: http://localhost:4000/
- Check for broken links: `docker-compose run jekyll bundle exec jekyll doctor`

## Code Style Guidelines
- Markdown: Use GitHub Flavored Markdown (GFM)
- YAML: 2-space indentation for _config.yml and front matter
- Front matter required for all posts and pages
- Post filenames: Use format `YYYY-MM-DD-title.md`
- Images should be stored in the `/images` directory
- Line endings: Unix-style (LF)
- Encoding: UTF-8
- Links: Use relative URLs for internal links
- Kramdown: Hard wraps are disabled, use explicit line breaks

## Repository Structure
- `_posts/`: Published posts
- `_drafts/`: Unpublished drafts
- `_layouts/`: Page templates
- `_includes/`: Reusable content
- `_sass/`: SCSS styles
- `images/`: Image assets