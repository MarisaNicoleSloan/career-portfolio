# Blog Submenu and Category Pages

<b>Client</b>

RehabPath

<b>Client Industry</b>

Addiction Treatment and Mental Health

<b>Project Scale</b>

This submenu impacted about 400 blog posts and required significant database modifications for implementation.

<b>Business Challenge and User Need</b>

Efficient organization and sorting are pivotal for a seamless blog user experience, driving reader retention and content exploration. The previous blog lacked these essential features, leading to reduced traffic and usage. To address these issues, I developed a user-friendly submenu with category pages.

<b>User Research Results</b>

Usability tests uncovered a common challenge: users frequently felt overwhelmed by the sheer volume of content and struggled to locate articles of interest. This critical insight provided the compelling foundation for the enhancements.

<img src="https://i.imgur.com/qvLhXCk.png"/>

<b>Technologies Used</b>

React, Tailwind CSS, Gatsby, WordPress

<b>Challenges and Iterative Design</b>


Initially, one of the key challenges was the organization of the extensive blog content. Users often felt overwhelmed, and this was reflected in the lack of specific feedback on the blog's usability. To address this, there needed to be a way to categorize and present content in a more user-friendly manner.

Implementing the submenu and category pages also posed technical challenges. I had to ensure that the navigation system was fast and responsive, especially as the blog had hundreds of posts. Integrating this seamlessly with WordPress, which was one of the website's content management systems, required careful planning.

<b>Design and Development</b>

The first design iteration involved the concept of introducing a submenu. Providing users with a quick way to navigate to specific categories would alleviate the issue of content overload.

To make the submenu more engaging, I implemented dynamic features using React. Users could now interact with the submenu, and clicking a button would take them to the corresponding category page. I also introduced auto-scrolling to create a seamless content exploration experience.

<img src="https://i.imgur.com/upjGlHc.png" height="80%" width="80%" alt="Blog Submenu"/>
  
After some feedback from the design team, I made the following refinements to improve user navigation as well as overall visual presentation:

- When a chip (e.g., "Symptoms") was selected, it showed as selected on the "Symptoms" page, providing users with a clear indication of their current location within the navigation
- Clicking on a tab immediately took users to a parent page of that title, eliminating confusion caused by sub-categories being initially displayed
- Once on the parent page, which as denoted by a tab such as "Gathering Information", users could easily select a subcategory to narrow down results. To facilitate this, an additional chip labeled "All" was added. This chip was selected by default when clicking on a tab.

<img src="https://i.imgur.com/xONWX3N.jpg"/>


<b>Before Implementation</b>
<img src="https://i.imgur.com/qvLhXCk.png"/>

<b>After Implementation</b>
<img src="https://i.imgur.com/xONWX3N.jpg"/>

<b>Results and Achievements</b>

- 30% increase in page views for blog content
- 20% increase in time on page for blog content
