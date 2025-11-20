# Recipe Explorer (Frontend)

- Theme: Ocean Professional (primary #2563EB, secondary #F59E0B, error #EF4444, background #f9fafb, text #111827)
- Runs on port 3000 (Astro default configured in astro.config.mjs)
- No external services required. If PUBLIC_API_BASE is not set, local mock data at `public/data/recipes.json` is used.

Environment variables:
- PUBLIC_API_BASE: Optional. If set, API calls go to `${PUBLIC_API_BASE}/recipes` and `/recipes/:id`. If unset or errors occur, the app falls back to mock data.

Structure:
- src/layouts/MainLayout.astro: Base layout, header, theme.
- src/components/{Header,RecipeCard,SearchFilters}.astro
- src/pages/{index,search,bookmarks,recipe/[id]}.astro
- src/lib/{api.ts, storage.ts, types.ts}
- public/data/recipes.json

Bookmarking:
- Stored in localStorage under key `recipe-explorer.bookmarks`. No backend required.

Future integration:
- Replace endpoints in `src/lib/api.ts` as needed; keep the fallback to mock data to avoid hard dependencies.
