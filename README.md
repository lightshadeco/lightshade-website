# 光影織藝官網 (Lightshade Official Website)

Official website for 光影織藝 (Lightshade Co.) — professional curtain design and installation services.

## Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| [Next.js](https://nextjs.org/) | 15 | React framework (App Router) |
| [Tailwind CSS](https://tailwindcss.com/) | 4 | Utility-first CSS |
| [TypeScript](https://www.typescriptlang.org/) | 5 | Type safety |
| [ESLint](https://eslint.org/) | 9 | Linting |
| [Prettier](https://prettier.io/) | 3 | Code formatting |

## Getting Started

### Prerequisites

- Node.js 18.x or later
- npm 9.x or later

### Development

```bash
# Install dependencies
npm install

# Start development server (http://localhost:3000)
npm run dev
```

### Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run format       # Format code with Prettier
npm run format:check # Check formatting without writing
```

## Project Structure

```
src/
├── app/               # Next.js App Router pages and layouts
│   ├── globals.css    # Global styles (Tailwind entry)
│   ├── layout.tsx     # Root layout
│   └── page.tsx       # Home page
└── components/        # Reusable React components
public/                # Static assets
```

## Deployment

This project is configured for deployment on **Vercel**.

### Deploy to Vercel

The project is deployed on Vercel: **https://lightshade-website.vercel.app**

- Vercel project: `lightshadecos-projects/lightshade-website`
- Every push to `main` triggers a production deployment
- Pull requests get preview deployments automatically

To connect GitHub auto-deploy, visit the Vercel dashboard and link the `lightshadeco/lightshade-website` GitHub repo under project settings.

### Environment Variables

Copy `.env.example` to `.env.local` for local development (see file for required vars).

## Development Workflow

- `main` branch → production
- Feature branches → `feat/<feature-name>`
- PRs require review before merging to `main`
