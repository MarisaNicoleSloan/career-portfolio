# Dynamic Page Routes and Categories for Critical Patient Needs

<b>Client</b>

RehabPath

<b>Client Industry</b>

Addiction Treatment and Mental Health

<b>Project Scale</b>

Over 100 new pages were added to the site while approximately 2,000 pages were updated to reflect these new service offerings.

<b>Technologies Used</b>

React, Gatsby, GraphQL, Firestore

<b>Business Challenge and User Need</b>

The website was struggling to rank for important offerings related to patient needs, particularly insurance, treatment therapies, and treatment services such as detox or residential programs. Since there were no unique pages and URLs for these offerings, not only could they not be found by search engines by CMS administrators could not enhance individual pages.

In order to address these issues, I implemented a system for defining and managing URLs and their associated content. This system allowed for the creation of distinct pages on the website, each with its own unique URL.

<b>Implementation Details</b>

A core part of the solution involved React Router, a popular library that enables declarative routing in React applications. React Router allowed me to define and manage routes within the application, ensuring that specific components were rendered when certain URLs were accessed. Here's how I approached dynamic route creation for the specific content categories:

*Route Configuration*

I established a route configuration system that mapped content categories to specific React components. This configuration acted as a blueprint for defining how different categories of content would be displayed. React Router's Route component was used to match URLs to the appropriate component based on the route configuration.

An example of mapping a taxonomy (category) to a route included insurance. Since the insurance route (path) was /insurance/, any insurance page included that path (e.g. /insurance/aetna/, /insurance/cigna/, etc.) Now a page could be made for any insurance provider and a URL would be generated for it, ensuring proper optimization for search engines and making it easier for CMS administrators to edit any page.

*Dynamic Routes*

To create dynamic routes, I dynamically generated route definitions based on the available content categories. This allowed me to scale the routing system as new categories were added.

This meant that whenever a new category, such as a new type of insurance provider, needed a web page, that page did not have to be created manually in the codebase. Instead, the system would automatically generate the page and assign it a unique URL. For example, if a CMS administrator added a new insurance provider called "Aetna," the system would create a page for it with a URL like "luxuryrehabs.com/insurance/aetna."

*GraphQL Integration*

GraphQL played a crucial role in this process by providing the necessary data to populate content pages for insurance offerings, treatment services, and therapies offered by medical facilities. When a user accessed a particular URL, GraphQL queries were executed to fetch the relevant content for that category. This seamless integration ensured that the content remained up-to-date and accurate.


These routes were achieved for 3 categories (insurance, treatment therapies, and treatment services), each critical decision points in users seeking treatment for addiction or mental health issues.

This is the final presentation of the insurance route. 
<img src="https://i.imgur.com/OJd1ebt.png">

The routes for treatment services and treatment therapy offerings followed the same layout as the insurance pages and use the same components as well, including popular destinations tagged with the relevant category as well as a feed of results for centers offering the chosen category.

<img src="https://i.imgur.com/HnydjmI.png">

<img src="https://i.imgur.com/VsavQRj.png">

<b>User Feedback</b>

User feedback was overwhelmingly positive. Users reported it easier to discover relevant content, and administrators appreciated the simplified content management process.

<b>Benefits and Achievements</b>

- 30% increase in organic traffic with the introduction of insurance pages, speaking to a primary user need
- 15% increase in conversion rates, resulting from insurance being a key point in influencing a user to make an inquiry
- Reduced customer support queries regarding insurance offerings by 10%

