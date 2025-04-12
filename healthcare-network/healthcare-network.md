# Redesigned Information Architecture and Navigation for a Leading Health Network to Maximize Discoverability, Patient Access, and SEO

## Project Background

Led the optimization of **10,000+ pages** for a digital healthcare marketplace with ongoing improvements to an additional **40,000 pages** to ensure consistency and prevent regressions, supporting a seamless user experience across the entire network.

- **Role:** Development Lead, Technical Architect, Project Manager
- **Collaborators:** Engineering Manager, Product Manager, Chief Product Officer (for buy-in and approval), Content Authors updating the CMS

---

## Tech Stack
React.js, TypeScript, GraphQL, Gatsby, PostgreSQL, Jest, Graph QL(Apollo Client), Cypress, Yarn, Git, GitHub Actions, Schema Markup Validator, Google's Structured Data Testing Tool, Lighthouse  

---

## Business Challenge
In an increasingly competitive healthcare market, the health network needed to enhance search visibility, drive organic traffic, and improve accessibility of critical information to boost conversions and patient acquisition.

---

## User Research Insights
I conductive extensive user research alongside the product team, including:

Surveys: Gained feedback from patients and healthcare professionals to identify pain points and expectations.

Keyword & Competitive Analysis: Analyzed popular search terms and competitor websites to identify opportunities for improving visibility and content structure.

Key insights revealed that appearing in rich results and featured snippets significantly impacted user engagement, guiding us to prioritize schema coverage for improved search visibility.

---

## Key Challenges and Solutions

### 1. Diverse Content Types & Schema Integration
Challenge: Multiple page types (articles, FAQs, product pages, clinic listings) required custom schema configurations.
Solution: Built reusable, dynamic JSON-LD templates using React components. Integrated with Gatsby’s SSR for pre-rendered structured data across 10,000+ pages, with automation scaling to an additional 40,000.

### 2. Schema Validation at Scale
Challenge: Manual schema validation wasn't scalable and risked compliance errors.
Solution: Used Google’s Structured Data Testing Tool to detect issues, then introduced Jest-based regression testing to ensure schema accuracy throughout CI/CD.

### 3. GraphQL Query Optimization
To improve the performance and consistency of content delivery, I integrated GraphQL with Firestore, ensuring seamless data fetching across dynamic content. I optimized Apollo Client caching to minimize redundant data fetching, boosting load times and reliability.

```tsx
// Example of Apollo Client caching strategy
const { data, loading, error } = useQuery(GET_CLINIC_DETAILS, {
  variables: { clinicId: clinicId },
  fetchPolicy: 'cache-first', // Use cache if available to reduce request load
});
```

### 4. Crawlability and Indexing
To improve crawl efficiency, I built categorized sitemap indexes, filtering out low-value pages like parameterized and noindex pages. This ensured a more effective use of crawl budgets and reduced unnecessary indexing delays.

## Technical Implementation Overview

### Dynamic Schema Generation
- Developed JSON-LD scripts for Articles, FAQs, Products, Clinics, and Businesses
- Integrated Schema.org types: FAQPage, BreadcrumbList, Review, MedicalClinic, MedicalBusiness
- Used React components to dynamically generate markup per content type
- Enabled SSR via Gatsby to pre-render schema and make it easily discoverable by search engines

```tsx
  // Example of a reusable React component for JSON-LD
const ArticleSchema = ({ article }) => {
  const schema = {
    "@context": "https://schema.org",
    "@type": "Article",
    "headline": article.title,
    "description": article.excerpt,
    "author": {
      "@type": "Person",
      "name": article.author,
    },
    "datePublished": article.datePublished,
    "image": article.image,
  };

  return <script type="application/ld+json">{JSON.stringify(schema)}</script>;
};
```

### GraphQL and Firestore Integration
- Queried structured content (e.g., clinic details, FAQs) from Firestore using GraphQL
- Ensured data consistency across front-end content and schema fields

```tsx
// Example of optimized GraphQL query with Apollo Client
const GET_CLINIC_DETAILS = gql`
  query GetClinicDetails($clinicId: ID!) {
    clinic(id: $clinicId) {
      name
      services {
        name
        description
      }
      location {
        address
        phone
      }
    }
  }
`;

const { data, loading, error } = useQuery(GET_CLINIC_DETAILS, {
  variables: { clinicId: clinicId },
});
```

### Breadcrumb Automation
I implemented an automated breadcrumb generation system based on real-time page hierarchy, which was paired with the BreadcrumbList schema to improve search result visibility. This allowed for better navigation and enhanced SERP features.

```tsx
- // Example of auto-generating breadcrumb for page hierarchy
const generateBreadcrumb = (pageHierarchy) => {
  return pageHierarchy.map((item, index) => ({
    "@type": "ListItem",
    "position": index + 1,
    "name": item.name,
    "item": `https://www.example.com/${item.slug}`,
  }));
};
```

```tsx
// Example usage for a page hierarchy
const breadcrumbList = generateBreadcrumb([
  { name: 'Home', slug: '' },
  { name: 'Services', slug: 'services' },
  { name: 'Cardiology', slug: 'cardiology' },
  { name: 'Clinic Name', slug: 'clinic-name' },
]);
```
This setup helped improve the site’s internal linking structure and ensured that search engines could more easily index key pages.

### Index and Performance Optimization
To improve crawl efficiency, I built categorized sitemap indexes, filtering out low-value pages like parameterized and noindex pages. This ensured a more effective use of crawl budgets and reduced unnecessary indexing delays.

```tsx
- // Example of dynamically generated sitemap for specific taxonomy
const generateSitemap = (pages, taxonomy) => {
  return pages
    .filter(page => page.taxonomy === taxonomy)
    .map(page => ({
      url: `https://www.example.com/${taxonomy}/${page.slug}`,
      lastModified: page.lastModified,
    }));
};

// Call function to create sitemap for 'cardiology' pages
const cardiologySitemap = generateSitemap(pages, 'cardiology');
```

- Implemented SSR and optimized bundle delivery to maintain high page speed and make the pages easily crawlable by search engines.

---

## Agile Project Management and Process Integration

### Eliciting Requirements and PRD Submission

- Collaborated with stakeholders to gather and document project requirements.
- Submitted a Product Requirements Document (PRD) to ensure alignment with business goals and gain stakeholder buy-in.

### Sprint Planning and Timeline Management

- Broke down the project into actionable tasks and managed them through Jira, ensuring progress aligned with the sprint timeline.
- Monitored and adjusted the project timeline to ensure on-time delivery, collaborating closely with cross-functional teams to manage dependencies and risks.

## Quality Assurance and Performance Testing

### Unit Testing (Jest)
I implemented Jest for unit testing to ensure component integrity, focusing on edge cases and data mock-ups. This early validation reduced post-launch issues and ensured schema stability.

### End-to-End Testing (Cypress)
Used Cypress to simulate user flows and verify correct schema rendering and page behavior, ensuring the site met SEO and accessibility standards.

### Performance Auditing (Lighthouse, PageSpeedInsights, SpeedCurve, WebPage Test)
Ran staging environment links through several tests to validate that the new implementation did not introduce any performance regressions.

---

## Results

### SEO & Site Performance Improvements:
- **+30% increase in visibility** through structured data integration, making content easier to find  
- **+20% more indexed pages**, with **−30% faster indexing times**  
- **+20% boost in rich snippet visibility** (FAQs, reviews), driving more traffic  
- **+15% increase in click-through rate**, leading to more organic traffic

### Efficiency & Productivity Gains:
- **+60% reduction in manual work** through automated schema generation, boosting developer velocity  
- **+25% improvement in content team productivity** by streamlining content workflows and reducing schema-related bottlenecks

### User Engagement & Conversions:
- **+25% increase in page views**  
- **+18% longer session duration**  
- **+20% more lead generation** for appointments
