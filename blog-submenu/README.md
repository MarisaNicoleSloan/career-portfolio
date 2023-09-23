# Blog Submenu and Category Pages

<b>Problem Statement</b>

In response to user pain points and a decline in traffic and engagement, the project aimed to address the significant challenges users encountered when navigating a content-rich blog with hundreds of posts. Prior to this project, users faced difficulties in locating and navigating through the extensive blog content, resulting in diminished traffic and reduced usage. The goal was to create a user-centric blog submenu and category pages, ensuring readers could effortlessly find and explore relevant content, thereby revitalizing the user experience and content discoverability.

<b>User Research Results</b>

Usability tests uncovered a common challenge: users frequently felt overwhelmed by the sheer volume of content and struggled to locate articles of interest. This critical insight provided the compelling foundation for the enhancements.

<b>Technologies Used</b>

React, Tailwind CSS, Gatsby, WordPress

<b>Challenges and Iterative Design</b>

*Challenge 1: Content Organization and User Overwhelm*

Initially, one of the key challenges was the organization of the extensive blog content. Users often felt overwhelmed, and this was reflected in the lack of specific feedback on the blog's usability. To address this, there needed to be a way to categorize and present content in a more user-friendly manner.

*Challenge 2: Technical Implementation*

Implementing the submenu and category pages posed technical challenges. I had to ensure that the navigation system was fast and responsive, especially as the blog had hundreds of posts. Integrating this seamlessly with WordPress, which was one of the website's content management systems, required careful planning.

*Challenge 3: Content Tagging and Maintenance*

Creating category pages and tagging articles presented challenges related to content management. The content team needed to tag each article correctly for it to appear on the respective category page. This required clear guidelines and coordination.

<b>Design and Development</b>

*Design Iteration 1: Submenu Concept*

The first design iteration involved the concept of introducing a submenu. Providing users with a quick way to navigate to specific categories would alleviate the issue of content overload.
After receiving feedback following the first design iteration, I made several enhancements to the submenu. Some additional functionality and styling were built upon this initial mockup. Specifically, I addressed the following issues:

- The gray divider line was made continuous for a more cohesive visual experience
-I adjusted the purple selected line to coordinate with the size of the title, ensuring it aligned with the content
  
After some feedback from the design team, I recognized a need for improved user navigation between parent and subcategory pages. To address this, I made the following refinements:

- When a chip (e.g., "Symptoms") is selected, it now shows as selected on the "Symptoms" page, providing users with a clear indication of their current location within the navigation.
- Clicking on a tab immediately takes users to a parent page of that title, eliminating confusion caused by sub-categories being initially displayed.
- Once on the parent page (e.g., "Gathering Information"), users can easily select a subcategory to narrow down results. To facilitate this, we introduced an additional chip labeled "All," which is selected by default when clicking on a tab.

*Design Iteration 2: Dynamic Submenu with Categories*

To make the submenu more engaging, I implemented dynamic features using React. Users could now interact with the submenu, and clicking a button would take them to the corresponding category page. I also introduced auto-scrolling to create a seamless content exploration experience.

<img src="https://i.imgur.com/xONWX3N.jpg" height="80%" width="80%" alt="Blog Submenu"/>

<b>Results and Achievements</b>

30% increase in page views for blog content.
20% increase in time on page for blog content.
