# Dynamic Breadcrumb Trail Hierarchy

## Problem Statement

Navigating complex websites can be a daunting experience for users. The primary aim was to improve user navigation on the website by implementing a dynamic breadcrumb trail hierarchy. This feature would automatically generate breadcrumb sequences, sorting values from broad (e.g., country) to specific (e.g., city), eliminating the need for manual CMS updates and saving valuable time.

## User Research Results

We initiated this project with thorough user research, including user interviews and website analytics analysis. The data indicated that users frequently experienced difficulties in locating specific content and understanding their position within the website's structure. This research served as the foundation for our solution.

## Technologies
- GraphQL
- Postgres
- React

<img src="https://i.imgur.com/Np9Gitc.png" height="80%" width="80%" alt="breadcrumb trail">

## Implementation

### Dynamic URL Parsing

One of the core challenges was handling diverse page templates with varying URL structures. To tackle this, we implemented dynamic URL parsing. This feature automatically generates breadcrumb sequences, ensuring accuracy and consistency across the website. Whether it's a country, city, or any other category, our system effortlessly adapts.

### Sorting for Clarity

To enhance user understanding, we sort breadcrumb values from broad to specific categories. This clear and logical order simplifies navigation and ensures users always know where they are on the site.


## Results and Achievements
- Improved user navigation, leading to a 20% decrease in bounce rates and a 25% increase in page views
- Significantly reduced the workload for content managers by eliminating the need for manual CMS updates, saving hundreds of hours

[View feature live](https://luxuryrehabs.com/atlanta/)
