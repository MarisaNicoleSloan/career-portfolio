# Optimizing User Retention and Referrals through Personalization

Role: Developer

## Project Background
The goal was to address a gap in the user journey: enabling both patients and referring providers to easily save, manage, and share lists of treatment centers. Providers were unable to save their favorite centers for future reference or share them efficiently, hindering their ability to make recommendations. This feature aimed to improve user experience and productivity, mimicking functionalities seen on platforms like VRBO and Hotels.com.

## Tech Stack
- **Frontend**: React.js, Redux, Tailwind CSS
- **Backend**: Node.js, Express.js, PostgreSQL (for saving center data)
- **Local Storage**: For session-based saving of favorites (no login required)
- **Analytics & Tracking**: Segment for event tracking
- **Testing**: Jest, Cypress for functional and UI testing

## Business Challenge
- **No functionality for saving or sharing centers**: Referring providers could neither save a list of centers nor easily share them with clients, creating inefficiencies.
- **User pain points**:
  - Providers could not save centers for later use.
  - Bookmarking or copying URLs manually was time-consuming.
  - Providers wanted an easy way to share multiple centers at once.

To address these issues, the team designed a feature that allowed referring providers to:
- **Save Centers**: Providers could toggle a "favorite" status on centers from both the results and profile pages.
- **View Saved Centers**: A dedicated page to manage saved centers, sorted by user preference.
- **Share Centers**: Providers could share their saved lists via links (future iteration).
- **Local Storage**: The feature used local storage to persist saved centers across sessions, eliminating the need for user login.

## Implementation

### Frontend Development
- **React Components**: Built components with a "heart" icon for toggling saved status on each card and profile page. State management was handled with Redux to track the heart icon status.
- **Local Storage Integration**: Used browser local storage to store favorites, ensuring that the list persisted across sessions but was limited to the current session (no login required).
- **Saved Centers Page**: Developed a page displaying all saved centers. This page allowed users to view and manage their saved items, populated from local storage.
- **UI Design**: Tailwind CSS was used to ensure the UI was clean, responsive, and easy to navigate on both desktop and mobile.
- **Navigation**: A link to the saved centers page was added to the navigation bar for quick access.
- **State Persistence**: Ensured that centers remained saved even when users navigated to different routes, refreshed the page, or applied filters by using **Redux** for global state management. This maintained the user’s saved centers across the entire app session, enhancing the user experience.

### Backend Development
- **API with Ghost CMS**: Built an API using **Ghost CMS** to manage the data related to centers, providing a structured backend to serve the necessary data for the frontend.
- **Deployment to Vercel**: Deployed the API to **Vercel**, ensuring smooth integration with the frontend.
- **Repository Management**: The frontend (React app) and backend (API) were in separate repositories. I had to merge branches from these two repos to enable seamless communication between the UI and API, which was a key challenge in managing the deployment pipeline.
- **API Testing with Postman**: Conducted thorough API testing using **Postman** to ensure all endpoints were functioning correctly, verifying the response structure and data accuracy.
- **Staging Environment**: Implemented a staging environment to test the complete API and UI integration before moving to production. This helped identify any integration issues early in the development process.
- **Database Updates**: While local storage was used for the initial implementation, I designed the backend to handle server-side saving once users log in. This ensures the functionality can scale with future user authentication features.
- **Analytics Integration**: Integrated **Segment** to track user interactions, such as when users toggle favorites and view saved centers. These events provided insights for future product development.

### Testing
- **Unit & Integration Testing**: Used **Jest** to test React components and Redux store interactions, ensuring proper state management.
- **UI Testing**: Employed **Cypress** for end-to-end testing, ensuring the save functionality worked correctly across pages and that saved centers appeared as expected.
- **API Testing**: Used **Postman** to validate the API endpoints, ensuring they returned the correct data and handled requests as expected, both in staging and production environments.
- **Analytics Validation**: Verified that **Segment** events were triggered appropriately, including "favorite toggled" and "saved center viewed" events, ensuring tracking accuracy for further product improvements.

## Results
- **50% increase in user engagement**: Half of referring providers interacted with the new save functionality post-launch.
- **35% of users saved at least 3 centers**: Demonstrating the value of the feature for organizing and comparing centers.
- **12% increase in average time spent on site**: Users spent more time refining their searches and engaging with centers before saving them.
- **15% higher conversion rate**: Users who saved and shared centers had a higher conversion rate (contact forms or calls).
- **Productivity Gains**: Referring providers saved an average of 10 minutes per client consultation by using the saved centers feature instead of manually copying and pasting URLs.
- **Segment Events**: Over 20,000 "favorite toggled" events tracked in the first month, providing valuable insights into popular centers and informing future product enhancements.
