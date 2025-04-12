# Optimizing User Journeys for a Digital Healthcare Platform with a Dynamic Patient Assessment Form

## Project Background
The platform was a digital health service designed to connect people with behavioral health and addiction treatment providers. Users—often in urgent or sensitive situations—had difficulty finding appropriate care due to overwhelming content and unclear pathways. To streamline the experience, I implemented a dynamic, multi-step assessment form that personalized the search and helped users connect with relevant providers more efficiently.

Disclaimer: Code samples have been abstracted and certain details redacted or generalized to respect confidentiality agreements. This case study is intended to demonstrate technical problem-solving and development approach.

<b>Role</b>: Development Lead, Project Manager

<b>Collaborators</b>: Product Manager, UX Designers, Clinical Research Director to approval assessment questions and options

**Tech Stack:** React,js, TypeScript, Tailwind CSS, Gatsby, WordPress, Jest, Cloudflare

## Business Challenge  
Users faced challenges when trying to navigate through a large volume of content to find relevant treatment providers, leading to:  

- **Irrelevant Search Results**: Without personalized filtering, users frequently encountered unsuitable treatment options, causing frustration 
- **Overwhelming Navigation**: The absence of clear guidance made it difficult for users to refine their searches or even know where to begin, resulting in confusion and abandonment  
- **Inefficient Experience**: Users often felt "lost" during the search process, negatively affecting engagement and retention  

## User Feedback Insights  
Usability tests and user interviews were conducted to uncover pain points, revealing the following insights:  

- Users struggled with site navigation and comprehending terminology  
- Many felt disoriented when attempting to narrow down their search for relevant treatment providers

### Agile Project Management  

**Planning & Setup:**  
- Wrote product requirements documents (PRDs) in Jira to align stakeholders and define scope  
- Secured stakeholder buy-in and timeline budget approval prior to kickoff  
- Broke down the project into prioritized, actionable tasks for the development team  
**Execution:**  
- Created user stories with detailed acceptance criteria in Linear to guide development  
- Collaborated with engineering, UX, and clinical teams to refine user stories and ensure feasibility  

**Delivery & Adoption:**  
- Presented demos to cross-functional teams and leadership throughout the project  
- Trained stakeholders on the feature and provided documentation on form inputs and logic to support internal adoption 

## Implementation

### Multi-Step Form
Developed a dynamic form that asks users about location (IP-based) and treatment needs. This allows for customized search results based on responses.

### Location Filter
Implemented a location-based radius filter (10, 150, 250, 500 miles, worldwide) based on user IP and preferences.

### User Intent and Preference Questions
- Added multiple questions in the intake form to gather relevant user data, such as location, treatment preferences, and user intent (e.g., self, loved one, or professional).
- All responses were stored in Firestore to dynamically filter and tailor the results based on user input.
- Developed logic using React hooks to show conditional content and adjust results according to the answers provided, improving the accuracy and relevance of search results.

### UI Enhancements for Mobile
Optimized form UI to ensure accessibility and ease of use across devices along with a clear CTA.


### Filter Wizard Integration:
- Added a multi-step intake form to the `/browse/` page to gather relevant user data (location, type of treatment seeker) before presenting search results.
- Implemented ReactJS to build dynamic components for the form, with state management handled using React's Context API for cross-component data flow.
- Used TypeScript to ensure type safety and prevent potential runtime errors during form submissions and state transitions.
- Integrated the Firestore database to store user inputs and dynamically filter the available results based on responses.

````tsx
// context/FormContext.tsx
const FormContext = createContext<FormState | null>(null);

export const FormProvider = ({ children }) => {
  const [formState, setFormState] = useState(initialState);

  return (
    <FormContext.Provider value={{ formState, setFormState }}>
      {children}
    </FormContext.Provider>
  );
};

### Location-Based Filtering:
- Leveraged GeoIP lookup via the user's IP address to identify the user’s location automatically. Integrated Cloudflare's Geolocation API to enhance this feature.
- Developed a radius-based filter system using GraphQL queries to fetch data specific to the location, with options for 10, 150, 250, and 500-mile radii or worldwide options.
````tsx
query GetProvidersByRadius($lat: Float!, $lng: Float!, $radius: Int!) {
  providersByLocation(lat: $lat, lng: $lng, radius: $radius) {
    name
    distance
    specialties
  }
}
````
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
- **10% increase in organic search traffic (SEO):** Improved visibility and discoverability, driving more organic traffic to the site.
- **15% improvement in filter accuracy:** More relevant and precise results for users, enhancing the quality of the search functionality.
- **20% increase in completed assessments on mobile:** Mobile UI optimization contributed to higher engagement and completion rates.
- **5% increase in successful treatment provider connections:** Users experienced higher relevancy in their search results, leading to more successful connections.
