## Optimizing User Journeys for a Digital Healthcare Platform: A Dynamic Patient Assessment Form

### Project Background

The platform was a digital health service designed to connect people with behavioral health and addiction treatment providers. Users—often in urgent or sensitive situations—had difficulty finding appropriate care due to overwhelming content and unclear pathways. As a Development Lead and acting Project Manager for this initiative, I led the implementation of a dynamic, multi-step assessment form that personalized the search and helped users connect with relevant providers more efficiently. This initiative aligned with the product vision of accessible and personalized care.

**Collaborators:** Product Manager, UX Designers, Clinical Research Director (approval of assessment questions and options)

**Tech Stack:** React.js, TypeScript, Tailwind CSS, Gatsby, WordPress, Jest, Cloudflare

* Disclaimer: Code samples have been abstracted, and certain details redacted or generalized to respect confidentiality agreements. This case study demonstrates technical problem-solving and development approach.

### The Problem

When searching for behavioral healthcare treatment, patients or their loved ones prioritize factors such as location, cost, specialization, and treatment approach. However, users faced significant challenges in navigating the platform:

* **Irrelevant Search Results:** Without personalized filtering, users frequently encountered unsuitable treatment options, causing frustration. The existing search bar, while excellent for providers familiar with the behavioral healthcare industry, relied on users knowing specific care models, treatment types, and insurance details.
* **Overwhelming Navigation:** The absence of clear guidance made it difficult for users to refine their searches or even know where to begin, resulting in confusion and abandonment. Users were overwhelmed by the sheer amount of subcategories, such as the 50+ specializations under the "Conditions" facet.
* **Inefficient Experience:** Users often felt "lost" during the search process, negatively affecting engagement and retention.

Usability tests and user interviews confirmed these pain points. For example, users reported feeling disoriented when attempting to narrow down their search, and customers with a profile on the site were unsure how to best attract traffic to their center profile. These findings highlighted that the existing search experience, while robust, did not effectively cater to patients unfamiliar with the complexities of behavioral healthcare terminology and options.

### Solution: Dynamic Patient Assessment Form

To address these challenges, I led the development of a dynamic, multi-step assessment form. This form guides users through a series of questions about their location (using IP-based geolocation) and treatment needs, progressively gathering information to customize search results. This approach was chosen based on user research that highlighted confusion with complex filters. By focusing on the most crucial factors initially (location and immediate treatment needs), we reduced cognitive load and improved the user experience.

The key features and implementation details of the solution include:

* **Multi-Step Form Development:**
    * Developed using React.js, the form dynamically renders content and manages complex state using React's Context API for efficient cross-component data flow. TypeScript was used to ensure type safety and prevent runtime errors.
    * Implemented logic using React hooks to conditionally display subsequent questions and tailor results based on user input.
    * Integrated with the Firestore database to store user inputs and dynamically filter the available results.
    * The form was integrated into the `/browse/` page, a primary entry point for users seeking providers.
* **Location-Based Filtering:**
    * Leveraged GeoIP lookup via the user's IP address, integrated with Cloudflare's Geolocation API, to automatically identify the user’s location.
    * Developed a radius-based filter system using GraphQL queries to fetch data specific to the location. The `GetProvidersByRadius` GraphQL query was optimized with indexed fields in our database to ensure efficient retrieval of providers within the specified radius. Caching mechanisms were implemented at the Cloudflare level to reduce latency for frequently accessed location-based searches.
    * Implemented a React-based custom component that dynamically updates the results as the user progresses through the form, with real-time filtering based on the selected radius.

    ```graphql
    query GetProvidersByRadius($lat: Float!, $lng: Float!, $radius: Int!) {
      providersByLocation(lat: $lat, lng: $lng, radius: $radius) {
        name
        distance
        specialties
      }
    }
    ```

* **User Intent and Preference Questions:**
    * Added multiple questions to the intake form to gather relevant user data, such as treatment preferences and user intent (e.g., self, loved one, or professional).
    * Stored all responses in Firestore to dynamically filter and tailor the results based on user input.
    * Developed logic using React hooks to show conditional content and adjust results according to the answers provided, improving the accuracy and relevance of search results.
* **UI/UX Enhancements:**
    * Applied Figma designs to ensure a clear and intuitive UI, with a prominent call-to-action (CTA) for the filter wizard.
    * Redesigned the form and filter layout with Tailwind CSS to be responsive, ensuring that the intake process was accessible and user-friendly across all screen sizes.
    * Used CSS Grid and Flexbox for flexible layouts to accommodate varying mobile screen sizes and optimize for a smooth, single-page experience.
    * Optimized image and asset loading through Cloudflare's CDN to improve load times on mobile devices.

The form is designed to adapt to both high-intent users (those who know their desired treatment options) and low-intent users (those who are still exploring their needs).

* **High-Intent User Flow:** [Watch the walkthrough video on Loom (opens in new tab)](https://www.loom.com/share/52a1578bd9a249058880b79ac10c5005)
* **Low-Intent User Flow:** [Watch the walkthrough video on Loom (opens in new tab)](https://www.loom.com/share/0728c4a8403f441382ae000707d069c6)

* **Performance Considerations:**
    * Optimized the intake form’s performance by using lazy loading for certain content blocks and code splitting for the JavaScript bundle to reduce page load time.
    * Utilized React Suspense for asynchronous data fetching to enhance user experience by showing skeleton loaders while waiting for results to load.
    * Added Jest and Cypress for front-end testing, ensuring that form interactions and filters were functioning as expected.
* **Analytics & Feedback:**
    * Integrated Google Analytics to track user interactions with the intake form and assess the success of the new filtering process (e.g., form completions, page scroll depth).
    * Set up event tracking for key user actions, such as submission of the location field and the “Loved One” question, to measure engagement and refine the filtering logic.
    * Analytics data on form completion rates, drop-off points, and search result clicks was used to iterate on the form questions and filtering logic. For example, initial data showed a higher drop-off rate on specific questions, leading to revisions in the wording and order.

### Results

The implementation of the dynamic patient assessment form resulted in significant improvements across key metrics:

* **25% increase in conversions (form completions):** This direct increase in qualified leads demonstrates the effectiveness of the form in guiding users to the appropriate providers.
* **40% improvement in search result relevancy:** Users were more accurately matched with treatment providers, indicating that the form effectively captured their needs and preferences.
* **10% increase in organic search traffic (SEO):** Improved visibility and discoverability, driving more organic traffic to the site.
* **15% improvement in filter accuracy:** The form provided more relevant and precise results, enhancing the overall quality of the search functionality.
* **20% increase in completed assessments on mobile:** The mobile UI optimization contributed to higher engagement and completion rates, demonstrating the success of the responsive design.
* **5% increase in successful treatment provider connections:** Users experienced higher relevancy in their search results, leading to more successful connections.

These results demonstrate the significant impact of the dynamic assessment form on improving the user experience and achieving the platform's goal of connecting patients with timely and appropriate care.

### Lessons Learned

This project provided several key takeaways:

* **The importance of user-centered design:** The success of the form highlights the critical role of user research and iterative design in developing effective solutions.
* **The power of progressive filtering:** Guiding users through a series of simple questions can be more effective than presenting them with a complex set of filters.
* **Effective communication and collaboration:** Close collaboration with the product manager, UX designers, and clinical team was crucial for the successful execution of this project.

By focusing on user needs and leveraging technology to create a more personalized and intuitive experience, we were able to significantly improve the platform's effectiveness in connecting patients with the care they need.

