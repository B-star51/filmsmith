feat: Filmsmith — Complete AI movie recommendation engine with multi-step reasoning agent

Netflix-style film curator with an embedded multi-step reasoning agent (Claude / GitHub Models) 
for the Microsoft Agents League Hackathon — Creative Apps track.

FEATURES & PHASES:

Phase 1: Foundation & Core Agent
- React 18 + Vite, Tailwind CSS, HashRouter (GitHub Pages friendly)
- Onboarding quiz (mood / time / last-loved), personalised home feed
- Movie cards with hover-reveal (poster zoom, critic score, streaming badges)
- Multi-step local fallback reasoning engine (6-step chain) — always works without API keys
- Profile page, streaming badges (Netflix/Prime/Disney+), clickable links

Phase 2: Real Tool-Use Agent Loop & UX Polish
- Claude tool-use loop: filter_by_mood_and_time, check_user_history, score_candidates
  Tools execute locally; iterate until final JSON — browser-direct via Anthropic API
- Agent Thinking UI: Typewriter reasoning trace replaces spinner
- Filmsmith Score: Explainable composite (critic 40% + genre fit 35% + mood fit 25%)
  Colour-coded "% for you" badge; "Rate films to unlock" hint
- Convince Me: Per-card personalised 3-sentence pitch (Claude/GitHub or local fallback)
- Live Critic Feed: "Fresh From the Critics" for cinema releases via Claude web_search
  Cached 6h; LIVE badge; graceful fallback to bundled blurb
- Movie Details Modal: Trailers (YouTube embeds + search), "where to watch" links
- Post-watch feedback: Rating, verdict, next-mood

Phase 3: Data & Content
- Catalogue expansion: 30 → 50 → 77 films
  Parasite, Knives Out, The Matrix, Gladiator, Spirited Away, Avatar: Fire and Ash, etc.
- Streaming platforms: Netflix, Prime, Disney+, Hulu, HBO Max, Paramount+, Apple TV+
- In-cinema releases tracked separately for critic feed & badges

Phase 4: Presentation & Submission
- Architecture diagram (GitHub Copilot build lane + Claude runtime agent lane)
- Hero banner, logo, project structure SVG diagrams
- Polished README with tech stack, features, architecture
- PWA: Web manifest, icons, service worker (network-first + stale-while-revalidate)

Phase 5: Bug Fixes & Polish
- Fixed truncated Tailwind class (hover:bg-violet-soft)
- Updated Claude model name to match agent (claude-sonnet-4-20250514)

TECHNOLOGY:
- React 18 + Vite, Tailwind CSS, react-router-dom
- Claude API (claude-sonnet-4-20250514) + GitHub Models (openai/gpt-4o-mini)
- localStorage for profile + key persistence
- Hardcoded movie dataset (no external API)
- Fully responsive (mobile & desktop)

KEY ARCHITECTURE:
- Explicit 6-step reasoning chain returned to UI (transparent agent)
- Deterministic local fallback when no key/network
- Browser-direct API calls; keys stored in localStorage only
- Explainable Filmsmith Score with breakdown
- Graceful degradation for all features

COPILOT USAGE:
- Tool schemas, JSX boilerplate, Tailwind utilities drafted with Copilot
- Local fallback scoring heuristic
- Repetitive card layouts, badge maps, quiz arrays autocompleted

Co-Authored-By: Claude <noreply@anthropic.com>
Co-Authored-By: GitHub Copilot <198982749+Copilot@users.noreply.github.com>
