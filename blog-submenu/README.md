# Healthcare Resource Hub Redesign and Content Overhaul

<b>Role</b>: Development Lead, QA, Project Manager
<b>Collaborators</b>: UX Researcher, Product Designer, Engineering Manager, Product Owner, Chief Producter Officer (for project and budget approval)

---

## Background
Led the redesign of a healthcare resource hub serving over 10,000 pages of medical content. Led frontend architecture, routing logic, content modeling, and custom CMS workflows. Focused on improving information architecture, navigation, SEO, and content discoverability across treatment options, insurance offerings, and clinic details. 




---

## Tech Stack 
- Frontend: ReactJS, TypeScript, Tailwind CSS, Gatsby, Webpack
- Routing & Pages: React Router, Gatsby’s createPages API
- Backend: WordPress, Postgres, GraphQL, Firestore
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

## Technical Execution

Routing & Page Generation
Used Gatsby’s createPages API and React Router to dynamically generate routes like /insurance/aetna/
Implemented templates for services, clinics, FAQs that scaled automatically as new content was added
Structured GraphQL queries to fetch category- and author-specific content
Added pagination and deep linking for efficient client-side navigation

State Management
Local state for interactivity (menu toggles, filter chips)
Derived state for route context and UI conditions
Synced state for dynamic content via GraphQL

Backend & CMS Integration
Extended WordPress with custom fields and synced content to Postgres
Integrated Firestore for real-time updates and lightweight admin workflows
Built custom WordPress plugins to support editorial workflows with modern delivery

Performance & Scalability
Refactored the data layer with Postgres for relational efficiency
Fetched only needed content using optimized GraphQL queries
Implemented Cloudflare caching and lazy loading to maintain sub-2s load times
Enabled scalable page generation and low-overhead content expansion

Testing & CI
Wrote unit and integration tests using Jest and Cypress
Validated routing and data hydration across devices
Incorporated schema validation, linting, and automated tests into CI/CD pipelines

SEO Enhancements & Structured Data
Created SEO-friendly URLs with clean, descriptive paths

Added meta tags, OG tags, and JSON-LD structured data for articles, clinics, insurance providers, reviews, breadcrumbs, and FAQs

Automated schema generation at build time and validated using Google Rich Results Test and Search Console


Information Architecture & Routing
Created dynamic nested routing (/insurance/aetna/, /clinics/tx/houston) via Gatsby’s createPages API and React Router

Built custom taxonomy system and submenu UI powered by GraphQL

Integrated pagination and query-based filtering using Gatsby node APIs and local/derived state

⚛️ Component System & State
Built modular, accessible UI components with React + Tailwind

Managed local (UI), derived (route-driven), and synced (GraphQL) state

Integrated Redux for shared global state where needed (e.g. filters, breadcrumbs)

🧱 CMS & Data Layer
Modeled WordPress as a headless CMS, syncing to Postgres for performant querying

Wrote custom WP plugins for editorial fields and used Firestore for lightweight real-time admin tools

Optimized GraphQL queries to fetch only what’s needed per route context

📈 SEO & Structured Data
Generated clean URLs, meta tags, and dynamic JSON-LD for articles, clinics, providers, FAQs

Validated structured data with Google Rich Results Tool and automated schema injection at build time

Improved organic visibility and content indexing for 1000s of pages

🚀 Performance & Scalability
Refactored queries and image handling for build speed and <2s TTI

Cached pages with Cloudflare and implemented lazy loading

Scaled automated page generation and CMS-driven updates with minimal dev overhead

🧪 Testing & CI
Wrote unit tests (Jest) and E2E flows (Cypress) for routing, content rendering, and UI state

Integrated schema validation, linting, and tests into GitHub Actions + Netlify deploy previews
---

1. **System Architecture**  
   - Planned and implemented a headless CMS flow combining **WordPress**, **Postgres**, and **GraphQL**.  
   - Structured schema to support scalable content growth and minimal database load.

2. **Frontend Development**  
   - Built responsive UI in **React** + **Tailwind**, including category submenus and article previews.  
   - Added **auto-scroll and smooth transition behaviors** for better user flow.

3. **Backend Integration**  
   - Used **GraphQL** to structure queries for precise data fetching.  
   - Implemented caching with **Cloudflare** to reduce server load.

4. **Testing & Optimization**  
   - Wrote unit and integration tests with **Jest** and **Cypress**.  
   - Optimized performance for mobile and slow networks.
  
   -  **Page & Routing Architecture**  
   - Used Gatsby’s `createPages` to generate hundreds of category and post pages from CMS content.  
   - Implemented React Router for clean URL structures and in-app routing between views.

2. **Frontend Engineering**  
   - Built submenu and filter components in **React** with accessibility and responsiveness in mind.  
   - Used **Tailwind CSS** for fast UI prototyping and consistent design tokens.

3. **Backend & Data Layer**  
   - Extended WordPress with custom fields and synced it to a **Postgres** schema.  
   - Wrote GraphQL queries to fetch categorized content efficiently and support filtering UI.

4. **State Management Strategy**  
   - Local state for interactive elements (e.g. submenu toggle, filter chips).  
   - Derived state for current route context and active filters.  
   - Server-synced state for dynamic content via GraphQL.

5. **Testing & CI**  
   - Covered UI interactions and edge cases with **Jest** unit tests.  
   - Wrote integration tests using **Cypress** to ensure routing and data hydration worked across devices.
     
---

## Dynamic Routing System and Page Generation

- Route Configuration: Used React Router to create a system for mapping content categories (e.g., /insurance/aetna/) to specific React components. This allowed for dynamic page generation based on category-specific data fetched from GraphQL.
- Dynamic Pages: Designed dynamic routes using Gatsby’s Page Query to ensure that the content for each page was pulled directly from a data source (Firestore/GraphQL). As new service pages were added, the route system would automatically handle them, keeping the site scalable.
- GraphQL API: Integrated GraphQL queries to ensure that every route was dynamically populated with the latest information, such as insurance plan details or treatment therapies. This enabled better content synchronization and accuracy across the website.

### SEO Enhancements
- Unique, Descriptive URLs: Worked on SEO-friendly URL structure (e.g., /insurance/aetna/) to make each page more easily discoverable by search engines and users.
- Meta Tags & Structured Data: Added meta tags, OG tags, and structured data to ensure that each page had optimized content for search engines, social media platforms, and third-party applications.
- Content Management System Enhancements

### Firestore Integration
Integrated Firestore as the backend database to store content for each category. This allowed real-time updates and easy content management without requiring heavy backend logic or manual updates, enabling non-technical administrators to manage content more efficiently.

### PostgreSQL for Data Storage
Used PostgreSQL to store historical data and ensure consistency across dynamic routes, allowing for more sophisticated querying and content aggregation.

## User Experience Enhancements

UI/UX Design: Leveraged Tailwind CSS to ensure a responsive, user-friendly interface, enhancing readability and mobile accessibility for healthcare-related content.

Navigation Optimization: Created intuitive breadcrumb navigation and category-based menus, allowing users to easily filter through insurance providers, treatment options, and other services.

Feedback Integration: Incorporated user feedback from both patients and site administrators to continually improve the flow of information and make the site easier to navigate.

Dynamic Routing and Page Generation
- Built a scalable routing architecture using React Router + Gatsby to generate page dynamically on the server (e.g. /insurance/aetna/) that pulled structured data from GraphQL + Firestore.
- Created templates for services, clinics, and FAQs that automatically generated new pages based on backend content updates—enabling content at scale with low engineering overhead.
- Integrated PostgreSQL for structured historical data storage and advanced content filtering.

Structured Data & SEO Enhancements
Developed JSON-LD schemas for:

 - Articles
 - Medical Clinics
 - Insurance Providers
 - FAQs
 - Reviews
 - Breadcrumbs

Implemented schema types per Schema.org standards and validated them using Google Rich Results Test and Search Console.
Automated schema generation during Gatsby builds, ensuring all new pages included accurate structured metadata.

## Quality Assurance Testing and Optimization
Ran rigorous validation using schema testing tools, Google Search Console, and in-browser previews.
Incorporated automated linting and schema validation checks into the CI/CD pipeline for continuous quality assurance.


## User Feedback
Patients: Found the improved structure and dynamic pages easier to navigate, leading to faster access to relevant insurance details and treatment options during the evaluation stage of their journey.

Administrators: Benefited from an optimized content management process, with fewer manual updates required and a more streamlined workflow for managing content at scale.

---

## Visuals

### Mockup Design  
<img src="https://i.imgur.com/xONWX3N.jpg" alt="Mockup Design" width="600"/>

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
