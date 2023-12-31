# Custom Sitemap Index to Organize an Ever-Changing, Multi-Level Site

<b>Client</b>

RehabPath

<b>Client Industry</b>

Addiction Treatment and Mental Health

<b>Project Scale</b>

Approximately 40,000 pages were evaluated in order to be included or excluded from the sitemap index.

<b>Technologies Used</b>

JavaScript (ES6), Gatsby, GraphQL, Firestore

<b>Business Challenge and User Need</b>

Prior to this project, the website faced challenges in efficiently communicating its structure to search engines and maximizing organic traffic. This initiative was undertaken to enhance the website's structure and organic visibility through the implementation of a custom sitemap index. This innovative solution aimed to serve as a directory for multiple sitemaps, aiding search engines in comprehending the website's hierarchy and thereby improving the visibility of its pages. 

<b>Discovery Findings</b>

The project commenced with a comprehensive analysis of the website's organic visibility and search engine indexing. This analysis included:

*Search Engine Indexing Analysis*

I assessed how search engines were indexing the website. This evaluation revealed that there were many locations and specialties that were not getting discovered for indexing, which revealed an opportunity to provide search engines with a clearer understanding of the content hierarchy.

*User Behavior Analysis*

Results from user tests revealed that users often struggled to navigate between different sections of the website effectively. This highlighted the need for improved cross-linking and navigation.

<b>Implementation Details</b>

Execution involved several technical components and steps, including the use of loops to iterate through URLs tagged with specific taxonomies in each sitemap category, and a special configuration to filter out pages missing a robots noindex tag.

The sitemap index was developed to reflect the business model of the site, which was a directory of treatment centers and other medical facilities offering treatment for various conditions. Each sitemap was created based on a key offering and corresponding URL path:
- <b>Location</b>: Locations where medical facilities were located
- <b>Condition</b>: Conditions that facilities treated. Example URL paths were /condition/depression/, /condition/schizophrenia/, etc.
- <b>Taxonomies</b>: This encompassed multiple categories, including treatment therapies, insurance providers, and types of clientele.
- <b>Resources</b>: All blog posts. Example path would be /resources/what-is-rehab/
- <b>Utility</b>: Web pages that serve a functional or informational purpose, often unrelated to the core content or primary navigation of the site. Examples include homepage, about us page, contact page, etc.

Once a user clicked on one of the high-level sitemaps, they could see all the URLs associated with a particular category. 

<img src="https://i.imgur.com/cBQFUqp.png">

This example is a snapshot of all the locations on the site stored in the locations sitemap.

<img src="https://i.imgur.com/6630vKV.png">

*Data Retrieval from Firestore*

I configured GraphQL queries to fetch content data and metadata, crucial for constructing the sitemap index. GraphQL's flexibility allowed me to precisely tailor the data retrieval process to meet the needs of the various sitemaps.

*Filtering Out Non-Indexable Pages*

One of the critical aspects of this project was the necessity for filtering. The website contained around 7,000 indexable pages, accompanied by hundreds of thousands of non-indexable pages with parameters. These non-indexable pages, due to their sheer volume, posed a significant challenge to search engine indexing and the overall website's organic visibility.

Reflecting the behavior of an e-commerce site, the URL structure would evolve according to any filters that the user selected. One the user selected at least three filters, each URL would contain parameters. These kinds of URLs were not to be indexed, since there were thousands of pages on the site that were nearly the same besides a few filters.

<img src="https://i.imgur.com/lhPhw9X.png">

Thus, it was crucial to ensure URLs like the one below were not included in the sitemap index:

https://luxuryrehabs.com/browse/?refinementList%5Blocations%5D=Florida&refinementList%5Bwhat_we_treat%5D=Alcohol&refinementList%5Baccepted_insurance%5D%

The filtering mechanism played a pivotal role in excluding non-indexable pages from the sitemap index. This selective approach ensured that only relevant and indexable content was included, preventing search engines from wasting resources on non-indexable pages with largely duplicate content. As a result, the custom sitemap index served as an efficient and streamlined directory, facilitating improved search engine indexing and enhancing the website's visibility.

<b>Benefits and Achievements</b>

- 20% increase in the number of pages indexed by search engines. This boost in indexing contributed to increased organic traffic and visibility.
- 30% reduction in indexing time. This expedited the appearance of new content in search results, enhancing the website's visibility.
