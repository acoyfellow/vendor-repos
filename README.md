# vendor-repos

Simple script to clone vendor repos locally for IDE/agent reference. Repos are gitignored, so they won't bloat your git repository.

## Why?

Coding agents (like Cursor, Claude, etc.) can search your codebase to answer questions about libraries. By cloning the source code locally, agents can reference the actual implementation instead of guessing.

## Usage

```bash
# Clone/update all repos
./scripts/update-vendor-repos.sh all

# Or update individual repos
./scripts/update-vendor-repos.sh effect
./scripts/update-vendor-repos.sh svelte
./scripts/update-vendor-repos.sh kit
```

## Setup

1. Copy `update-vendor-repos.sh` to your project's `scripts/` directory
2. Make it executable: `chmod +x scripts/update-vendor-repos.sh`
3. Add to `.gitignore`:
   ```
   vendor/
   ```
4. Run the script to clone repos to `vendor/`

## What it does

- Clones repos to `vendor/{name}/` (gitignored)
- Updates existing repos if they already exist
- Uses `--depth 1` for faster clones
- Tracks `main` branch by default

## Customization

Edit the script to add/remove repos:

```bash
EFFECT_REPO="https://github.com/Effect-TS/effect"
SVELTE_REPO="https://github.com/sveltejs/svelte"
KIT_REPO="https://github.com/sveltejs/kit"
```

## License

MIT

