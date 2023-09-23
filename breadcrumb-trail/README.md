# Dynamic Breadcrumb Trail Hierarchy Implementation

<b>Problem Statement</b>

Navigating complex websites can be a daunting experience for users. The primary aim was to improve user navigation on the website by implementing a dynamic breadcrumb trail hierarchy. This feature would automatically generate breadcrumb sequences, sorting values from broad (e.g., country) to specific (e.g., city), eliminating the need for manual CMS updates and saving valuable time.

<b>User Research Results</b>

Usability test results and web analytics analyses indicated that users frequently experienced difficulties in locating specific content and understanding their position within the website's structure. 

<b>Technical Challenges</b>

*Handling Diverse Page Templates and URL Structures*

One of the core challenges was handling diverse page templates with varying URL structures. For example, different sections of the website had URLs structured differently, making it challenging to extract meaningful breadcrumb information consistently. 

*Integration of GraphQL, Postgres, and React*

Integrating GraphQL for data retrieval, Postgres for database storage, and React for the frontend presented its own set of challenges. Ensuring seamless communication between these technologies and maintaining data consistency required careful planning and execution.

*Extending Existing Breadcrumb Functionality*

The original breadcrumbs were configured to work across certain page templates. Extending the new dynamic breadcrumb functionality without causing regressions for the old templates was crucial.

<b>Technologies Used</b>

React, GraphQL, Postgres, Jest

<b>Database Schema</b>

The database schema was a critical component of the solution. It was designed to store information about the website's content, including categories, subcategories, and their relationships. The schema included tables for content pages, categories, and mappings that linked pages to categories.

<b>GraphQL Integration</b>

To access data from the Postgres database, I utilized GraphQL as the query language. I defined GraphQL queries and resolvers that allowed me to retrieve relevant information for breadcrumb generation. GraphQL provided flexibility in fetching only the necessary data, reducing over-fetching, and optimizing query performance.

<b>Implementation Details</b>

*Dynamic URL Parsing*

To address the URL structure challenge, our team implemented dynamic URL parsing. This involved creating a URL parsing engine that could adapt to various URL structures. It intelligently extracted relevant information to construct breadcrumb sequences. We encountered instances where page URLs included query parameters and dynamically generated content, which required careful handling to ensure accuracy.

*Sorting for Clarity*

To enhance user understanding, breadcrumb values are sorted in order of specificity. This clear and logical order simplifies navigation and ensures users always know where they are on the site. 

<b>Testing and Quality Assurance</b>

Jest was implemented as an automated testing framework to validate the accuracy of breadcrumb generation.</b>

<b>Results and Achievements</b>

- Improved user navigation, leading to a 20% decrease in bounce rates and a 25% increase in page views.
- Significantly reduced the workload for content managers by eliminating the need for manual CMS updates, saving hundreds of hours.
