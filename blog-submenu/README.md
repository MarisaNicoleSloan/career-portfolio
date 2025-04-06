# Resource Hub Redesign  
**Architecting a Scalable Solution for Optimized Content Organization, Navigation, and User Experience
🔗 [Recovery.com](https://recovery.com)

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

## Project Overview  
Led the redesign of a large-scale healthcare resource hub, improving its information architecture, navigation, and user interaction. Built a scalable solution using **Gatsby**, **GraphQL**, **Postgres**, and **WordPress** to enhance content discoverability and user engagement.

---

## Business Challenge  
The original resource hub had a flat, unstructured blog layout. Content was hard to find, and engagement suffered. My goal was to revamp the system into a more intuitive and scalable content experience while maintaining performance.

---

## User Research & Insights  
- Usability testing showed users struggled to locate relevant content.
- Feedback highlighted confusion caused by inconsistent category labeling and lack of filtering.
- These insights drove a redesign focused on clear categorization and easier exploration.

---

## Technologies & Tools  
- **Frontend**: ReactJS, TypeScript, Tailwind CSS, Gatsby
- **Routing & Pages**: React Router, Gatsby’s `createPages` API  
- **Backend**: WordPress (CMS), Postgres, GraphQL
- **State Management**:  
  - Local component state (filters, toggles)  
  - Derived state (active routes, category context)  
  - Synced state (content from GraphQL via CMS) 
- **Testing & Optimization**: Jest, Cypress  
- **Infrastructure**: Cloudflare (CDN, caching)  
- **Version Control**: Git, GitHub
  
---

## Key Challenges & Solutions

### Content Organization & Navigation  
- Built a **dynamic hierarchical category system** using GraphQL to reduce content overload.
- Designed a **submenu UI** for quick access to relevant topics.
- - Designed a **hierarchical taxonomy** for content categories, then mapped that to Gatsby’s page generation system.  
- Built **category landing pages** and **individual article pages** dynamically using `gatsby-node.js`.

### Routing & State  
- Used **React Router** for custom client-side routing and deep linking across categories.  
- Handled submenu navigation state locally, while syncing global content filters via GraphQL.  
- Managed UI state (expanded menus, selected filters) in a scalable, reusable pattern.
- 
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

## Technical Execution

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

## Results

- **30% increase** in page views on blog content  
- **20% increase** in average time on page  
- **50% improvement** in page load times  
- **95% reduction** in bounce rate from search visitors  
- Scalable system built to support future content growth without compromising speed

---

## Collaboration & Leadership  
- Worked cross-functionally with frontend engineers, backend developers, and UX designers.  
- Mentored junior devs in **React**, **GraphQL**, and performance optimization best practices.  
- Translated technical decisions into stakeholder-friendly updates throughout the project.

---

## Visuals

### Mockup Design  
<img src="https://i.imgur.com/xONWX3N.jpg" alt="Mockup Design" width="600"/>

### Before Implementation  
<img src="https://i.imgur.com/qvLhXCk.png" alt="Before Screenshot" width="600"/>

### After Implementation  
<img src="https://i.imgur.com/xONWX3N.jpg" alt="After Screenshot" width="600"/>

---

## Takeaways  
This project showcased my ability to lead full-stack development with a strong focus on user needs, system scalability, and maintainability. I delivered measurable improvements in both product performance and content engagement, laying a strong foundation for long-term growth.
