# Maximizing Customer Success and Administrator Productivity with Automatic CMS Field Updates

## Executive Summary

Designed and implemented an automated FAQ management system that reduced admin workload by 80% while improving content accuracy for 20,000+ rehab center pages. By enabling dynamic updates of variables and creating editable default FAQs, the solution addressed both customer and internal pain points, resulting in improved SEO performance and user engagement.

## Project Scope and Scale
The goal of this project was to address challenges surrounding the management of default FAQs for rehab centers. Specifically, the issue was that custom FAQs were overriding default FAQs for 20,000+ pages in the CMS, causing unnecessary maintenance and potentially outdated information. The solution needed to ensure that default FAQs could populate in Sanity and allow for easy editing, while also ensuring that key variables (such as price and insurance details) could be automatically updated when changed in the system.

<b>Role</b>: Developer, Project Manager

<b>Collaborators</b>: Customer Success Director, Product Manager, Chief Product Officer

## Tech Stack
React.js, TypeScript, Node.js, GraphQL, PostgreSQL, Tailwind CSS, Jest, Cypress, AWS Lambda, Sanity, Yarn, Git, Netlify

## Business Challenge

### Internal Pain Points
- <b>Customization Needs</b>: Centers needed an easier way to edit default FAQs rather than creating custom FAQs for every minor change.
- <b>Data Maintenance</b>: Custom FAQs were overriding default FAQs in Sanity, leading to maintenance challenges and outdated information.Changes in variables (e.g., price, insurance) required manual updates, which were prone to errors and delays.

### Customer Feedback
- Centers with standardized operations expressed frustration with manual updates.
- Admins sought simpler solutions to adjust FAQ text without needing to rebuild entire FAQs.
- Clients noted that small tweaks to information should not require rebuilding FAQs from scratch.

#### Direct Feedback
"Our team was spending hours each week just updating basic information across different pages. It felt like we were constantly playing catch-up." - Administrator at a multi-location rehab network


## Data Flow for Core Content Updates
- <b>User interface and content management</b>: Sanity provides the interface for content managers. CMS is a restrictive interface to update data.
- <b>Digital asset management</b>: Cloudinary is an image hosting provider for content content. All image content updates are synced to Cloudinary and the Algolia collection for the entry.
- <b>Data source</b>: PostgreSQL database stores the core content. Algolia is a search engine specifically used for searching core content (center and location data). Sanity is an interface for managing content that is then automatically synced (replicated) in PostgreSQL and Algolia.
- <b>Data retrieval</b>: GraphQL API queries only the necessary data. It bridges between Postgres and WordPress. More developer-friendly way to write queries for data retrieval.
- <b>Front-end</b>: CMS updates reflect on front end following site build
- <b>CI/CD</b> U[dates are automatically synced to the production site. Every time a new entry is published a new build is triggered via a CI/CD pipeline.
- <b>CDN</b>: User traffic is routed through cloudflare, which caches static assets (CSS, JS, images, fonts, 3rd-party libraries)
- <b>End user</b>: Sees the most recent data updates in the UI


## Implementation

### Default FAQ Population
- Developed a Node.js backend API to fetch default FAQ data from PostgreSQL. The API ensured that FAQs were correctly mapped to center-specific configurations.
- Implemented a React component to dynamically render FAQs in Sanity. This component displayed the default FAQs with options for editing, allowing Sanity to automatically populate with up-to-date FAQs based on the center’s configuration.
- Utilized GraphQL to efficiently query only the necessary FAQ data, reducing unnecessary data load and optimizing performance.

[Watch the walkthrough video on Loom (opens in new tab)](https://www.loom.com/share/4a2617416e9940fc85e25684f602ab5b)

## Automatic Variable Updates
- Designed and configured AWS Lambda functions to listen for changes in PostgreSQL-stored center data (e.g., pricing or insurance), automatically triggering updates to the relevant FAQ fields in Sanity.
- Used GraphQL queries to fetch only the updated FAQ data, ensuring accurate, real-time reflections of center-specific changes with minimal manual intervention.

## CMS Enhancements for Editing FAQs:

- Built a user-friendly interface using Tailwind CSS for Sanity. This allowed admins to modify FAQ text directly within the default FAQ framework, eliminating the need to create custom FAQs for every minor change.
- Focused on providing a responsive UI that worked seamlessly across desktop and mobile devices, ensuring the process of FAQ management was smooth and efficient for admins on all devices.

### Technical Challenges Overcome

- <b>Data Synchronization:</b> Implemented a robust error handling system to ensure that failed updates would retry automatically, preventing data inconsistencies between PostgreSQL and Sanity.
- <b>Performance Optimization:</b> Initial GraphQL queries were causing performance bottlenecks. Optimized queries by implementing pagination and selective field fetching, reducing average response time from 3s to 200ms.
- <b>Editing Workflow:</b> Created a custom React component for Sanity that preserved core FAQ content while allowing variable sections to be edited, solving the challenge of balancing standardization with customization.

## Testing and Quality Assurance

- Developed unit tests using Jest to ensure the integrity of the FAQ population and editing features. Tests were designed to validate that default FAQs were correctly populated in Sanity and that edits were saved without errors.
- Ran Cypress integration tests to simulate real-world scenarios and ensure that changes to center configurations (such as pricing or insurance) properly triggered updates to FAQs, ensuring end-to-end functionality across the system.

## Results
- <b>50% faster FAQ updates</b>: Admins can now directly edit default FAQs, reducing time spent managing content.
- <b>80% less manual maintenance</b>: Automatic updates ensure FAQs are always accurate, cutting the need for frequent manual intervention.
- <b>15% lower bounce rate</b>: More relevant, up-to-date FAQs keep users engaged, increasing time spent on center pages.
- <b>20% boost in organic traffic</b>: SEO-optimized FAQs align with user queries, driving more visitors to rehab center pages.
- <b>50% reduction in FAQ management time:</b> Streamlined editing process enables admins to maintain FAQs efficiently without rebuilding custom entries.
- <b>Reduced operational overhead</b>: Automating FAQ updates lowers the maintenance burden on project managers and admins.


### User Testimonial

"The ability to edit default FAQs directly has been a game-changer for our team. What used to take hours now takes minutes, and we're confident that our information is always accurate." - Center Administrator at a multi-location rehab provider

## Lessons Learned & Future Improvements
- <b>Early Stakeholder Involvement:</b> Having customer success team members involved from the beginning was crucial to understanding user pain points accurately and designing a solution that truly addressed their needs.
- <b>Automated Testing Investment:</b> The extensive Jest and Cypress testing setup required significant upfront time but paid dividends in reduced bugs and faster iterations, ultimately saving an estimated 40+ hours of debugging time.
- <b>Future Enhancements:</b> Plan to extend the automation framework to other content types beyond FAQs, and implement AI-assisted content suggestions based on user engagement patterns to further improve content relevance and SEO performance.Automated Testing Investment: The extensive Jest and Cypress testing setup required significant upfront time but paid dividends in reduced bugs and faster iterations, ultimately saving an estimated 40+ hours of debugging time.
- <b>Future Enhancements:</b> Plan to extend the automation framework to other content types beyond FAQs, and implement AI-assisted content suggestions based on user engagement patterns to further improve content relevance and SEO performance.
