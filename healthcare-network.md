# Optimizing an Enterprise Healthcare Network: Site Structure, Navigation, and SEO

## Project Scale

Led the optimization of **10,000+ pages**, with ongoing improvements to an additional **40,000 pages** to ensure consistency and prevent regressions, supporting a seamless user experience across the entire network.

- **Role:** Full-stack Developer, Project Manager
- **Timeline:** 1 Sprint (2 weeks)  

Managed all aspects of the project, from research and technical architecture to implementation, testing, and deployment.

---

## Tech Stack

React, TypeScript, GraphQL, Gatsby, PostgreSQL, Jest, Graph QL(Apollo Client), Cypress, Yarn, Git, GitHub Actions, Schema Markup Validator, Google's Structured Data Testing Tool, Lighthouse  

---

## Business Challenge

In a competitive online landscape, improving search engine visibility is crucial for medical facilities. The goal was to enhance search result presentation—boosting organic traffic, increasing conversions, and improving user engagement.

---

## User Research Insights

Surveys, keyword analysis, and competitive research revealed that appearing in rich results and featured snippets significantly influenced user behavior. Improving schema coverage across the site was key to visibility and growth.

---

## Key Challenges and Solutions

### 1. Diverse Content Types & Schema Integration
Challenge: Multiple page types (articles, FAQs, product pages, clinic listings) required custom schema configurations.
Solution: Built reusable, dynamic JSON-LD templates using React components. Integrated with Gatsby’s SSR for pre-rendered structured data across 10,000+ pages, with automation scaling to an additional 40,000.

### 2. Schema Validation at Scale
Challenge: Manual schema validation wasn't scalable and risked compliance errors.
Solution: Used Google’s Structured Data Testing Tool to detect issues, then introduced Jest-based regression testing to ensure schema accuracy throughout CI/CD.

### 3. GraphQL Query Optimization
Challenge: Performance bottlenecks from complex GraphQL queries.
Solution: Tuned Apollo Client caching and restructured Firestore queries to reduce data-fetching overhead, improving both load speed and reliability.

### 4. Crawlability & Indexing
Challenge: Low-priority and parameterized pages were inflating crawl budgets.
Solution: Built categorized sitemap indexes grouped by taxonomy, condition, and location. Excluded noindex and tracking-parameter pages to reduce crawl waste and accelerate indexing.

## Technical Implementation Overview

### Dynamic Schema Generation
Developed JSON-LD scripts for Articles, FAQs, Products, Clinics, and Businesses
Integrated Schema.org types: FAQPage, BreadcrumbList, Review, MedicalClinic, MedicalBusiness
Used React components to dynamically generate markup per content type
Enabled SSR via Gatsby to pre-render schema and enhance SEO

### GraphQL & Firestore Integration
Queried structured content (e.g., clinic details, FAQs) from Firestore using GraphQL
Ensured data consistency across front-end content and schema fields

### Breadcrumb Automation
Auto-generated breadcrumb trails based on real-time page hierarchy (e.g., Home > Services > Cardiology > Clinic Name)
Paired with BreadcrumbList schema to support enhanced listings in search results

### Index and Performance Optimization
Built custom sitemap indexes categorized by topic, condition, and location
Removed low-value (thin content) pages and noindex pages (robots tag contains noindex),to improve crawl efficiency
Implemented SSR and optimized bundle delivery to maintain high page speed and make the pages easily crawlable by search engines.

---

## Quality Assurance and Performance Testing

### Unit Testing (Jest)
Covered edge cases, mocked incomplete GraphQL data to ensure graceful degradation.

### End-to-End Testing (Cypress)
Simulated user flows and verified schema rendering in live environments.

### Performance Auditing (Lighthouse, PageSpeedInsights, SpeedCurve, WebPage Test)
Ran staging environment links through several tests to validate that the new implementation did not introduce any performance regressions.

---

## Results

- **+15% click-through rate** → more organic traffic  
- **+20% increase in lead generation** for appointments  
- **+25% increase in page views**  
- **+18% increase in session duration**  
- **+20% increase in indexed pages**  
- **−30% indexing time**  

---

## Impact on Business

- +60% reduction in manual work through automated schema generation, boosting developer velocity and freeing up time for higher-impact initiatives
- +25% improvement in content team productivity by streamlining content management workflows and reducing schema-related bottlenecks
- +20% increase in rich snippet visibility (FAQs, reviews), driving higher traffic and improved conversion rates
- +30% improvement in discoverability via structured data integration, contributing to long-term SEO performance and governance strategy
