# Dynamic Page Routes and Categories

<b>Problem Statement</b>

To enhance user experience, scalability, SEO, and content management, I implemented a robust URL routing system and dynamic page categories. This solution addressed user feedback on content discoverability and simplified content management for administrators, all with the goal of creating a better user experience.

<b>Technologies Used</b>

React, Gatsby, GraphQL, Firestore

<b>Challenges Faced</b>
The challenges of this project were multifaceted:

- User Experience: Users found it difficult to navigate and discover content tailored to their interests and needs.
- Scalability: As our content library expanded, managing static routes became increasingly cumbersome.
- SEO: The website's organic traffic potential was diminished due to lack of discoverability 
- Content Management: Administrators faced challenges updating and organizing content efficiently

<b>Implementation Details</b>

A core part of the solution involved React Router, a popular library that enables declarative routing in React applications. React Router allowed me to define and manage routes within our application, ensuring that specific components were rendered when certain URLs were accessed. Here's how I approached dynamic route creation for our specific content categories:

*Route Configuration*

I established a route configuration system that mapped content categories to specific React components. This configuration acted as a blueprint for defining how different categories of content would be displayed. React Router's Route component was used to match URLs to the appropriate component based on the route configuration.

*Dynamic Routes*

To create dynamic routes, I dynamically generated route definitions based on the available content categories. This allowed me to scale the routing system as new categories were added.

*GraphQL Integration*

GraphQL played a crucial role in this process by providing the necessary data to populate content pages for insurance offerings, treatment services, and therapies offered by medical facilities. When a user accessed a particular URL, GraphQL queries were executed to fetch the relevant content for that category. This seamless integration ensured that the content remained up-to-date and accurate.

<img src="https://i.imgur.com/OJd1ebt.png">

These routes were achieved for 3 categories, each critical decision points in users seeking treatment for addiction or mental health issues.

In addition to the insurance routes, there were also routes for treatment services and treatment therapy offerings. The layout of the pages followed the same layout as the insurance pages and use the same components as well, including popular destinations tagged with the relevant category as well as a feed of results for centers offering the chosen category.

<img src="https://i.imgur.com/HnydjmI.png">

<img src="https://i.imgur.com/VsavQRj.png">

<b>User Feedback</b>

User feedback was overwhelmingly positive. Users reported it easier to discover relevant content, and administrators appreciated the simplified content management process.

<b>Benefits and Achievements</b>

- 30% increase in organic traffic with the introduction of insurance pages, speaking to a primary user need
- 15% increase in conversion rates, resulting from insurance being a key point in influencing a user to make an inquiry
- Reduced customer support queries regarding insurance offerings by 10%

