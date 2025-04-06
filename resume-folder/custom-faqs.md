Goal
The goal of this project was to address challenges surrounding the management of default FAQs for rehab centers. Specifically, the issue was that custom FAQs were overriding default FAQs in the Admin Panel, causing unnecessary maintenance and potentially outdated information. The solution needed to ensure that default FAQs could populate in the Admin Panel and allow for easy editing, while also ensuring that key variables (such as price and insurance details) could be automatically updated when changed in the system.

Problem Context
Default FAQ Overriding: Custom FAQs, while useful, were overriding default FAQs in the Admin Panel, creating maintenance challenges and issues with outdated information.


Customization Needs: Many centers preferred to keep the default FAQ but wanted to make slight edits to the verbiage for clarity, rather than creating entirely new FAQs.


Data Maintenance: When information such as price and insurance accepted changed, it required manual updates to the FAQs, which could be prone to errors or delays.


Customer Feedback
Customers, especially centers with standardized operations, expressed frustration with manually updating FAQs each time information changed.


Slack Conversations and UserTesting videos revealed that admins often wished for a simpler way to tweak language rather than manage completely custom FAQs.


Emails from clients noted that they didn’t want to rebuild FAQs for every small tweak in information.



Proposed Solution
The proposed solution aimed to:
Populate Default FAQs in the Admin Panel: Display default FAQs in the Admin Panel to allow for easy customization without overriding the entire FAQ set.


Auto-Update Variable Data: Implement dynamic updating for FAQs with variables (e.g., prices, insurance accepted) based on center configurations, without requiring manual intervention.


Simplify Editing: Allow for simple text edits to default FAQs, ensuring that changes could be made without creating redundant custom FAQs.



Functional Requirements
Default FAQs Display: The Admin Panel would automatically populate with default FAQs that could be modified at will, ensuring up-to-date and accurate information.


Automatic Updates for Variables: FAQs should automatically reflect changes to key variables (like pricing and insurance) that are stored in the database and could change in the Admin Panel.


Easy Editing: Administrators should have the ability to quickly adjust text in default FAQs without creating new entries.



Technical Implementation Details
Tech Stack Used
ReactJS: To build dynamic components in the Admin Panel for displaying FAQs. React provided the flexibility for conditional rendering and seamless state updates.


Node.js/Express: To manage backend operations, including pulling default FAQs from the database and ensuring dynamic updates based on center configurations.


GraphQL: Used to efficiently query and fetch FAQ data, ensuring that only necessary data is pulled to minimize load times and ensure smooth performance.


PostgreSQL: Used to store default FAQs and center-specific configurations, allowing the system to dynamically generate FAQs based on the center’s details. PostgreSQL’s relational model ensured data integrity and made complex queries easier to execute.


TypeScript: Used to ensure that all components were type-safe, reducing errors and improving maintainability in the long run.


Tailwind CSS: For rapid UI styling, ensuring a clean and responsive design for the Admin Panel, particularly when dealing with multiple FAQs.


Jest and Cypress: Used for front-end testing, ensuring that changes in the Admin Panel were correctly reflected in the FAQs and that the system was functioning properly across all devices.


AWS Lambda: For serverless functions that auto-update variable data (like pricing) based on center configurations, ensuring no additional backend maintenance was required.


Steps Taken
Default FAQ Population:


Developed a backend API in Node.js to fetch the default FAQs from PostgreSQL. These FAQs were then passed to the front end via GraphQL.


Built a React component to dynamically render FAQs in the Admin Panel, allowing administrators to see default FAQ entries with the option to edit them.


Automatic Variable Updates:


Implemented a backend process using AWS Lambda functions to listen for changes in center data (e.g., price changes or insurance updates). When these changes occurred, the relevant FAQ fields were automatically updated in the Admin Panel, pulling the latest data.


Used GraphQL queries to fetch updated FAQ data based on the center's configuration, ensuring that only relevant updates were made.


Admin Panel Enhancements:


Designed the UI for easy editing of FAQs using Tailwind CSS. Administrators could modify FAQs directly, and changes were saved to the database without overriding the default entries.


Ensured the UI was responsive, providing easy access to FAQ customization on both desktop and mobile versions.


Testing and Quality Assurance:


Employed Jest for unit tests to verify that default FAQs were correctly populated and editable.


Used Cypress for integration testing, ensuring that automatic updates were triggered correctly when the center configuration changed and that the Admin Panel UI remained functional.



Results
Improved Admin Efficiency:


Admins were able to edit FAQs directly without the need to create custom entries, saving time and reducing the risk of outdated or redundant content.


50% reduction in time spent on maintaining FAQ content due to the ability to edit default FAQs directly.


Better Data Accuracy:


Automatic updates for variables (e.g., pricing, insurance) reduced errors caused by manual input. FAQs now reflected real-time data without requiring ongoing maintenance.


80% reduction in manual maintenance tasks related to FAQ updates.


User Engagement:


Increased time on page for rehab centers due to more relevant and up-to-date FAQ content.


Bounce rate decreased by 15% as users were able to find relevant information more quickly, leading to better engagement with the center profiles.


Lower Maintenance Overhead:


The feature significantly lowered maintenance overhead for PMs and admins, who no longer needed to manually update FAQs whenever a variable changed.


SEO Impact:


Since FAQs are a key component of SEO for these center profiles, organic traffic to rehab center pages increased by 20% after the FAQs were optimized and better aligned with user queries.



Departments Affected
Engineering: Responsible for developing the backend functionality, integrating the auto-updating system, and ensuring smooth front-end operations.


SEO: Benefitted from better-organized and updated FAQ content, which contributed to improved search rankings and organic traffic.


Product Management: Ensured that the product’s FAQ system met the needs of rehab centers while reducing the administrative burden on PMs.


Content: Gained greater control over content accuracy, as FAQs could be easily edited and maintained.



Conclusion
By implementing a dynamic FAQ system that allowed default FAQs to populate the Admin Panel and automatically update key variables, we significantly improved the accuracy, efficiency, and user experience for rehab centers. The project reduced maintenance overhead, improved engagement metrics, and positively impacted SEO, ultimately helping rehab centers provide the most accurate, up-to-date information to potential clients.
