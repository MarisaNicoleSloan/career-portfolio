# Dynamic Treatment Education Feature for a Digital Healthcare Platform

## Project Background
Implemented a dynamic treatment information module across 4,000+ pages, aiming to improve user understanding of mental health and addiction treatment options. The module aimed to present clear, structured data on the various levels of care available at facilities, such as outpatient therapy and inpatient care.

<b>Role</b>: Development Lead, Project Manager

<b>Collaborators</b>: UI Designer, Product Manager, Chief Product Officer (for buy-in and budget), Research Specialists for clinical review

## Tech Stack
React.js, TypeScript, Tailwind CSS, Gatsby, GraphQL, PostgreSQL, Yarn, Git, Jest, Cypress, Sanity

## Business Challenge
Many individuals seeking information about addiction and mental health facilities often struggle to find clear and comprehensive information about the available support tiers, which can range from outpatient therapy to intensive inpatient options. The existing system lacked clarity in presenting these support tiers, making it difficult for users to make informed decisions about their treatment.

## User Research Results
The project began with extensive user research, including surveys and user interviews. The findings revealed that users faced challenges in understanding the different levels of care available for mental health and addiction treatment. They expressed a need for clear and accessible information to make informed decisions about their treatment options.

## Implementation

### Database Integration
Leveraged PostgreSQL to store detailed information about treatment centers, with daily data refreshes for accuracy. Data was retrieved using GraphQL to optimize performance.

### React-Based UI
Created a user-friendly interface that allowed users to explore treatment options with minimal friction. Components were designed for scalability and reuse.

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
