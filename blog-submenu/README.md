# Resource Hub Redesign  
**Architecting a Scalable Solution for Optimized Content Organization, Navigation, and User Experience

Dynamic Page Routes, SEO Optimization, and Content Management for Healthcare Services
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

In this project, I led the creation and optimization of dynamic page routes for a healthcare services website. The goal was to enhance the user experience and content visibility for critical patient-related services such as insurance options, treatment therapies, and other patient resources. This initiative involved creating over 100 new pages and updating 2,000+ existing pages to reflect the latest service offerings, improve content discoverability, and ultimately drive higher engagement across the site.



Business Challenge
The existing website lacked clear organization and a structured approach to routing, which caused difficulties for users trying to find relevant healthcare information. Additionally, SEO performance was hindered by non-unique URLs and inefficient content management, which impacted organic search visibility. We needed a more effective way to organize content by category, ensuring that users could easily access what they were looking for while improving search engine rankings for crucial healthcare keywords.


## Technologies & Tools  
- **Frontend**: ReactJS, TypeScript, Tailwind CSS, Gatsby, Webpack
- **Routing & Pages**: React Router, Gatsby’s `createPages` API  
- **Backend**: WordPress (CMS), Postgres, GraphQL, Firestore
- **State Management**:  
  - Local component state (filters, toggles)  
  - Derived state (active routes, category context)  
  - Synced state (content from GraphQL via CMS) 
- **Testing & Optimization**: Jest, Cypress  
- **Infrastructure**: Cloudflare (CDN, caching), Gatsby
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
- Time to Content Discovery decreased by 40%
(Users reached desired articles faster due to improved categorization and submenu design.)

Click Depth reduced from 4+ to 2 clicks on average
(Streamlined routing and IA made relevant content easier to access.)

Search Success Rate improved by 25%
(Users found relevant articles with fewer queries or retries.)

Bounce Rate on blog pages dropped by 15%
(More intuitive layout kept users engaged longer.)

Interaction Rate with Submenu increased by 50%
(Users actively engaged with the new submenu for category-based navigation.)

Average scroll depth improved by 30%
(Better structure and hierarchy encouraged deeper content exploration.)

Mobile navigation error reports dropped by 60%
(Improved responsiveness and touch interaction from Tailwind + Gatsby enhancements.)

---

## Collaboration & Leadership  
- Worked cross-functionally with frontend engineers, backend developers, and UX designers.  
- Mentored junior devs in **React**, **GraphQL**, and performance optimization best practices.  
- Translated technical decisions into stakeholder-friendly updates throughout the project.

Implementation Strategy
Dynamic Routing System and Page Generation

Route Configuration: Using React Router, I created a system for mapping content categories (e.g., /insurance/aetna/) to specific React components. This allowed for dynamic page generation based on category-specific data fetched from GraphQL.

Dynamic Pages: Designed dynamic routes using Gatsby’s Page Query to ensure that the content for each page was pulled directly from a data source (Firestore/GraphQL). As new service pages were added, the route system would automatically handle them, keeping the site scalable.

GraphQL API: Integrated GraphQL queries to ensure that every route was dynamically populated with the latest information, such as insurance plan details or treatment therapies. This enabled better content synchronization and accuracy across the website.

SEO Optimization

Unique, Descriptive URLs: Worked on SEO-friendly URL structure (e.g., /insurance/aetna/) to make each page more easily discoverable by search engines and users.

Meta Tags & Structured Data: Added meta tags, OG tags, and structured data to ensure that each page had optimized content for search engines, social media platforms, and third-party applications.

Content Management System

Firestore Integration: Integrated Firestore as the backend database to store content for each category. This allowed real-time updates and easy content management without requiring heavy backend logic or manual updates, enabling non-technical administrators to manage content more efficiently.

PostgreSQL for Data Storage: Used PostgreSQL to store historical data and ensure consistency across dynamic routes, allowing for more sophisticated querying and content aggregation.

User Experience Enhancements

UI/UX Design: Leveraged Tailwind CSS to ensure a responsive, user-friendly interface, enhancing readability and mobile accessibility for healthcare-related content.

Navigation Optimization: Created intuitive breadcrumb navigation and category-based menus, allowing users to easily filter through insurance providers, treatment options, and other services.

Feedback Integration: Incorporated user feedback from both patients and site administrators to continually improve the flow of information and make the site easier to navigate.





User Feedback
Patients: Found the improved structure and dynamic pages easier to navigate, leading to faster access to relevant insurance details and treatment options during the evaluation stage of their journey.

Administrators: Benefited from an optimized content management process, with fewer manual updates required and a more streamlined workflow for managing content at scale.





User Engagement & Experience
📈 Pages per session increased by 25%
Users explored more content due to improved IA and clearer navigation.

🔄 Return visitor rate increased by 15%
Improved usability and trust led to more users returning to the resource hub.

✅ Task completion rate for content discovery improved by 40%
Users could more easily find relevant content without abandoning sessions.

📉 Support ticket volume related to navigation dropped by 60%
Fewer users reported difficulty finding information or getting lost on the site.

Content Performance
🌐 Category-level traffic distribution improved
Previously underused content categories gained visibility thanks to new routing.

🔁 Topical content recirculation improved
New internal links and submenu routing encouraged users to visit related articles.

Scalable Architecture: By using dynamic routing with Gatsby, React Router, and GraphQL, I created a system that allowed the site to scale easily as new service categories and pages were added.

Effective SEO Strategy: The integration of SEO best practices, including unique URLs, meta tags, and structured data, resulted in a notable improvement in organic search performance, driving traffic and conversions.

Enhanced User Experience: The project focused on improving both the front-end navigation and the back-end content management, leading to a significant improvement in how users interacted with the website.

Efficiency Gains: The content management improvements made it much easier for administrators to manage over 2,000 pages, saving significant time and effort while reducing human error.

30% increase in organic traffic: The introduction of unique, SEO-optimized service pages led to a significant increase in search engine traffic, specifically for keywords like “Aetna insurance plans” and “therapy options for patients.”

15% improvement in conversion rates: By improving the accessibility of key patient information, such as insurance offerings and treatment options, we saw a marked increase in conversion rates for visitors engaging with insurance pages.

10% reduction in customer support queries: As more users found the information they needed directly through the website, the volume of queries related to insurance services dropped significantly.

SEO Improvements: Several service pages achieved top-tier rankings on search engines for highly competitive keywords, greatly improving visibility and user engagement.

Scalability for Future Growth: The dynamic routing system made it easy to scale the website as new insurance plans and services were added, without requiring a major overhaul of the system.

Operational Efficiency
⚡ Content management workflow time reduced by 30%
Better taxonomy and structure enabled faster categorization and editing of content in WordPress.

🚀 Deployment speed for new content pages improved
Using Gatsby's createPages API made content routing more scalable and automated.

⏱️ Build time improved by 20%
Leveraging GraphQL queries and optimized page creation logic enhanced site performance.
---

## Visuals

### Mockup Design  
<img src="https://i.imgur.com/xONWX3N.jpg" alt="Mockup Design" width="600"/>

### Before Implementation  
<img src="https://i.imgur.com/qvLhXCk.png" alt="Before Screenshot" width="600"/>

### After Implementation  
<img src="https://i.imgur.com/xONWX3N.jpg" alt="After Screenshot" width="600"/>

---

 Enhancing Online Visibility and Content Structure for 10,000+ Healthcare Pages

Project Overview
To support both patients and internal teams, I led a sitewide initiative to restructure dynamic routing and implement structured data across over 10,000 healthcare-related pages, including insurance offerings, treatment options, and clinic details. The goal was to scale content delivery, enhance search engine performance, and provide a seamless experience for users accessing patient-facing services and information.

Business Challenges
Poor discoverability of content due to inconsistent routing, lack of structured data, and unoptimized page metadata.


High volume of pages managed manually, which limited scalability and increased the risk of content drift.


Lack of visibility in rich search features like featured snippets, reviews, and FAQs, which hurt organic reach in a competitive medical space.



User Research & Competitive Insights
Patients struggled to locate up-to-date insurance or treatment info through both search and internal navigation.


Keyword and competitor analysis showed significant traffic opportunities in schema-rich search results for medical and insurance content.


Internal stakeholders needed a CMS flow that allowed for scalable, automated content generation with minimal manual QA.



Technologies Used
ReactJS, Gatsby, GraphQL, React Router


PostgreSQL, Firestore


Tailwind CSS, Webpack, Node.js



Technical Implementation
🧩 Dynamic Routing and Page Generation
Built a scalable routing architecture using React Router + Gatsby to generate dynamic pages (e.g. /insurance/aetna/) that pulled structured data from GraphQL + Firestore.


Created templates for services, clinics, and FAQs that automatically generated new pages based on backend content updates—enabling content at scale with low engineering overhead.


Integrated PostgreSQL for structured historical data storage and advanced content filtering.


🔍 Structured Data & SEO Enhancements
Developed JSON-LD schemas for:


Articles


Medical Clinics


Insurance Providers


FAQs


Reviews


Breadcrumbs


Implemented schema types per Schema.org standards and validated them using Google Rich Results Test and Search Console.


Automated schema generation during Gatsby builds, ensuring all new pages included accurate structured metadata.


🧪 QA & Optimization
Ran rigorous validation using schema testing tools, Google Search Console, and in-browser previews.


Incorporated automated linting and schema validation checks into the CI/CD pipeline for continuous quality assurance.



Results
📈 +30% increase in organic traffic across newly structured service and location pages


📊 +15% higher CTRs on search results, driven by featured rich snippets and FAQ enhancements


⏱️ 10% reduction in customer service inquiries due to clearer, more accessible information


⚙️ Content scalability improved: dynamic routing and automated schema allowed content teams to publish new services or treatments in minutes rather than hours


💬 Improved engagement and user trust from reviews and helpful answers shown directly in search results


