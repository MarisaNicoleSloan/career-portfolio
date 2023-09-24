# Dynamic Breadcrumbs for a Complex Addiction Treatment Directory

<b>Client</b>

RehabPath

<b>Client Industry</b>

Addiction Treatment and Mental Health

<b>Project Scale</b>

Approximately 8,000 pages were changed while another 40,000 had exclusions in place to avoid regressions

<b>Business Challenge and User Need</b>

Navigating complex websites can be a daunting experience for users. The primary aim was to improve user navigation on the website by implementing a dynamic breadcrumb trail hierarchy. This feature would automatically generate breadcrumb sequences, sorting values from broad (e.g., country) to specific (e.g., city), eliminating the need for manual CMS updates and saving valuable time.

<b>User Research Results</b>

Usability test results and web analytics analyses indicated that users frequently experienced difficulties in locating specific content and understanding their position within the website's structure. 

In addition, the breadcrumb trail had some logical inconsistencies depending on what page template a user was on. In this example, when selecting a city a state would get removed from the breadcrumb, and the speciality, in this case detox, would get placed at the end of the breadcrumb trail.

<img src="https://i.imgur.com/OWy50qS.png">

<b>Technologies Used</b>

React, GraphQL, Postgres, Jest

<b>Technical Challenges</b>

One of the core challenges was handling diverse page templates with varying URL structures. For example, different sections of the website had URLs structured differently, making it challenging to extract meaningful breadcrumb information consistently. 

The original breadcrumbs were configured to work across certain page templates. Extending the new dynamic breadcrumb functionality without causing regressions for the old templates was crucial.

<b>Implementation Details</b>

*Database Schema*

The database schema was a critical component of the solution. It was designed to store information about the website's content, including categories, subcategories, and their relationships. The schema included tables for content pages, categories, and mappings that linked pages to categories.

*GraphQL Integration*

To access data from the Postgres database, I utilized GraphQL as the query language. I defined GraphQL queries that allowed me to retrieve relevant information from the database for breadcrumb generation. GraphQL provided flexibility in fetching only the necessary data, reducing over-fetching, and optimizing query performance.

*Dynamic URL Parsing*

To address the URL structure challenge, I implemented dynamic URL parsing that could adapt to various URL structures depending on what page template the user was on. It intelligently extracted relevant information to construct breadcrumb sequences. 

*Sorting for Clarity*

To enhance user understanding, breadcrumb values are sorted in order of specificity. The values are sorted from broad, such as continent or country level, to the most specific and recent page in the trail, which would be the city that the user is searching for.

Thus, the breadcrumb always follow the pattern in this order:
- Continent
- Country
- State (if applicable)
- Region (if applicable), such as New England
- City or Province

<img src="https://i.imgur.com/prQqAh6.png">

This clear and logical order simplifies navigation and ensures users always know where they are on the site. 

<b>Testing and Quality Assurance</b>

Jest was implemented as an automated testing framework to validate the accuracy of breadcrumb generation on each page template. 

<b>Results and Achievements</b>

- Improved user navigation, leading to a 20% decrease in bounce rates and a 25% increase in page views
- Significantly reduced the manual workload for content managers by eliminating the need for manual CMS updates involving breadcrumb structure, saving hundreds of hours
