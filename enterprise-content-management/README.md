# Empowering Users and Streamlining Operations Through Integrated Content & Digital Enablement Solutions

<b>Role:</b> Developement Lead, Project Manager

<b>Collaborators:</b> Product Designer, UX Designer, Product Manager, Chief Product Officer, Clinical Research Director

## Project Background

This case study highlights the implementation of integrated platform capabilities that enhanced user education, streamlined internal operations, and improved content discoverability across over **20,000 pages** of a digital healthcare platform. Addressing inefficient content management, a lack of clarity in treatment information, and poor site navigation, strategic solutions were developed and deployed. The automation of content types, including FAQs, hero content, more custom fields, significantly reduced administrative workload and improved content accuracy. Concurrently, a dynamic treatment information module enhanced user understanding of treatment options, while comprehensive SEO optimizations and performance enhancements improved site visibility and user experience platform-wide. These integrated improvements optimized internal processes, empowered users, and resulted in positive platform metrics and user feedback.

## Business Challenge

The digital healthcare platform faced three key challenges that hindered user experience and adoption as well as internal efficiency:

1.  **Inefficient Content Management:** Maintaining accurate and up-to-date information, particularly default FAQs across a vast number of center pages, was a time-consuming and error-prone process. Custom FAQs often overrode default content, leading to inconsistencies and increased administrative burden.
    * **Internal Pain Points:**
        * **Customization Needs:** Centers needed an easier way to edit default FAQs rather than creating custom FAQs for every minor change.
        * **Data Maintenance:** Custom FAQs were overriding default FAQs in Sanity, leading to maintenance challenges and outdated information. Changes in variables (e.g., price, insurance) required manual updates, which were prone to errors and delays.
    * **Customer Feedback:**
        * Centers with standardized operations expressed frustration with manual updates.
        * Admins sought simpler solutions to adjust FAQ text without needing to rebuild entire FAQs.
        * Clients noted that small tweaks to information should not require rebuilding FAQs from scratch.
        * *"Our team was spending hours each week just updating basic information across different pages. It felt like we were constantly playing catch-up."* - Administrator at a multi-location rehab network

2.  **Lack of Clarity in Treatment Information:** Many individuals seeking information about addiction and mental health facilities struggled to understand the different levels of care available, hindering their ability to make informed decisions about treatment options. The platform lacked a clear and accessible presentation of the continuum of care.

3.  **Poor Content Discoverability and Inconsistent Routing**: Patients struggled to find specific information due to a disorganized structure and unpredictable URLs, potentially delaying access to crucial details about their health and treatment options.

    * **User Research Results:**
        * In interviews with 50 users, 30% expressed frustration with not knowing the difference between outpatient and inpatient care.
        * 45% of survey respondents indicated that unclear treatment options were a significant barrier to making informed decisions about care.
        * 30% of users reported they would have engaged with treatment centers sooner if the treatment levels were better explained.
    * **Competitive Landscape:** Other digital healthcare platforms used clinical language without sufficient explanation, creating a mismatch with user comprehension.
    * Keyword and competitor analysis identified significant opportunities to improve organic visibility by leveraging rich snippets and structured data for healthcare-related searches. This could directly improve patient access to reliable information.
    * *"I see all these different terms like 'PHP' and 'residential,' but I have no idea what they actually mean for me."* - User Interview Participant

## Agile Project Management

This project was managed using Agile methodologies, ensuring a transparent and efficient development process focused on delivering value iteratively. Key activities included:

* **Requirements Gathering and Alignment:** Collaborated with stakeholders to gather and document project requirements, which were formalized in detailed Product Requirements Documents (PRDs). These PRDs ensured clear alignment with business goals and facilitated stakeholder buy-in across engineering, content, and design teams.
* **MVP Definition and Roadmapping:** Worked closely with the Product Owner and Chief Product Officer to scope the Minimum Viable Product (MVP) and define a prioritized feature roadmap, focusing on delivering core value early and often.
* **Sprint Planning and Execution:** Led sprint planning sessions, facilitated story writing and backlog grooming within Jira, and managed task progress to ensure alignment with sprint timelines.
* **Cross-Functional Collaboration:** Managed daily standups and sprint reviews with engineering, UX, and stakeholders, fostering seamless communication and shared understanding across cross-functional teams. Proactively managed dependencies and risks through close collaboration.
* **Quality Assurance and Acceptance:** Defined clear acceptance criteria and QA checkpoints across multiple agile sprints to maintain high quality and ensure alignment with user needs throughout the development lifecycle.
* **Release and Post-Launch Support:** Created comprehensive internal release documentation and tailored Content Management System (CMS) training materials for content editors to facilitate a smooth onboarding experience.

## Core Capabilities Implemented

To address these interconnected challenges, the following core capabilities were designed and implemented:

### 1. Automated & Centralized Content Management

**Goal:** To streamline the management of default FAQs, ensure accuracy, and reduce administrative workload.

**Data Flow for Core Content Updates:**

* **User interface and content management**: Sanity provides the interface for content managers. CMS is a restrictive interface to update data.
* **Digital asset management**: Cloudinary is an image hosting provider for content content. All image content updates are synced to Cloudinary and the Algolia collection for the entry.
* **Data source**: PostgreSQL database stores the core content. Algolia is a search engine specifically used for searching core content (center and location data). Sanity is an interface for managing content that is then automatically synced (replicated) in PostgreSQL and Algolia.
* **Data retrieval**: GraphQL API queries only the necessary data. It bridges between Postgres and WordPress. More developer-friendly way to write queries for data retrieval.
* **Front-end**: CMS updates reflect on front end following each new site build
* **CDN**: User traffic is routed through a CDN (Cloudflare), which caches static assets (CSS, JS, images, fonts, 3rd-party libraries)
* **End user**: Sees the most recent data updates in the UI
![image](https://github.com/user-attachments/assets/937194b3-f0ca-40c9-b77c-3bdbe27a1ff1)


**Functionality:**

* **Dynamic Default FAQ Population:** Developed a Node.js backend API to fetch default FAQ data from PostgreSQL. The API ensured that FAQs were correctly mapped to center-specific configurations. This component displayed the default FAQs with options for editing, allowing Sanity to automatically populate with up-to-date FAQs based on the center’s configuration. Utilized GraphQL to efficiently query only the necessary FAQ data, reducing unnecessary data load and optimizing performance.

[Watch the walkthrough video on Loom](https://www.loom.com/share/4a2617416e9940fc85e25684f602ab5b)

* **Automatic Updates for Variable Data:** Designed and configured AWS Lambda functions to listen for changes in PostgreSQL-stored center data (e.g., pricing or insurance), automatically triggering updates to the relevant FAQ fields in Sanity. Used GraphQL queries to fetch only the updated FAQ data, ensuring accurate, real-time reflections of center-specific changes with minimal manual intervention.
* **Intuitive In-CMS Editing:** Built schemas as user-friendly custom fields in Sanity, which allowed admins to modify content directly within the default framework, eliminating the need for manual code changes.
* - **To further enhance content creation flexibility, I **expanded the Sanity type definitions to enable rich text functionality** for various CMS fields, allowing content editors to include formatting, links, and other rich media directly within the Sanity interface. 

### SEO & Structured Data: Improving Visibility and Trust

- Generated clean and descriptive URLs for all dynamic pages, improving search engine understanding and user comprehension.
- Implemented comprehensive meta tags, Open Graph tags, and automated JSON-LD schema for various content types, including:
    - Articles
    - Medical Clinics
    - Insurance Providers
    - FAQs
    - Reviews
    - Breadcrumbs
- Validated all structured data using Google Rich Results Test and Search Console, ensuring accurate representation in search results and enhancing trust.
- Automated schema injection at build time via Gatsby, ensuring consistent and accurate structured data across thousands of pages without manual intervention. This improves the likelihood of patients finding reliable health information through search engines.

#### Crawlability and Indexing
To improve crawl efficiency, I built categorized sitemap indexes, filtering out low-value pages like parameterized and noindex pages. This ensured a more effective use of crawl budgets and reduced unnecessary indexing delays.

#### Breadcrumb Automation
I implemented an automated breadcrumb generation system based on real-time page hierarchy, which was paired with the BreadcrumbList schema to improve search result visibility. This allowed for better navigation and enhanced SERP features.

#### Navigation Improvements
- Implemented dynamic routing using Gatsby's `createPages` API and React Router to create intuitive, category-based URLs (e.g., `/insurance/aetna/`, `/clinics/texas/houston/`), making it easier for patients to find specific information.


### Performance Optimization: Delivering Fast and Reliable Access

- Refactored data queries and optimized asset loading to achieve a Time to Interactive (TTI) of under 2 seconds, ensuring rapid access to critical health information for patients.
- Implemented Cloudflare CDN for efficient content caching and lazy loading of assets, minimizing page load times and improving the overall user experience, especially on slower connections.
- Structured GraphQL queries on a per-route basis to prevent over-fetching of data and reduce build times, contributing to a faster and more efficient website.
- Implemented SSR and optimized bundle delivery to maintain high page speed and make the pages easily crawlable by search engines.

**Technical Challenges Overcome:**

* **Data Synchronization:** Implemented a robust error handling system to ensure that failed updates would retry automatically, preventing data inconsistencies between PostgreSQL and Sanity.
* **Performance Optimization:** Initial GraphQL queries were causing performance bottlenecks. Optimized queries by implementing pagination and selective field fetching, reducing average response time from 3s to 200ms.
* **Editing Workflow:** Created a custom React component for Sanity that preserved core FAQ content while allowing variable sections to be edited, solving the challenge of balancing standardization with customization.

### 2. Dynamic Treatment Education Module

**Goal:** To enhance user understanding of available treatment options and facilitate informed decision-making.

* **Continuum of Care Mapping:** The structure and levels of care presented in this module were directly based on the **ASAM (American Society of Addiction Medicine) Continuum of Care for Adult Addiction Treatment**. This widely recognized framework defines a comprehensive range of services, from outpatient therapy to medically managed inpatient care, ensuring a standardized and evidence-based approach to treatment. The specific levels defined and described in the module included:
  
    1.  **Outpatient Services**: Short-term, non-residential treatment for individuals.
    2.  **Partial Hospitalization Programs (PHP)**: Intensive, structured treatment during the day with flexible night accommodations.
    3.  **Residential Treatment**: Full-time, inpatient care for individuals needing intensive support.
    4.  **Detoxification**: Supervised care for individuals withdrawing from substances.
    5.  **Aftercare and Support**: Ongoing recovery support after primary treatment.
    
Clear and accessible descriptions for each level were developed in close collaboration with clinicians and subject-matter experts to ensure accuracy and user comprehension.

**UX Design Process:**

Led the iterative design process, including user research, wireframing, prototyping, and user testing. UX designers created detailed mockups and explored multiple state changes (hover, focus, active, etc.) in Figma, leveraging a comprehensive design library to ensure consistency and adherence to brand guidelines. These Figma designs served as the blueprint for the user interface of the treatment education module. The final module was placed beneath the center overview panel to ensure visibility without overwhelming the user. 

The design team initially suggested a grid approach. However, feedback from UserTesting indicated that a **linear, column-based presentation was significantly clearer and easier for users to understand the continuum of care**. This direct user feedback led to the prioritization and implementation of the column-based structure for improved comprehension and usability.I then took these Figma designs and converted them into the final, responsive UI implementation using Tailwind CSS, ensuring a seamless transition from design to code.

![Initial Grid Design Suggestion](https://i.imgur.com/JfzY8PS.png)

The final module was implemented on every center profile directly beneath the center overview panel, prioritizing user education about treatment options before delving into specific center specialties.

The module displayed core services in the continuum of care, even when not offered by a provider, to educate users. Links to location-specific pages enhanced relevance.

![Final Iteration of the Continuum of Care Module](https://i.imgur.com/6PtX7Nh.png)

**Functionality:**

* **Dynamic Presentation:**
    * Developed a reusable React-based UI component to dynamically display relevant treatment options on center profile pages.
    * Leveraged PostgreSQL to store detailed information about treatment centers, with daily data refreshes for accuracy. Data was retrieved using optimized GraphQL queries.
* **Contextual Linking:** Integrated dynamic hyperlinks that adapted based on user preferences, location, and browsing history, guiding them to relevant, location-specific services like detox treatment.


## Internal Navigation on Resource Hub

### Before Implementation
![Before Screenshot](https://i.imgur.com/qvLhXCk.png)
The resource hub lacked any structured navigation. Information was presented in a disorganized manner, making it extremely difficult for patients to find specific details. The absence of clear categories and overwhelming options led to high bounce rates and frustrated users, as they struggled to navigate the vast amount of content.*

### After Implementation
![After Screenshot](https://i.imgur.com/xONWX3N.jpg)
A new navigation structure was implemented based on a Jobs to Be Done framework, introducing clear top-level categories such as "Understand Needs," "Explore Options," and "Gather Information," with relevant sub-categories like "Substances" and "Dual Diagnosis." This marked a significant improvement from the previous state, which lacked any organized navigation. By focusing on the core jobs patients were trying to accomplish, we provided a much-needed structure to the resource hub.

The introduction of this goal-oriented navigation, with its clear categorization, intuitive filtering (as seen in the screenshot), and consistent hierarchy, drastically improved usability. This directly addressed the previous challenges of high bounce rates and user frustration.

While search data informed the initial selection of these categories, future iterations would benefit from deeper user research to further refine the taxonomy based on patient mental models and language. This iterative approach will ensure the navigation continues to evolve and best serve the needs of our users.

The implementation of this redesigned navigation involved close collaboration with the Product Designer and UX Designer, translating detailed specifications into a functional and visually appealing UI using Tailwind CSS. The design meticulously incorporated the primary, secondary, and tertiary color palettes from our brand's design system to define the default, pressed, and hover states of each category. This attention to detail ensured clear visual feedback for user interactions.

Adhering to the brand style guide's emphasis on conveying "Hope, growth, Connection, & Calm," the color choices and overall aesthetic of the navigation were carefully selected. Furthermore, a key consideration was ensuring accessible text and clear visual distinction between UI elements and surfaces, contributing to an inclusive user experience. This thoughtful design process, combined with the structured Jobs to Be Done framework, played a significant role in the improved usability and positive user feedback.


**Testing and Validation:**

* **Unit Testing:** Jest was used for testing individual React components to ensure functionality and stability.
* **End-to-End Testing:** Cypress validated the entire user journey to ensure the feature worked seamlessly across browsers and devices.
* **User Acceptance Testing (UAT):** UAT was conducted with a sample of end-users, including healthcare professionals and individuals seeking treatment, to ensure the feature met expectations. Key focus areas included accessibility, clarity of information, and mobile usability. Feedback from UAT led to minor adjustments regarding readability contrast.

* **Testing and Quality Assurance:**

- **Unit Testing (Jest):** Validated individual React components and FAQ functionality, ensuring default FAQs were populated and editable without errors.
- **End-to-End Testing (Cypress):** Simulated real-world user journeys and verified cross-browser/device performance, including updates to center configurations and FAQ logic.
- **User Acceptance Testing (UAT):** Conducted with healthcare professionals and end-users to evaluate clarity, accessibility, and mobile usability. Feedback led to contrast improvements for better readability.
- **Continuous Integration:** Integrated automated schema validation, code linting, and test execution into GitHub Actions and Netlify deploy previews.
- **Accessibility Compliance:** Implemented WCAG 2.1 AA standards to support users with disabilities.

## User Feedback: Positive Impact on Patients and Administrators

### Patients

Reported that the improved site structure and dynamic pages made it significantly easier to navigate and locate relevant insurance details and treatment options during the crucial evaluation stage of their healthcare journey. The enhanced search functionality and clearer categorization empowered them to find the information they needed quickly and efficiently.

> "I used to spend 15-20 minutes trying to find information about whether my insurance was accepted at a specific clinic. Now I can find everything I need in under a minute. This makes a huge difference when you're trying to make healthcare decisions." - Patient feedback from post-launch survey

### Administrators

Experienced a substantial optimization of the content management process, with significantly fewer manual updates required and a more streamlined workflow for managing content at scale. The new CMS and automated processes reduced the burden on administrative resources and improved the timeliness of content updates.

> "Before this update, I would spend about 60% of my work week just making manual updates across pages. Now that time has been cut in half, allowing me to focus on creating better content instead of just maintaining it." - Content Administrator

## Results & Overall Impact

- **30% increase in pageviews** on pages featuring the treatment module.
- **25% increase in time spent per session**, indicating deeper user engagement with treatment information.
- **45% of users reporting feeling more confident** in their treatment decisions after using the module.
- **15% lower bounce rate** across center pages by providing more relevant and actionable information.
- **30% reduction in manual content updates** related to treatment information due to the structured and dynamic nature of the module.

## Lessons Learned & Future Enhancements

* **Integrated Solutions are a Powerful Force for the Bottom Line:** Addressing related challenges with interconnected capabilities (efficient content management directly supports better user-facing information) leads to more holistic and impactful outcomes.
* **User-Centricity Drives Adoption:** Focusing on the needs of both internal users (admins needing efficient tools) and external users (patients needing clear information) is crucial for the success of any platform enhancement.
* **Data-Driven Iteration is Key:** Leveraging user research, feedback, and platform analytics to refine and improve features is essential for continuous optimization. The pivot in the treatment module design based on evolving understanding highlights this.
* **Cross-Functional Collaboration is Essential:** The success of both initiatives relied heavily on the collaboration between development, product, design, clinical, and customer success teams.

**Future enhancements** include extending automation to other content types beyond FAQs, incorporating AI-assisted content suggestions based on user engagement patterns, personalizing treatment information based on user profiles, and integrating interactive elements and multimedia (e.g., videos) to enhance user understanding further.
