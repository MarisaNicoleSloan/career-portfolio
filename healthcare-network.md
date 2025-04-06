# Optimizing an Enterprise Healthcare Network: Site Structure, Navigation, and SEO

## Project Scale

Led the optimization of **10,000+ pages**, with ongoing improvements to an additional **40,000 pages** to ensure consistency and prevent regressions, supporting a seamless user experience across the entire network.

- **Role:** Full-stack Developer, Lead Technical Architect  
- **Timeline:** 1 Sprint (2 weeks)  

I managed every aspect of this project, from initial research and technical implementation to final testing and deployment.

---

## Business Challenge

In a competitive online landscape, improving search engine visibility is crucial for medical facilities. The primary goal was to integrate structured data to better present content in search results, ultimately boosting organic traffic and improving user engagement.

---

## User Research Insights

Surveys, keyword analysis, and competitive research revealed that visibility in featured snippets and rich search results was vital for attracting user attention. Our goal was to ensure that the medical facility's content was well-represented in these results.

---

## Tech Stack

- ReactJS  
- TypeScript  
- GraphQL  
- Gatsby  
- PostgreSQL  
- Jest  
- Apollo Client  
- Google Structured Data Testing Tool  
- Lighthouse  

---

## Technical Challenges

### Content Diversity  
Different content types (articles, FAQs, product pages) required custom structured data markups. I developed flexible, reusable schema templates to handle this complexity efficiently.

### Schema Integration  
Implementing Schema.org vocabulary across thousands of pages and content types required custom solutions for automation and consistency.

---

## Problem-Solving and Technical Details

### Schema Validation Issue  
Used Google’s Structured Data Testing Tool to identify and fix schema markup errors. Implemented **automated Jest tests** for regression checks, maintaining schema integrity at scale.

### Optimizing GraphQL Queries  
Utilized **Apollo Client caching** to reduce data request overhead, improving page load speeds and performance.

---

## Implementation

### JSON-LD Scripts  
Developed dynamic JSON-LD scripts for:
- Articles
- Products
- FAQs
- Medical Clinics
- Businesses

### Schema Types Implemented  
- `Breadcrumb`  
- `Review`  
- `FAQ`  
- `MedicalClinic`  
- `MedicalBusiness`

### Dynamic Breadcrumbs  
Implemented auto-generated breadcrumbs reflecting page hierarchy, reducing manual updates.

- **Custom Sitemap Index:** Categorized URLs by location, condition, taxonomies, and resources  
- **Exclusion of Non-Indexable Pages:** Filtered out noindex-tagged and parameterized URLs  
- **Data Retrieval:** Queried content from Firestore via GraphQL  

---

## Technical Implementation

### React & Gatsby for Dynamic Rendering  
Used React components to dynamically render schema markup based on content type.

### Server-Side Rendering (SSR) with Gatsby  
Enabled pre-rendered JSON-LD to improve SEO and page performance.

### GraphQL Integration  
Built schema from the same data source as content. For example, GraphQL fetched clinic details to populate `MedicalClinic` and `MedicalBusiness` schema types.

---

## Breadcrumbs Implementation

Auto-generated breadcrumbs reflected site hierarchy dynamically (e.g., `Home > Services > Cardiology > Clinic Name`).

- Integrated `BreadcrumbList` schema with React components to support search result enhancements.

---

## JSON-LD Schema Integration

Used JSON-LD for ease of integration without disrupting layout. Implemented schema types:

- `Breadcrumb` – site navigation  
- `FAQPage` – featured snippets  
- `Review` – medical service credibility  
- `MedicalBusiness`, `MedicalClinic` – accurate facility representation  

---

## Optimizing for Search Engine Indexing

- **SSR with Gatsby** for pre-rendered structured data  
- **Google Structured Data Testing Tool** for validation  
- Ensured full schema compliance and indexability  

---

## Quality Assurance and Testing

### Unit Testing with Jest  
- Tested schema edge cases and integration  
- Mocked GraphQL responses for incomplete/malformed data  

### End-to-End Testing with Cypress  
- Simulated user journeys  
- Validated correct schema rendering in search snippets  

### Performance Auditing with Lighthouse  
- Monitored SEO and load time metrics  
- Tuned SSR to maintain high performance  

---

## Results

### Key Metrics

- **+15% click-through rate** → more organic traffic  
- **+20% increase in lead generation** for appointments  
- **+25% increase in page views**  
- **+18% increase in session duration**  
- **+20% increase in indexed pages**  
- **−30% indexing time**  

---

## Impact on Business

- **Rich snippets (reviews, FAQs)** drove higher traffic and conversions  
- **Automated schema generation** reduced manual work by 60%  
- Boosted productivity and streamlined content management workflows  


