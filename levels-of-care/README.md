# Dynamic Treatment Education Feature for a Digital Healthcare Platform: Driving Adoption Through Product Enablement

## Project Background
Implemented a dynamic treatment information module across 4,000+ pages, aiming to improve user understanding of mental health and addiction treatment options. The module aimed to present clear, structured data on the various levels of care available at facilities, such as outpatient therapy and inpatient care, enhancing the patient journey from initial inquiry to treatment selection.

<b>Role</b>: Development Lead, Project Manager

<b>Collaborators</b>: UI Designer, Product Manager, Chief Product Officer (for buy-in and budget), Research Specialists for clinical review

Disclaimer: Code samples have been abstracted and certain details redacted or generalized to respect confidentiality agreements. This case study is intended to demonstrate technical problem-solving and development approach.

## Tech Stack
React.js, TypeScript, Tailwind CSS, Gatsby, GraphQL, PostgreSQL, Yarn, Git, Jest, Cypress, Sanity

## Business Challenge
Many individuals seeking information about addiction and mental health facilities often struggle to find clear and comprehensive information about the available support tiers, which can range from outpatient therapy to intensive inpatient options. The existing system lacked clarity in presenting the continuum of care, making it difficult for users to make informed decisions about their treatment.

## User Research Results
The project began with extensive user research, including surveys and user interviews. The findings revealed that users struggled to understand the different levels of care available for mental health and addiction treatment, with many unfamiliar with key terms like "partial hospitalization" and "residential treatment." This lack of clarity created a barrier to seeking treatment, as patients were unsure about their options or how to navigate the process.

### Key Findings
- In interviews with 50 users, 80% expressed frustration with not knowing the difference between outpatient and inpatient care. The new module aimed to clarify these distinctions.
- 45% of survey respondents indicated that unclear treatment options were a significant barrier to making informed decisions about care.
- 30% of users reported they would have engaged with treatment centers sooner if the treatment levels were better explained.
- A competitive audit of other digital healthcare platforms showed widespread use of clinical language (e.g., “PHP,” “IOP,” “residential treatment”) that matched provider taxonomies—but lacked accompanying explanations for patients. This mismatch between industry language and user comprehension highlighted the need for educational modules written in plain, accessible terms.

## Implementation


### Mapping the Levels of Care
The feature presented treatment options along a continuum of care, including:

1. **Outpatient Therapy**: Short-term, non-residential treatment for individuals.
2. **Partial Hospitalization Programs (PHP)**: Intensive, structured treatment during the day with flexible night accommodations.
3. **Residential Treatment**: Full-time, inpatient care for individuals needing intensive support.
4. **Detoxification**: Supervised care for individuals withdrawing from substances.
5. **Aftercare and Support**: Ongoing recovery support after primary treatment.

### Collaboration with Clinicians
Clinicians and subject-matter experts were closely involved to ensure the accuracy of the content. Research specialists reviewed and validated the descriptions for each treatment level, ensuring that the information was medically sound, while the copy was written to be both accessible and informative for users.


### Database Integration
Leveraged PostgreSQL to store detailed information about treatment centers, with daily data refreshes for accuracy. Data was retrieved using GraphQL to optimize performance.


````tsx
// Example of a GraphQL query fetching treatment details
const GET_TREATMENT_OPTIONS = gql`
  query GetTreatmentOptions($centerId: ID!) {
    treatmentCenter(id: $centerId) {
      name
      services {
        type
        description
        location
      }
    }
  }
`;
````

### React-Based UI
Created a user-friendly interface that allowed users to explore treatment options with minimal friction. Components were designed for scalability and reuse.

````tsx
// Example of how you used React to dynamically render treatment options
const TreatmentOptions: React.FC<{ centerId: string }> = ({ centerId }) => {
  const { data, loading, error } = useQuery(GET_TREATMENT_OPTIONS, {
    variables: { centerId },
  });
return (
    <div>
      <h3>Treatment Options at {data.treatmentCenter.name}</h3>
      <ul>
        {data.treatmentCenter.services.map((service) => (
          <li key={service.type}>
            <strong>{service.type}</strong>: {service.description} ({service.location})
          </li>
        ))}
      </ul>
    </div>
  );
};

````

### Conditional Hyperlinks
Integrated dynamic hyperlinks that adapted based on user preferences, location, and browsing history. These links helped users find location-specific services like detox treatment.


## UX Design Process
Led the iterative design process, including wireframing, prototyping, and user testing. The final module was placed beneath the center overview panel to ensure visibility without overwhelming the user with details.

The design team initially suggested a grid approach, but design and development decided to not move forward with that iteration as it became more apparent what core offerings would be shown in that module.
<img src="https://i.imgur.com/JfzY8PS.png">

The module in its final form ended up going on every center profile right beneath the center overview panel. This treatment prioritized educating the user about treatment options before delving into the specialties of a specific center.

<img src="https://i.imgur.com/GJSVieA.png"/>

### Value Maximization
Displayed core services in the continuum of care, even when not offered by a provider, to educate users. Links to location-specific pages enhanced relevance.

### Final Iteration of the Continuum of Care Module


<img src="https://i.imgur.com/6PtX7Nh.png"/>


## Testing and Validation
### Unit Testing
Jest was used for testing individual components to ensure functionality and stability.
### End-to-End Testing
Cypress validated the entire user journey to ensure the feature worked seamlessly across browsers and devices.
#### User Acceptance Testing (UAT)
UAT was conducted with a sample of end-users, including healthcare professionals and individuals seeking treatment, to ensure the feature met expectations.

##### Key Focus Areas:
- Accessibility and clarity of information
- Mobile usability

##### Feedback
Most users easily navigated and understood the treatment options. Minor adjustments were made based on feedback regarding readability contrast.

## User Reception
User feedback following the launch of the feature was overwhelmingly positive. Users appreciated the platform's commitment to providing transparent and accessible information, making their search for mental health and addiction resources more manageable and less daunting.

Here is one example of the how helped someone achieve more clarity about the continnum of care when perusing profiles of treatment facilities. Please click on the image to view the user interaction.

<a href="https://drive.google.com/file/d/1sCRUGweHWsJYjoLGQ0c186nQ_8ylOK9y/view?usp=sharing" title="Levels of Care Module"><img src="https://i.imgur.com/6vbFpC8.png"/></a>

## Results
- **30% increase in pageviews** within two weeks of launch, demonstrating immediate engagement  
- **25% increase in time spent per session**, indicating deeper user interaction with treatment content  
- **15% reduction in bounce rate**, showing that users found more relevant and actionable information  
- **85% of users reported feeling more confident** in their treatment decisions after using the module  
- **50% reduction in manual content updates**, streamlining operations and improving team efficiency  
- **Faster feedback processing**, with user survey analysis time cut by **30%**, thanks to clearer, structured content
