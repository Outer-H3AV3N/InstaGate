
# Contributing to InstaGate

Welcome to the **InstaGate** development team!  
This document outlines how to contribute code, ideas, and improvements to the project.

> *“Start something — and help others do the same.”*

---

## 🧭 Overview
**InstaGate** is a social event-funding platform built on:
- React Native CLI (TypeScript)
- Node.js (Express)
- Stripe payments + OAuth integrations
- AWS / Cloud infrastructure (planned)
- OpenAI integration for creative flyer generation (planned)

This is a **private, invite-only repository**, so contributions are coordinated within the internal development team.

---

## 🛠️ Development Workflow

### 1. Clone & Setup
```bash
git clone https://github.com/<your-username>/instagate.git
cd instagate
pnpm install
pnpm run setup
```

Run the API locally:
```bash
cp apps/api/.env.example apps/api/.env
pnpm dev:api
```

Then run the mobile app:
```bash
cd apps/mobile
npx react-native start
npx react-native run-ios
```

> On iPhone testing, replace `127.0.0.1` with your Mac’s LAN IP in API calls.

---

## 🌿 Branching Strategy

We follow a simplified **Git Flow** model:

| Branch | Purpose |
|---------|----------|
| `main` | Stable production-ready builds |
| `dev` | Integration branch for next release |
| `feature/<name>` | New features or modules |
| `fix/<name>` | Bug fixes or hot patches |
| `docs/<name>` | Documentation or README updates |

Example:
```bash
git checkout -b feature/qr-checkin-sounds
```

When finished:
```bash
git push origin feature/qr-checkin-sounds
```

---

## 🧩 Commit Guidelines

**Format:**
```
<type>: <short summary>
```

**Examples:**
```
feat: add QR scanner to mobile app
fix: correct Stripe webhook signature handling
docs: update API endpoint examples in README
refactor: simplify event listing component
```

**Commit types:**
- `feat` — new features
- `fix` — bug fixes
- `docs` — documentation only
- `style` — UI or style-only changes
- `refactor` — code restructuring
- `perf` — performance improvements
- `test` — adding or fixing tests

---

## 🧪 Testing

Run all tests before submitting:
```bash
pnpm test
```

### Unit & Integration
- Backend: Jest + Supertest  
- Mobile: Jest + React Native Testing Library

> Add tests for every new API route or UI component where feasible.

---

## 💳 Environment & Secrets

Never commit credentials or `.env` files.  
Sensitive values include:
- `STRIPE_SECRET_KEY`
- `JWT_SECRET`
- `TICKET_SIGNING_SECRET`
- OAuth provider keys (Google, Apple, Microsoft, TikTok)

Use `.env.example` as your template for local setup.

---

## 🧠 Code Standards
- Use **TypeScript** everywhere.
- Prefer **functional components** with hooks in React Native.
- Maintain consistent formatting with Prettier.
- Avoid inline styles in favor of StyleSheet or Tailwind-like patterns.
- Keep API endpoints RESTful and version-ready (`/api/v1/...`).

---

## 📸 Assets & Branding

When adding new visual assets:
- Store under `/assets/` with descriptive filenames.
- Avoid embedding raw binaries (videos, PSDs) in the repo.
- Add references to `/docs/branding.md` when finalized.

> Logo and style guide are still under design — use placeholder assets for now.

---

## 🧾 Pull Requests

### PR Checklist
- [ ] Code builds and runs locally
- [ ] Tests pass (`pnpm test`)
- [ ] Lint checks pass (`pnpm lint` if configured)
- [ ] Documentation updated (if applicable)
- [ ] No credentials or personal data included

### Review Process
1. Create PR into `dev` branch.
2. Include short description and screenshots (if UI-related).
3. Request review from **@JasonHutchcraft**.
4. After approval, merge via **Squash and Merge**.

---

## 🧱 CI/CD

CI is configured via GitHub Actions:
- Lints & tests backend and mobile independently.
- Builds iOS project in Xcode simulator (macOS runners).
- Future: automated TestFlight deployment on `main`.

---

## 💬 Communication

Use GitHub Discussions or project Slack for coordination.

If you discover a bug, open an Issue using the **Bug Report** template.

---

## 🧭 Guiding Principles
1. **Build for real people.** Every feature should solve a problem for hosts or attendees.  
2. **Be pragmatic.** Simplicity beats cleverness.  
3. **Security by design.** Protect user trust and financial data.  
4. **Performance matters.** Faster UX = better retention.  
5. **Iterate quickly, launch boldly.**

---

## 👤 Author
**Jason Hutchcraft**  
Creator & Lead Architect — *InstaGate*  
© 2025 All Rights Reserved  

> *“Start Something.”*
