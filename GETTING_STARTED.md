# Getting Started with German Bureaucracy Helper

Willkommen zum German Bureaucracy Helper!

## Quick Links

- Live Demo: https://rintu-chowdory.github.io/devops-portfolio-ci-cd/
- Repository: https://github.com/Rintu-chowdory/devops-portfolio-ci-cd
- Project Summary: PROJECT_SUMMARY.md
- Deployment Guide: DEPLOYMENT_GUIDE.md
- App Documentation: BUREAUCRACY_HELPER_README.md

## Installation

```bash
# Clone repository
git clone https://github.com/Rintu-chowdory/devops-portfolio-ci-cd.git
cd devops-portfolio-ci-cd

# Install dependencies
pnpm install

# Start dev server
pnpm run dev
```

App available at: http://localhost:3000

## Commands

```bash
pnpm run dev              # Development server
GITHUB_PAGES=true pnpm run build  # Production build
pnpm run check            # TypeScript check
pnpm run format           # Format code
pnpm run test             # Run tests
```

## Deployment to GitHub Pages

1. Go to Repository Settings > Pages
2. Select "GitHub Actions" as source
3. Go to Actions tab and enable workflows
4. Push changes to main branch
5. Website available at: https://rintu-chowdory.github.io/devops-portfolio-ci-cd/

See DEPLOYMENT_GUIDE.md for detailed instructions.

## Features

- Checklisten Generator for bureaucratic processes
- Dokument Erklärer for complex German documents
- Fristen Manager for deadline tracking

## Technology

- React 19 + TypeScript
- Tailwind CSS 4 + shadcn/ui
- Vite + pnpm
- GitHub Actions + GitHub Pages

## Support

- Issues: Create an issue in the repository
- Documentation: See PROJECT_SUMMARY.md

---

Developed with love for expats, students, and new workers in Germany
