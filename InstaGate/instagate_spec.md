# InstaGate — App Specification v1.0
**Slogan:** "Start Something."

---

## 1. Elevator Pitch
A social event-funding app that lets users host and share events (parties, concerts, contests, karaoke nights, etc.), collect small payments directly from attendees instead of traditional gifts, and issue digital confirmations (tickets, tokens, or badges) once payment is received. Users can log in via Google, Apple, or TikTok, upload event images and descriptions, set contribution levels, and receive funds directly to their connected account.

## 2. Users & Roles
Universal user model: anyone can host or attend. Hosts create events, set tiers, receive payments; guests discover events, pay, and get confirmations. Admins moderate ToS/AUP and manage abuse reports. Ratings/reviews drive reputation and incentives for good hosting/support.

## 3. User Journeys
1. Host creates Tesla meet → uploads photos → posts to “The Wall” → attendees pay → system issues badge/ticket → attendee reviews.
2. Attendee browses The Wall → finds flyer → pays → attends → reviews/rates host.
3. Business hosts open mic → sells tickets → attendees livestream & post → host recaps → reviews feed credibility.

## 4. Features
**MVP:** user onboarding; chat assistant for event flyer creation; payments; location-aware Wall and directions; confirmation badges/tickets.  
**Later:** livestreams, merch sales, sponsorships for high performers, artist-to-fan direct ticketing.

## 5. Data Model
- **User:** name, age, sex, gender, interests, hobbies, affiliation, school, etc.  
- **Event:** title, description, location, datetime, support level, badge/ticket, userId, media, social links.  
- **Payment:** service, bank/card/crypto references.  
- **Review:** blog/comment.

## 6. Authentication & Accounts
SSO (Google, Apple, TikTok, Microsoft). MFA + biometrics. Age 18+ for payments; 13–17 limited unless both parties KYC verified. KYC for payouts, aliases allowed for hosting.

## 7. Backend & Integrations
Node/Express API; AWS hosting (cost/perf TBD). Realtime chat/boards; OpenAI LLM integration; payments via Stripe + exploring JPMorgan/Venmo/Zelle/CashApp; email/SMS reminders; wallet for tickets/badges; DMs KYC-gated.

## 8. Device Features
Camera/mic (flyers, posts, livestream), push notifications, location (maps + heat-map popularity), background reminders, file import/export, Apple Wallet passes, QR/NFC/Bluetooth check-in (Pro), offline caching.

## 9. Security & Compliance
PCI tokenization only; KYC/AML; COPPA minor controls with KYC-gated DMs; moderation and admin audit trail; GDPR/CCPA; encryption via KMS/SSM; audit logs and retention; incident response playbooks.

## 10. Monetization
Platform fee per transaction; Pro hosts with increased reach; ads/sponsorships for top users; subscriptions/members-only events; product placements in livestreams; later merch & marketplace revenue.

## 11. Branding & UI
App name: **InstaGate**.  
Slogan: “Start Something.”  
Stylized alligator logo. Users are **Instigators**.  
Visual: cyberpunk + grunge, flyer-on-wall aesthetic. Chatbot-driven flyer creation UX with AI creative assistance.

## 12. Testing & Release
iOS first, Android next, web day 1. Milestones—Day30 device run, Day60 stable MVP, Day90 App Store submission, Day120 soft launch. Rollout: US → Canada → UK → others. GitHub CI/Xcode from start.

## 13. Operations
Three environments (dev/staging/prod). Secrets in GitHub + AWS SSM. Logging via Sentry + CloudWatch; metrics via Metabase; monitoring for fraud/abuse; automated deploys; PCI/KYC/AML enforced at API layer.
