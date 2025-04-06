# Dynamic Treatment Information Module for Mental Health and Addiction Centers

<b>Company</b>

Recovery.com

<b>Industry</b>

Behavioral Health (Addiction Treatment and Mental Health)

<b>Project Background and Scale</b>

Approximately 10,000 pages incorporated this module.

<b>Tech Stack</b>

ReactJS, Tailwind CSS, Gatsby, GraphQL, PostgreSQL

<b>Business Challenge</b>

Many individuals seeking information about addiction and mental health facilities often struggle to find clear and comprehensive information about the available support tiers, which can range from outpatient therapy to intensive inpatient options. The existing system lacked clarity in presenting these support tiers, making it difficult for users to make informed decisions about their treatment.

<b>User Research Results</b>

The project began with extensive user research, including surveys and user interviews. The findings revealed that users faced challenges in understanding the different levels of care available for mental health and addiction treatment. They expressed a need for clear and accessible information to make informed decisions about their treatment options.

<b>Implementation Details</b>

In order to address the issues mentioned above, I implemented the following key technical features:

*Database Integration*

I leveraged PostgreSQL, a relational database, to store and manage information about addiction and mental health facilities. This database included details about specializations, treatment options, and support tiers. This structured approach provided users with comprehensive and up-to-date information, since the data was refreshed on a daily basis. GraphQL queries were configured to efficiently retrieve data from the database and present it in an organized manner.

*React-Based User Interface*

I built the interface using ReactJS to display information about these facilities. This allowed users to easily navigate and explore the treatment options available to them. 

*Conditional Hyperlinks*

To further enhance the user experience, I implemented a feature that conditionally displayed hyperlinks to related pages based on user preferences and the availability of relevant results. This optimization ensured that users were directed to pages with ample results, enhancing their overall experience and minimizing frustration. 

<b>UX Design Process</b>

Figuring out the placement of the module and its destination links involved wireframing, prototyping, and user testing. I iterated on the design based on user feedback to ensure an intuitive and user-friendly experience.

The design team initially suggested a grid approach, but design and development decided to not move forward with that iteration as it became more apparent what core offerings would be shown in that module.
<img src="https://i.imgur.com/JfzY8PS.png">

The module in its final form ended up going on every center profile right beneath the center overview panel. This treatment prioritized educating the user about treatment options before delving into the specialties of a specific center.

<img src="https://i.imgur.com/GJSVieA.png"/>

In order to maximize value to the user, the core services of the continuum of care were always shown whether the provider offered it or not in order to educate the patient. The hyperlink went to a faceted location, meaning that users were directed to a page featuring centers in a location along with a specific specialty, such as detox treatment. This decision kept the results contextually relevant to the user, since they were directed to a page in the same location as the center they had just viewed.

This is how the final block appeared.


<img src="https://i.imgur.com/6PtX7Nh.png"/>


<b>User Reception</b>

User feedback following the launch of the feature was overwhelmingly positive. Users appreciated the platform's commitment to providing transparent and accessible information, making their search for mental health and addiction resources more manageable and less daunting.

Here is one example of the how helped someone achieve more clarity about the continnum of care when perusing profiles of treatment facilities. Please click on the image to view the user interaction.

<a href="https://drive.google.com/file/d/1sCRUGweHWsJYjoLGQ0c186nQ_8ylOK9y/view?usp=sharing" title="Levels of Care Module"><img src="https://i.imgur.com/6vbFpC8.png"/></a>


<b>Benefits and Achievements</b>

- 30% increase in pageviews within just two weeks of launching the feature
- Surfacing this information reinforced the brand's reputation as a trusted platform in the mental health addiction space as a comprehensive online resource that was always patient-first

Project Scale:
Implemented a comprehensive treatment levels feature across 4,000+ pages, ensuring accurate, dynamic information on mental health and addiction care is accessible to users.

Business Challenge:
Users struggled to find clear, comprehensive information about addiction and mental health care options, which affected their ability to make informed decisions about treatment centers.

User Research Insights:
Research revealed a significant gap in the accessibility and clarity of information related to available treatment levels. Users needed an easy, structured way to compare options, understand care pathways, and find the right fit for their needs.

Technologies Used:

ReactJS: Used for building the dynamic and interactive UI components, ensuring a seamless user experience.

Tailwind CSS: Implemented for fast, responsive styling with utility-first classes, enabling a highly customizable and efficient development process.

Gatsby: Leveraged for static site generation, ensuring fast load times and optimized for SEO.

GraphQL: Utilized to fetch data efficiently from the database, improving performance and scalability.

PostgreSQL: Used to manage and update the facility details, treatment tiers, and specializations, ensuring accurate and timely content.

Implementation:

Database Integration: Used PostgreSQL to store and manage detailed information about treatment centers, including specializations and treatment tiers. Implemented daily data refreshes to ensure the most up-to-date and accurate information was available. Data was retrieved using GraphQL queries, optimizing data fetching and reducing unnecessary load times for users.

React-Based UI: Developed the user interface in ReactJS, focusing on responsiveness and accessibility. The interface was designed to allow users to easily browse through treatment options with minimal friction. Key components were built as reusable React components, allowing for quick updates and scalability.

Conditional Hyperlinks: Integrated dynamic conditional hyperlinks that adapt to user preferences and browsing history, enhancing the accessibility and relevance of content. Links were automatically generated based on factors like location, user interests, and available care options, improving the discoverability of specialized services.

UX Design Process: Led the iterative UX design process, which included wireframing, prototyping, and user testing. The final feature was strategically positioned within the center overview panel on each treatment center profile to maximize visibility and ease of access. Conducted regular user testing to refine and optimize the user flow, ensuring it was intuitive and straightforward.

Value Maximization: Ensured that core services were always displayed within the continuum of care, even for providers that didn’t offer them, helping to educate users about available options. Added links that directed users to location-specific pages containing relevant specialties, further personalizing the user experience and aiding in decision-making.

Results:

30% increase in pageviews within two weeks of launch, indicating improved engagement and content visibility.

Enhanced user trust and retention: Users found the information more accessible, leading to higher levels of engagement and increased trust in the platform’s authority on mental health and addiction care.

Improved decision-making: The clear, structured presentation of treatment options allowed users to make more informed choices, ultimately contributing to a better overall user experience.

Enhanced brand reputation: The project positioned the platform as a reliable source of mental health and addiction care information, enhancing the brand’s credibility and trust within the healthcare community.

Testing and Validation:

Unit Testing: Wrote and ran unit tests using Jest to ensure individual components and features worked as expected, providing robust error handling and stability.

End-to-End Testing: Conducted E2E testing using Cypress to simulate user interactions and validate the entire user journey from start to finish, ensuring that the treatment levels feature functioned seamlessly across different browsers and devices.
