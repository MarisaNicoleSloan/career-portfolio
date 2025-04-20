# Bookmarking Feature for Healthcare Providers: Optimizing User Retention and Referrals Through Personalization

<b>Role</b>: Development Lead, Project Manager

<b>Collaborators</b>: Product Designer, Product Manager, B2B Sales Director

> **Disclaimer**: Code samples have been abstracted and certain details redacted or generalized to respect confidentiality agreements. This case study is intended to demonstrate technical problem-solving and development approach.

## Project Background
A clear gap existed in the patient journey for a healthcare platform's appointment service: enabling both patients and referring providers to easily save, manage, and share lists of treatment centers. Providers were unable to save their favorite centers for future reference or share them efficiently, hindering their ability to make recommendations.

## Tech Stack
- **Frontend**: React.js, Redux, Tailwind CSS
- **Backend**: Node.js, Express.js, PostgreSQL (for querying center data)
- **Local Storage (Browser Storage)**: For session-based saving of favorites (no login required)
- **Analytics & Tracking**: Segment for event tracking
- **Testing**: Jest, Cypress, and LambdaTest for functional, cross-browser, and UI testing

# Business Challenge
The system lacked functionality for saving and sharing centers, leading to inefficiencies for referring providers. Internal research and provider interviews revealed that over 80% of providers manually tracked options using spreadsheets or printed notes. Key pain points included:

- No way to save centers for later reference
- Time-consuming process of bookmarking or copying URLs
- No simple method to share multiple centers at once

This validated the business value of implementing a native Favorites feature.

# Solution
To address these challenges, the product and engineering teams proposed a feature allowing providers to do the following: 

- **Save Centers:** Toggle a “favorite” status on centers directly from the results and profile pages.  
- **View Saved Centers:** Access a dedicated page to manage and sort saved centers based on user preference.  
- **Share Centers:** Share saved lists via links (planned for future iterations).  
- **Local Storage:** Use local storage to persist saved centers across sessions, eliminating the need for login.  

The initial prioritization focused on the "Save" and "View" functionalities to address the most immediate pain points identified in user research – the inability to save and easily access preferred centers. The "Share Centers" functionality was planned for a future iteration to allow for validation of the core saving mechanism and gather user feedback before tackling the complexities of sharing.

## Implementation

### Frontend Development
#### UX Collaboration on a Modular Design System
I collaborated closely with the product designer to create a seamless desktop and mobile experience using a component-based architecture. Designs in Figma reflected a robust design system focused on clarity and responsiveness. I built interactive elements, like the heart icon that enlarged on hover as an optimistic UI pattern to provide immediate visual feedback. Each component was aligned with our shared design library for scalable reuse across the application.

To manage the heart icon's state, I used Redux to ensure consistency across all components, addressing the challenge of synchronizing the icon’s saved status across multiple components.

```tsx
// TypeScript version with type annotations
interface Center {
  id: string;
  name: string;
  url: string;
}

const toggleFavorite = (id: string): void => {
  dispatch({ type: 'TOGGLE_FAVORITE', payload: id });
};

```
#### Local Storage Integration
Used browser local storage to persist favorites across sessions, ensuring users could save centers without needing a login. However, local storage can only store data up to a certain limit, which led to issues when users saved a large number of centers. To resolve this, I limited the saved data to only essential center information (name, ID, and URL).

```tsx
const saveToLocalStorage = (center: Center): void => {
  const savedCenters: Center[] = JSON.parse(localStorage.getItem('favorites') || '[]');
  if (!savedCenters.find(c => c.id === center.id)) {
    savedCenters.push({ name: center.name, id: center.id, url: center.url });
    localStorage.setItem('favorites', JSON.stringify(savedCenters));
  }
};
```

#### API Optimization
Initially, I used fetch to interact with the backend API. However, as the project progressed, I encountered challenges with managing request cancellations and handling error responses. For example, canceling requests when a user quickly navigated between different pages caused potential issues with unnecessary API calls.

```tsx
const fetchCenters = async (): Promise<void> => {
  try {
    const response = await fetch('/api/centers');
    const data: Center[] = await response.json();
    setCenters(data);
  } catch (error) {
    console.error('Error fetching centers:', error);
  }
};
```

After switching to axios, I was able to handle requests more effectively, especially with support for request cancellation and easier error handling. This change also made it easier to manage request configurations, such as headers, and to handle different response formats. This was particularly useful when dealing with more complex API responses that required custom error handling.

```tsx
import axios from 'axios';

const fetchCenters = async (): Promise<void> => {
  try {
    const response = await axios.get<Center[]>('/api/centers');
    setCenters(response.data);
  } catch (error) {
    console.error("Error fetching centers:", error);
  }
};

```

This change improved the reliability and maintainability of the API interactions, allowing for easier handling of edge cases like timeouts and retries.

#### Saved Centers Page
Developed a page to manage saved centers. The challenge here was ensuring the page remained responsive while displaying a dynamic number of saved centers. Using Tailwind CSS, I created a flexible layout that adjusted based on screen size, making it easy for users to interact with the saved centers on both desktop and mobile devices.

#### State Persistence
Ensured saved centers persisted across page refreshes using Redux. One challenge was managing the state when users navigated between pages or applied filters. This was solved by saving the state in the Redux store and using useEffect to rehydrate the state on page load.

```tsx
useEffect(() => {
  dispatch(loadFavoritesFromLocalStorage());
}, []);
```

### Backend Development

#### API Development
Built an API using the Ghost API to manage center data. A common challenge with API integration was handling CORS errors when the frontend tried to fetch data from the backend. This was resolved by modifying the API to include the necessary CORS headers.

```tsx
app.use((req, res, next) => {
  res.header('Access-Control-Allow-Origin', '*');
  res.header('Access-Control-Allow-Methods', 'GET, POST');
  next();
});
```

#### Deployment to Vercel
Deployed the API to **Vercel**, ensuring smooth integration with the frontend

#### Repository Management
The frontend (React app) and backend (API) were in separate repositories. The two branches were then merged together to enable seamless communication between the UI and API and ensure a smooth deployment pipeline. 

#### Staging Environment
Implemented a staging environment to test the complete API and UI integration before moving to production. This helped identify any integration issues early in the development process.

#### Database Updates
Initially, local storage handled saved centers, but as part of the future user authentication features, I designed the backend to allow server-side storage. The challenge was migrating data from local storage to the backend without causing data loss. This was done by creating an endpoint to synchronize local favorites with the database once the user logged in.

#### Analytics Integration and Validation
Integrated Segment to track user interactions. One challenge was ensuring event data was tracked accurately across multiple components, especially when users toggled favorites. To resolve this, I added event triggers on each toggle action.

```tsx
const trackFavoriteToggle = (center: Center): void => {
  analytics.track('Favorite Toggled', {
    centerId: center.id,
    centerName: center.name,
  });
};
```
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

## Results
- **20% increase in user engagement**: Half of referring providers interacted with the new save functionality post-launch, a significant shift from the 80% who previously relied on manual tracking
- **35% of users saved at least 3 centers**: Demonstrating the value of the feature for organizing and comparing centers
- **12% increase in average time spent on site**: Users spent more time refining their searches and engaging with centers before saving them
- **15% higher conversion rate**: Users who saved and shared centers had a higher conversion rate (contact forms or calls)
- **Productivity Gains**: Referring providers saved an average of 10 minutes per client consultation by using the saved centers feature instead of manually copying and pasting URLs
- **High Feature Adoption**: Over 20,000 "favorite toggled" events tracked in the first month, providing valuable insights into popular centers and informing future product enhancements

## Lessons Learned & Future Improvements
- <b>Prioritize User Workflow:</b> The importance of deeply understanding and prioritizing the user's workflow (in this case, the referring provider) was crucial to the success of this feature.

- <b>Iterative Development with User Feedback:</b> The iterative approach, incorporating feedback from internal stakeholders and the pilot group, allowed for valuable adjustments and a more refined final product.

- <b>Value of a Robust Testing Strategy:</b> The combination of unit, integration, cross-browser, and end-to-end testing ensured a high-quality, reliable feature across different environments.

- <b>Future Enhancements:</b> Implement the "Share Centers" functionality to further streamline the referral process.
