# Scaling Enterprise Content Management for a Digital Healthcare Platform
<b>Role</b>: Development Lead, QA, Project Manager
<b>Collaborators</b>: UX Researcher, Product Designer, Engineering Manager, Product Owner, Chief Producter Officer (for project and budget approval)

---

## Background
Led the redesign of a healthcare resource hub serving over 10,000 pages of medical content. Led frontend architecture, routing logic, content modeling, and custom CMS workflows. Focused on improving information architecture, navigation, SEO, and content discoverability across treatment options, insurance offerings, and clinic details. 

---

## Tech Stack 
- Frontend: React.js, TypeScript, Tailwind CSS, Gatsby, Webpack
- Routing & Pages: React Router, Gatsby’s createPages API
- Backend: WordPress, Sanity, Postgres, GraphQL, Firestore
- State Management: Local, derived, and synced state via Redux
- Testing & Optimization: Jest, Cypress
- CI/CD: GitHub Actions, Netlify, Vercel
- Version Control: Git, GitHub

## Business Challenge  
The existing site struggled with poor content organization, duplicate URLs, and inefficient metadata—hindering SEO, user navigation, and scalability. Manual management of 10,000+ pages led to content drift and a fragmented user experience.

### Key issues:
 - Poor content discoverability and inconsistent routing
 - Manual workflows for content management
 - Lack of visibility in search results (e.g., rich snippets, featured content)
 - Suboptimal user flow, leading to higher bounce rates and lower conversions
 - Cluttered navigation and inefficient content structure across 10,000+ pages
---

## User Research & Insights  
User testing and data analytics surfaced major friction points:

 - Users were overwhelmed navigating treatment options, clinics, and insurance providers
 - Key user feedback highlighted frustration with unclear category labels and a lack of filtering options.
 - Category labels were unclear, and filter options were limited
 - Keyword and competitor analysis revealed SEO opportunities using rich snippets and structured data

## Technical Implementation
### Routing & Page Generation

- Implemented dynamic routing using `createPages` (Gatsby) and React Router for category-based URLs like `/insurance/aetna/`, `/clinics/tx/houston/`
- Created page templates that automatically generated new routes from CMS updates—enabling content scaling without code changes
- Added pagination, deep linking, and query-based filtering with route-aware GraphQL queries
---

### CMS & Data Architecture

- Sanity: Used Sanity as the headless CMS for product and service pages, allowing flexible content modeling and dynamic content delivery. Extended it with custom fields and syncing content to PostgreSQL for relational querying and historical data storage
- Modeled WordPress as a headless CMS, extended with custom fields and synced to PostgreSQL for relational querying and historical data storage  
- Integrated Firestore for real-time admin workflows, allowing non-technical editors to update content without redeploys  
- Built custom WordPress plugins for managing editorial workflows and structured metadata

---

### State Management

- Used local state for UI interactivity (e.g., menu toggles, filter chips), derived state for routing context, and synced state via GraphQL  
- Integrated Redux for global state (e.g., active filters, breadcrumbs) when needed

---

### Frontend Development

- Developed responsive, accessible UI components in React + Tailwind CSS
- Built dynamic submenus, breadcrumbs, and smooth-scrolling navigation to enhance UX
- Created filterable views for services, clinics, and articles based on structured CMS data

---

### SEO & Structured Data

- Generated clean, descriptive URLs for all dynamic pages
- Added meta tags, Open Graph tags, and automated JSON-LD schema for:
  - Articles
  - Medical Clinics
  - Insurance Providers
  - FAQs
  - Reviews
  - Breadcrumbs
- Validated structured data using Google Rich Results Test and Search Console
- Injected schema automatically at build time via Gatsby, improving discoverability across 1000s of pages

---

### Performance Optimization

- Refactored data queries and asset loading for <2s Time to Interactive (TTI)  
- Used Cloudflare CDN for caching and lazy loading to minimize page load times  
- Structured GraphQL queries per route to avoid overfetching and reduce build times

---

### Testing & CI/CD

- Wrote unit tests (Jest) and end-to-end tests (Cypress) for routing, rendering, and UI behavior  
- Integrated schema validation, linting, and automated tests into GitHub Actions + Netlify deploy previews  
- Ensured cross-device compatibility and robust CI/CD pipelines for continuous quality assurance

---
### System Architecture

- Architected a modular, scalable content system powered by WordPress, PostgreSQL, Firestore, and GraphQL  
- Designed schema structures and content flows that minimized database load and maximized editorial flexibility

## User Feedback

### Patients
Found the improved structure and dynamic pages easier to navigate, leading to faster access to relevant insurance details and treatment options during the evaluation stage of their journey.

### Administrators
Benefited from an optimized content management process, with fewer manual updates required and a more streamlined workflow for managing content at scale.

---

## Internal Navigation on Resource Hub

### Before Implementation
<img src="https://i.imgur.com/qvLhXCk.png" alt="Before Screenshot" width="600"/>

### After Implementation
<img src="https://i.imgur.com/xONWX3N.jpg" alt="After Screenshot" width="600"/>

---

## Results

- Boosted core feature interactions (e.g., consultations, bookings) by 25%.
- Improved conversion rate by 20% for high-value actions like bookings and form submissions; bookings alone rose 15% within two cycles.
- Raised mobile engagement by 25%, ensuring consistent cross-device usability.
- Increased returning users by 15%, signaling improved product experience and customer loyalty.
- Lifted Net Promoter Score (NPS) by 10 points after new feature rollout, reflecting higher user satisfaction.
- Automated content updates reduced manual intervention by 40%, cutting errors and rework.
- Streamlined workflows cut content approval and publishing times by 30%, enabling greater scalability.
- Achieved 90% user satisfaction with new feature addressing a key pain point: matching users with the right center.
