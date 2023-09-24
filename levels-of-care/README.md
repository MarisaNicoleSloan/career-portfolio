# Levels of Care Feature for Mental Health and Addiction Treatment

<b>Client</b>

RehabPath

<b>Client Industry</b>

Addiction Treatment and Mental Health

<b></b>Project Scale</b>

Approximately 4,000 pages incorporated this module.

<b>Business Challenge and User Need</b>

Many individuals seeking information about addiction and mental health facilities often struggle to find clear and comprehensive information about the available support tiers, which can range from outpatient therapy to intensive inpatient options. The existing system lacked clarity in presenting these support tiers, making it difficult for users to make informed decisions about their treatment.

<b>User Research Results</b>

The project began with extensive user research, including surveys and user interviews. The findings revealed that users faced challenges in understanding the different levels of care available for mental health and addiction treatment. They expressed a need for clear and accessible information to make informed decisions about their treatment options.

<b>Technologies Used</b>

ReactJS, Tailwind CSS, Gatsby, GraphQL, PostgreSQL

<b>Implementation Details</b>

In order to address the issues mentioned above, I implemented the following key technical features:

<b>Database Integration</b>

I leveraged PostgreSQL, a relational database, to store and manage information about addiction and mental health facilities. This database included details about specializations, treatment options, and support tiers. This structured approach provided users with comprehensive and up-to-date information, since the data was refreshed on a daily basis. GraphQL queries were configured to efficiently retrieve data from the database and present it in an organized manner.

<b>React-Based User Interface</b>

I built the interface using ReactJS to display information about these facilities. This allowed users to easily navigate and explore the treatment options available to them. 

<b>Conditional Hyperlinks</b>

To further enhance the user experience, I implemented a feature that conditionally displayed hyperlinks to related pages based on user preferences and the availability of relevant results. This optimization ensured that users were directed to pages with ample results, enhancing their overall experience and minimizing frustration. 

<b>UX Design Process</b>

Figuring out the placement of the module and its destination links involved wireframing, prototyping, and user testing. I iterated on the design based on user feedback to ensure an intuitive and user-friendly experience.

The design team initially suggested a grid approach, but design and development decided to not move forward with that iteration as it became more apparent what core offerings would be shown in that module.
<img src="https://i.imgur.com/JfzY8PS.png">


The module in its final form ended up going on every center profile right beneath the center overview panel. This treatment prioritized educating the user about treatment options before delving into the specialties of a specific center.

<img src="https://i.imgur.com/GJSVieA.png"/>

In order to maximize value to the user, the core services of the continuum of care were always shown whether the provider offered it or not in order to educate the patient. The hyperlink went to a faceted location, meaning that users were directed to a page featuring centers in a location along with a specific specialty, such as detox treatment. This decision kept the results contextually relevant to the user, since they were directed to a page in the same location as the center they had just viewed.

<img src="https://i.imgur.com/6PtX7Nh.png"/>

<b>Benefits and Achievements</b>

- 50% increase in pageviews within just two weeks of launching the feature
- Surfacing this information reinforced the brand's reputation as a trusted platform in the mental health addiction space as a comprehensive online resource that was always patient-first.
