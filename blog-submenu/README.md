# Sitewide Content Overhaul and Resource Hub Redesign for Healthcare Marketplace: Scalable Architecture, SEO Optimization, and Enhanced UX
---

## Table of Contents

- [Overview](#overview)
- [Business Challenge](#business-challenge)
- [User Research Insights](#user-research-insights)
- [Technologies Used](#technologies-used)
- [Architecture & Implementation](#architecture--implementation)
  - [Content Architecture](#content-architecture)
  - [Dynamic Routing and Page Creation](#dynamic-routing-and-page-creation)
  - [State Management](#state-management)
- [Results](#results)
- [Before & After](#before--after)

## Background
Led the redesign of a healthcare resource hub, improving information architecture, navigation, and user interaction. Used Gatsby, GraphQL, Postgres, and WordPress to enhance content discoverability and engagement, scaling to 10,000+ healthcare pages.

The redesign focused on improving content delivery, search engine performance, and user experience across treatment options, insurance offerings, and clinic details. The goal was to streamline content organization, improve discoverability, and enhance SEO for better online visibility.

Role: Development Lead, QA, Project Manager
Collaborators: UX Researcher, Product Designer, Engineering Manager, Product Owner, Chief Producter Officer (for project and budget approval)

---

## Tech Stack 
- Frontend: ReactJS, TypeScript, Tailwind CSS, Gatsby, Webpack
- Routing & Pages: React Router, Gatsby’s createPages API
- Backend: WordPress, Postgres, GraphQL, Firestore
- State Management: Local, derived, and synced state with Redux
- Testing & Optimization: Jest, Cypress
- Version Control: Git, GitHub
- CI/CD: GitHub Actions, Netlify, Vercel

## Business Challenge  
The existing site lacked clear content organization and routing, hindering user navigation. SEO performance was also impacted by duplicate URLs and inefficient metadata, affecting organic traffic. The challenge was to implement a scalable content structure and improve search engine rankings.

### Key issues:
 - Poor content discoverability and inconsistent routing
 - Manual management of 10,000+ pages, limiting scalability and increasing the risk of content drift
 - Lack of visibility in search results (e.g., rich snippets, featured content)
 - Suboptimal user flow, leading to higher bounce rates and lower conversions
 - Cluttered navigation and inefficient content structure across 10,000+ pages
---

## User Research & Insights  
User testing and data analytics indicated key pain points:

 - Users found it difficult to navigate the massive catalog of treatment options, insurance plans, and clinics.
 - Key user feedback highlighted frustration with unclear category labels and a lack of filtering options.
 - Search results were inconsistent, with important content buried deep within the site.
 - Through keyword analysis and competitive benchmarking, we identified opportunities to improve on-page SEO by incorporating schema for rich snippets and focusing on better taxonomies for healthcare topics.

## Technical Execution

### Content Organization & Navigation  
- Built a **dynamic hierarchical category system** using GraphQL to reduce content overload.
- Designed a **submenu UI** for quick access to relevant topics.
- Designed a **hierarchical taxonomy** for content categories, then mapped that to Gatsby’s page generation system.  
- Built **category landing pages** and **individual article pages** dynamically on the server

### Routing & State  
- Used **React Router** for custom client-side routing and deep linking across categories.  
- Handled submenu navigation state locally, while syncing global content filters via GraphQL.  
- Managed UI state (expanded menus, selected filters) in a scalable, reusable pattern.
  
### Performance & Scalability  
- Refactored data layer using **Postgres** for relational efficiency.
- Used **GraphQL** to fetch only the data needed, improving speed and responsiveness.
- Structured GraphQL queries to fetch content by category and author.  
- Used **Cloudflare caching and lazy loading** to keep load times under 2s, even for large datasets.  
- Enabled pagination for long category archives to reduce client load.

### Seamless CMS Integration  
- Developed custom WordPress plugins for syncing with Postgres.
- Preserved editorial workflows while modernizing the content delivery stack.

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

Route Configuration: Using React Router, I created a system for mapping content categories (e.g., /insurance/aetna/) to specific React components. This allowed for dynamic page generation based on category-specific data fetched from GraphQL.
Dynamic Pages: Designed dynamic routes using Gatsby’s Page Query to ensure that the content for each page was pulled directly from a data source (Firestore/GraphQL). As new service pages were added, the route system would automatically handle them, keeping the site scalable.
GraphQL API: Integrated GraphQL queries to ensure that every route was dynamically populated with the latest information, such as insurance plan details or treatment therapies. This enabled better content synchronization and accuracy across the website.

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
