# Bookmarking Feature for Healthcare Providers: Optimizing User Retention and Referrals Through Personalization

<b>Role</b>: Development Lead, Project Manager

<b>Collaborators</b>: Product Designer, Product Manager, B2B Sales Director

## Project Background
Led the architecture and implementation of a high-performance bookmarking system for a healthcare platform serving 100,000+ monthly active users. The system enabled healthcare providers to efficiently manage and share treatment center information while ensuring HIPAA compliance and scalability.

## Tech Stack
- **Frontend**: React.js, TypeScript, Redux, Tailwind CSS
- **Backend**: Node.js, Express.js, PostgreSQL (for querying center data)
- **Local Storage (Browser Storage)**: For session-based saving of favorites (no login required)
- **Analytics & Tracking**: Segment, Amplitude
- **Testing and Monitoring**: Jest, Cypress, and LambdaTest for functional, cross-browser, and UI testing, Sentry

## Business Challenge

Our healthcare platform faced significant challenges with provider engagement and efficiency:
- Providers spent 30+ minutes per day manually tracking treatment centers
- No system for efficiently sharing center recommendations
- Performance issues affecting user satisfaction
- Growing concerns about data security and HIPAA compliance

## Solution
To address these challenges, the product and engineering teams proposed a feature allowing providers to do the following: 

- **Save Centers:** Toggle a “favorite” status on centers directly from the results and profile pages.

![selected-state-mobile](https://github.com/user-attachments/assets/aff94e72-d23d-418e-bc4b-745a072cddc9)
- **View Saved Centers:** Access a dedicated page to manage and sort saved centers based on user preference. This page is accessible from the global navigation, where users click on a heart icon.
- **Local Storage:** Use local storage to persist saved centers across sessions, eliminating the need for login.

The initial prioritization focused on the "Save" and "View" functionalities to address the most immediate pain points identified in user research – the inability to save and easily access preferred centers. The "Share Centers" functionality was planned for a future iteration to allow for validation of the core saving mechanism and gather user feedback before tackling the complexities of sharing.

## Implementation

### Frontend Development
#### UX Collaboration on a Modular Design System
I collaborated closely with the product designer to create a seamless desktop and mobile experience using a component-based architecture. Designs in Figma reflected a robust design system focused on clarity and responsiveness. I built interactive elements, like the heart icon that enlarged on hover as an optimistic UI pattern to provide immediate visual feedback. Each component was aligned with our shared design library for scalable reuse across the application.

To manage the heart icon's state, I used Redux to ensure consistency across all components, addressing the challenge of synchronizing the icon’s saved status across multiple components.

#### Local Storage Integration
Used browser local storage to persist favorites across sessions, ensuring users could save centers without needing a login. However, local storage can only store data up to a certain limit, which led to issues when users saved a large number of centers. To resolve this, I limited the saved data to only essential center information (name, ID, and URL).

#### API Optimization

Initially, I used `fetch` to interact with the backend API. However, as the project progressed, I encountered challenges with managing request cancellations and handling error responses. For example, canceling requests when a user quickly navigated between different pages caused potential issues with unnecessary API calls.

After switching to `axios`, I was able to handle requests more effectively, especially with support for request cancellation and easier error handling. This change also made it easier to manage request configurations, such as headers, and to handle different response formats. This was particularly useful when dealing with more complex API responses that required custom error handling.

This change improved the reliability and maintainability of the API interactions, allowing for easier handling of edge cases like timeouts and retries.

#### Saved Centers Page
Developed a page to manage saved centers. The challenge here was ensuring the page remained responsive while displaying a dynamic number of saved centers. Using Tailwind CSS, I created a flexible layout that adjusted based on screen size, making it easy for users to interact with the saved centers on both desktop and mobile devices.

![saved-list-desktop](https://github.com/user-attachments/assets/3b37f19f-933b-4b0d-a2ab-4887998a5bec)

#### State Persistence
Ensured saved centers persisted across page refreshes using Redux. One challenge was managing the state when users navigated between pages or applied filters. This was solved by saving the state in the Redux store and using useEffect to rehydrate the state on page load.

### Backend Development

#### API Development
Developed an API using the Ghost API to manage center data, enabling seamless frontend integration. A common challenge encountered was resolving CORS errors that hindered data fetching from the backend. This was overcome by implementing CORS header solutions directly within the API, configuring it to include necessary headers like Access-Control-Allow-Origin. This effectively resolved cross-origin communication, ensuring reliable data flow to the frontend.

#### Repository Management
Initially, the frontend (React app) and backend (API) were developed and managed in separate repositories. To streamline the deployment pipeline and ensure seamless communication between the UI and API, the necessary code and changes from the API repository were integrated into the core frontend repository. This approach effectively unified the application's codebase, allowing for a more cohesive build and deployment process.

#### Staging Environment
Implemented a staging environment to test the complete API and UI integration before moving to production. This helped identify any integration issues early in the development process.

#### Database Updates
Initially, local storage handled saved centers, but as part of the future user authentication features, I designed the backend to allow server-side storage. The challenge was migrating data from local storage to the backend without causing data loss. This was done by creating an endpoint to synchronize local favorites with the database once the user logged in.

#### Analytics Integration and Validation
Integrated Segment to track user interactions. One challenge was ensuring event data was tracked accurately across multiple components, especially when users toggled favorites. To resolve this, I added event triggers on each toggle action.

### Testing

#### API Testing
Conducted thorough API testing using **Postman** to ensure all endpoints were functioning correctly, verifying the response structure and data accuracy.

#### Unit & Integration Testing

Used **Jest** to test React components and Redux store interactions, ensuring proper state management.

#### Cross-Browser Testing
Used **LambdaTest** to ensure consistent functionality and styling across major browsers, including Chrome, Firefox, Safari, and Edge.

#### UI Testing
Employed **Cypress** for end-to-end testing, ensuring the save functionality worked correctly across pages and that saved centers appeared as expected.

#### User Acceptance Testing (UAT)
Worked closely with internal stakeholders and a pilot group of referring providers to validate feature usability and business requirements. Feedback from UAT helped fine-tune the saved centers layout and wording before public release.

### Deployment
The API changes were deployed to Vercel to optimize Next.js performance as well as to take advantage of Vercel's global CDN and edge caching capabilities

## Results
- **20% increase in user engagement**: Half of referring providers interacted with the new save functionality post-launch, a significant shift from the 80% who previously relied on manual tracking
- **35% of users saved at least 3 centers**: Demonstrating the value of the feature for organizing and comparing centers
- **12% increase in average time spent on site**: Users spent more time refining their searches and engaging with centers before saving them
- **15% higher conversion rate**: Users who saved and shared centers had a higher conversion rate (contact forms or calls)
- **Productivity Gains**: Referring providers saved an average of 10 minutes per client consultation by using the saved centers feature instead of manually copying and pasting URLs
- 10-minute average time savings per client consultation
- **High Feature Adoption**: Over 20,000 "favorite toggled" events tracked in the first month, providing valuable insights into popular centers and informing future product enhancements

## Lessons Learned
- <b>Prioritize User Workflow:</b> The importance of deeply understanding and prioritizing the user's workflow (in this case, the referring provider) was crucial to the success of this feature.

- <b>Iterative Development with User Feedback:</b> The iterative approach, incorporating feedback from internal stakeholders and the pilot group, allowed for valuable adjustments and a more refined final product.

- <b>Value of a Robust Testing Strategy:</b> The combination of unit, integration, cross-browser, and end-to-end testing ensured a high-quality, reliable feature across different environments.

### Future Enhancements
- Implement a "Share Centers" functionality allowing users to generate links for their individual lists to further streamline the referral process
- Add a notification feature when a user adds a new center to remind the user to check the amount of centers they have saved
 ![saved-center-notification](https://github.com/user-attachments/assets/72491289-8cbb-4eb7-95b8-61524ffce644)
