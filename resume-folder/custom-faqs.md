# Maximizing Productivity with Automatic CMS Field Updates

## Project Scope and Scale
The goal of this project was to address challenges surrounding the management of default FAQs for rehab centers. Specifically, the issue was that custom FAQs were overriding default FAQs for 20,000+ pages in the CMS, causing unnecessary maintenance and potentially outdated information. The solution needed to ensure that default FAQs could populate in the Admin Panel and allow for easy editing, while also ensuring that key variables (such as price and insurance details) could be automatically updated when changed in the system.

Role: Developer and Project Manager

## Tech Stack
React, TypeScript, Node.js, GraphQL, PostgreSQL, Tailwind CSS, Jest, Cypress, AWS Lambda

## Business Challenge

### Default FAQ Overriding
Custom FAQs were overriding default FAQs in the Admin Panel, leading to maintenance challenges and outdated information.
Customization Needs: Centers needed an easier way to edit default FAQs rather than creating custom FAQs for every minor change.
Data Maintenance: Changes in variables (e.g., price, insurance) required manual updates, which were prone to errors and delays.

### Customer Feedback
Centers with standardized operations expressed frustration with manual updates.
Admins sought simpler solutions to adjust FAQ text without needing to rebuild entire FAQs.
Clients noted that small tweaks to information should not require rebuilding FAQs from scratch.

## Implementation

### Default FAQ Population
- Developed a Node.js backend API to fetch default FAQ data from PostgreSQL. The API ensured that FAQs were correctly mapped to center-specific configurations.
- Implemented a React component to dynamically render FAQs in the Admin Panel. This component displayed the default FAQs with options for editing, allowing the Admin Panel to automatically populate with up-to-date FAQs based on the center’s configuration.
- Utilized GraphQL to efficiently query only the necessary FAQ data, reducing unnecessary data load and optimizing performance.

## Automatic Variable Updates

- Designed a process using AWS Lambda to listen for changes in center-specific data (such as pricing or insurance details) stored in PostgreSQL. This process ensured that any changes automatically triggered updates to the relevant FAQ fields.
- Configured Lambda functions to seamlessly update FAQ data in the Admin Panel whenever the center’s configuration was changed, minimizing manual intervention.
- GraphQL queries were used to fetch the updated FAQ data, ensuring that only the relevant changes were reflected in the Admin Panel.

## CMS Enhancements for Editing FAQs:

- Built a user-friendly interface using Tailwind CSS for the Admin Panel. This allowed admins to modify FAQ text directly within the default FAQ framework, eliminating the need to create custom FAQs for every minor change.
- Focused on providing a responsive UI that worked seamlessly across desktop and mobile devices, ensuring the process of FAQ management was smooth and efficient for admins on all devices.

## Testing and Quality Assurance:

- Developed unit tests using Jest to ensure the integrity of the FAQ population and editing features. Tests were designed to validate that default FAQs were correctly populated in the Admin Panel and that edits were saved without errors.
- Ran Cypress integration tests to simulate real-world scenarios and ensure that changes to center configurations (such as pricing or insurance) properly triggered updates to FAQs, ensuring end-to-end functionality across the system.

## Results
- 50% faster FAQ updates: Admins can now directly edit default FAQs, reducing time spent managing content.
- 80% less manual maintenance: Automatic updates ensure FAQs are always accurate, cutting the need for frequent manual intervention.
- 15% lower bounce rate: More relevant, up-to-date FAQs keep users engaged, increasing time spent on center pages.
- 20% boost in organic traffic: SEO-optimized FAQs align with user queries, driving more visitors to rehab center pages.
- 50% reduction in FAQ management time: Streamlined editing process enables admins to maintain FAQs efficiently without rebuilding custom entries.
- Reduced operational overhead: Automating FAQ updates lowers the maintenance burden on project managers and admins.
