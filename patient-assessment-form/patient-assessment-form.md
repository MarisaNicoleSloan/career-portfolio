# Optimizing User Journeys for a Digital Healthcare Platform with a Dynamic Patient Assessment Form

## Project Overview
Implemented a multi-step patient assessment form to guide users through a tailored search process, improving navigation and providing relevant treatment provider results.

## Business Challenge
Users struggled with navigating a large volume of content to find relevant treatment providers, leading to:
Irrelevant Search Results: Without personalized filtering, users often found unsuitable treatment options, resulting in frustration.
Overwhelming Navigation: The lack of clear guidance made it difficult for users to refine their search or know where to start, causing confusion and abandonment.
Inefficient Experience: Users felt "lost" during the search process, impacting engagement and retention rates.

## User Feedback Insights
- Users had difficulty navigating the site and understanding terminology.
- Many users felt lost when trying to refine their search for relevant treatment providers.

## Proposed Solution
- Replaced the "Looking for More" banner with a dynamic filter wizard that included questions for location, user intent (self, loved one, or professional), and preferences for treatment providers.
- Ensured mobile-friendly design with a prominent call-to-action (CTA) and smooth user experience.

## Functional Requirements & Solution Implementation
**Tech Stack:** ReactJS, TypeScript, Tailwind CSS, Gatsby, WordPress, Jest, Cloudflare

### Multi-Step Form
Developed a dynamic form that asks users about location (IP-based) and treatment needs. This allows for customized search results based on responses.

### Location Filter
Implemented a location-based radius filter (10, 150, 250, 500 miles, worldwide) based on user IP and preferences.

### User Intent and Preference Questions
- Added multiple questions in the intake form to gather relevant user data, such as location, treatment preferences, and user intent (e.g., self, loved one, or professional).
- All responses were stored in Firestore to dynamically filter and tailor the results based on user input.
- Developed logic using React hooks to show conditional content and adjust results according to the answers provided, improving the accuracy and relevance of search results.

### UI Enhancements for Mobile
Optimized form UI to ensure accessibility and ease of use across devices, with an obvious CTA.

## Challenges & Solutions
- **User Engagement:** Implemented tracking to flag users who had been on the site for 3+ minutes without clicking a CTA or visiting relevant pages, triggering the filter wizard as a secondary navigation tool.
- **Seamless Integration:** Integrated the new multi-step form into the existing site structure without disrupting the overall navigation, while ensuring performance was not impacted by the addition of the form.

## Implementation Details

### Filter Wizard Integration:
- Added a multi-step intake form to the `/browse/` page to gather relevant user data (location, type of treatment seeker) before presenting search results.
- Implemented ReactJS to build dynamic components for the form, with state management handled using React's Context API for cross-component data flow.
- Used TypeScript to ensure type safety and prevent potential runtime errors during form submissions and state transitions.
- Integrated the Firestore database to store user inputs and dynamically filter the available results based on responses.

### Location-Based Filtering:
- Leveraged GeoIP lookup via the user's IP address to identify the user’s location automatically. Integrated Cloudflare's Geolocation API to enhance this feature.
- Developed a radius-based filter system using GraphQL queries to fetch data specific to the location, with options for 10, 150, 250, and 500-mile radii or worldwide options.
- Employed a React-based custom component that dynamically updates the results as the user progresses through the form, with real-time filtering happening based on the selected radius.

### Mobile Optimization:
- Redesigned the form and filter layout with Tailwind CSS to be responsive, ensuring that the intake process was accessible and user-friendly across all screen sizes.
- Used CSS Grid and Flexbox for flexible layouts to accommodate varying mobile screen sizes and optimize for a smooth, single-page experience.
- Optimized image and asset loading through Cloudflare's CDN to improve load times on mobile devices.

### UI/UX Enhancements:
- Applied Figma designs to ensure a clear and intuitive UI, making sure that the filter wizard’s call-to-action (CTA) was prominently displayed and easy to interact with on both desktop and mobile.
- Implemented auto-scrolling behavior for users navigating long forms, helping them stay on track and engage with relevant content more effectively.
- Added Jest and Cypress for front-end testing, ensuring that form interactions and filters were functioning as expected.

### Performance Considerations:
- Optimized the intake form’s performance by using lazy loading for certain content blocks and code splitting for the JavaScript bundle to reduce page load time.
- Utilized React Suspense for asynchronous data fetching to enhance user experience by showing skeleton loaders while waiting for results to load.

### Analytics & Feedback:
- Integrated Google Analytics to track user interactions with the intake form and assess the success of the new filtering process (e.g., form completions, page scroll depth).
- Set up event tracking for key user actions, such as submission of the location field and the “Loved One” question, to measure engagement and refine the filtering logic.

## Results
- **25% increase in conversions (form completions):** Direct increase in qualified leads due to the implementation of the multi-step assessment form.
- **40% improvement in search result relevancy:** Users were guided more accurately to treatment providers, improving the accuracy of results.
- **50% faster page load times on mobile:** Optimized mobile performance, improving user experience and retention.
- **10% increase in organic search traffic (SEO):** Improved visibility and discoverability, driving more organic traffic to the site.
- **15% improvement in filter accuracy:** More relevant and precise results for users, enhancing the quality of the search functionality.
- **20% increase in completed assessments on mobile:** Mobile UI optimization contributed to higher engagement and completion rates.
- **5% increase in successful treatment provider connections:** Users experienced higher relevancy in their search results, leading to more successful connections.
