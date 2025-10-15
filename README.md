# iphone15_clone

# iPhone Website (React • Three.js • GSAP • Tailwind • Vite)

Interactive clone inspired by Apple's iPhone page with a 3D model, smooth GSAP animations, and a custom video carousel. Built with Vite for a fast dev experience.

## Tech Stack
- React 18, Vite
- Tailwind CSS
- Three.js, React Three Fiber, Drei
- GSAP (ScrollTrigger, animations)
- Sentry (optional monitoring)

## Features
- 3D iPhone model with realistic lighting and color variants
- Smooth, scroll-based animations using GSAP
- Custom video carousel with progress indicators
- Responsive UI

## Getting Started
1) Install
```bash
npm install
```

2) Run dev server
```bash
npm run dev
```
Open http://localhost:5173

3) Build and preview
```bash
npm run build
npm run preview
```

## Scripts
- `dev`: start Vite dev server
- `build`: production build to `dist`
- `preview`: preview the production build
- `lint`: run ESLint on js/jsx files

## Environment Variables (Optional: Sentry)
To enable error monitoring with Sentry, set a public DSN.

Create `.env` (or configure in your hosting provider):
```bash
VITE_SENTRY_DSN=your_public_sentry_dsn
```
Notes:
- The app initializes Sentry only if `VITE_SENTRY_DSN` is set and you are not on localhost (see `src/main.jsx`).
- Ensure your production domain is added to Allowed Domains in Sentry → Project → Client Keys (DSN), otherwise the browser may get 403 Forbidden on ingest.

## Project Structure (selected)
```text
src/
  components/        # UI sections (Hero, Highlights, VideoCarousel, etc.)
  utils/             # asset exports, animations
  constants/         # slides, models, links
  App.jsx            # main app component
  main.jsx           # entry point, Sentry init, React root
public/              # static assets (images/videos/models)
```

## Deployment
- Build with `npm run build` and deploy the `dist` folder to any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages, etc.).
- If using Sentry, set `VITE_SENTRY_DSN` in your host’s env and redeploy.

## Troubleshooting
- Sentry 403 (Forbidden) after hosting:
  - Add your site domain in Sentry → Project Settings → Client Keys (DSN) → Allowed Domains, and verify the DSN is correct.
  - Or unset `VITE_SENTRY_DSN` to disable Sentry.
- Videos not playing on mobile: ensure videos are muted and `playsInline` is set (already handled in `VideoCarousel.jsx`).

## License
This project is for educational/demo purposes and not affiliated with Apple.
