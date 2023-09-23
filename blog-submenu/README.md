# Blog Submenu and Category Pages

<b>Problem Statement</b>

In response to user pain points and a decline in traffic and engagement, our project aimed to address the significant challenges users encountered when navigating a content-rich blog with hundreds of posts. Prior to this project, users faced difficulties in locating and navigating through the extensive blog content, resulting in diminished traffic and reduced usage. Our goal was to create a user-centric blog submenu and category pages, ensuring readers could effortlessly find and explore relevant content, thereby revitalizing the user experience and content discoverability.

<b>User Research Results</b>

Our user research, encompassing surveys and usability testing, uncovered a common challenge: users frequently felt overwhelmed by the sheer volume of content and struggled to locate articles of interest. This critical insight provided the compelling foundation for our enhancements.

<b>Technologies Used</b>

React, Tailwind CSS, Gatsby, WordPress

<b>Challenges and Iterative Design</b>

*Challenge 1: Content Organization and User Overwhelm*

Initially, one of the key challenges we faced was the organization of the extensive blog content. Users often felt overwhelmed, and this was reflected in the lack of specific feedback on the blog's usability. To address this, we needed to find a way to categorize and present content in a more user-friendly manner.

*Design Iteration 1: Submenu Concept*

Our first design iteration involved the concept of introducing a submenu. We believed that providing users with a quick way to navigate to specific categories would alleviate the issue of content overload.

*Challenge 2: Technical Implementation*

Implementing the submenu and category pages posed technical challenges. We had to ensure that the navigation system was fast and responsive, especially as the blog had hundreds of posts. Integrating this seamlessly with WordPress, which was our content management system, required careful planning.

*Design Iteration 2: Dynamic Submenu with Categories*

To make the submenu more engaging, we decided to implement dynamic features using React. Users could now interact with the submenu, and clicking a button would take them to the corresponding category page. We also introduced auto-scrolling to create a seamless content exploration experience.

After receiving feedback following the first design iteration, we made several enhancements to the submenu. Some additional functionality and styling were built upon this initial mockup. Specifically, we addressed the following issues:

- The gray divider line was made continuous for a more cohesive visual experience.
- We adjusted the purple selected line to coordinate with the size of the title, ensuring it aligns with the content.
  
Furthermore, we recognized a need for improved user navigation between parent and subcategory pages. To address this, we made the following refinements:

- When a chip (e.g., "Symptoms") is selected, it now shows as selected on the symptoms page, providing users with a clear indication of their current location within the navigation.
- Clicking on a tab immediately takes users to a parent page of that title, eliminating confusion caused by sub-categories being initially displayed.
- Once on the parent page (e.g., "Gathering Information"), users can easily select a subcategory to narrow down results. To facilitate this, we introduced an additional chip labeled "All," which is selected by default when clicking on a tab.

*Challenge 3: Content Tagging and Maintenance*

Creating category pages and tagging articles presented challenges related to content management. Our content team needed to tag each article correctly for it to appear on the respective category page. This required clear guidelines and coordination.

*Design Iteration 3: Tags for Enhanced Navigation*

To further enhance navigation, we introduced tags for articles. These tags were prominently displayed, allowing users to easily access category pages. We also explored distinct routes for category pages to improve content discoverability.

<img src="https://i.imgur.com/xONWX3N.jpg" height="80%" width="80%" alt="Blog Submenu"/>

<b>Results and Achievements</b>

30% increase in page views for blog content.
20% increase in time on page for blog content.
