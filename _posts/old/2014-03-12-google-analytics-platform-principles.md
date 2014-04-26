---
title: Google Analytics Platform Principles
author: 肖庆
layout: post
permalink: /google-analytics/google-analytics-platform-principles/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 684
categories:
  - Google Analytics
tags:
  - Analytics Academy
  - Google Analytics Platform Principles
---
<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> Platform Principles is the latest Web Analytics learning course presented by Google Analytics team, below is the exercises excerpted from the <a title="Google Analytics Platform Principles" href="https://analyticsacademy.withgoogle.com/course02" target="_blank">official website</a>. It&#8217;s just for note-taking, and it&#8217;s strongly suggested that you watch all the videos first and if there is anything unclear, check the help center or google it. If you would like to check the answers, the full documents with answers and videos is available via <a title="Google Analytics Platform Principles" href="http://ga.xiaoq.in/course02/" target="_blank">this link</a>.

<img class="alignnone size-full wp-image-1643" alt="google analytics platform principals" src="https://xiaoq.in/cdn/2014/03/google-analytics-platform-principals.gif" width="345" height="220" />

Unit 1  
Course overview  
The platform components  
The data model  
Unit 2  
Data collection overview  
Website data collection  
Mobile app data collection  
Measurement Protocol data collection  
Unit 3  
Processing & configuration overview  
Processing hits into sessions & users  
Importing data into Google Analytics  
Transforming & aggregating data  
Unit 4  
Reporting overview  
Building reports with dimensions & metrics  
The reporting APIs  
Report sampling  
Final Assessment

Video download: http://ga.xiaoq.in/

Copyright by Google, Edited by xiaoq.in

Print below or Learn the Video First!!!

Activity 1.2 &#8211; The platform components  
1. What are the four main parts of the Google Analytics platform?  
A. Collection, Processing, Continuation, and Reporting  
B. Configuration, Processing, Reporting, and Recollection  
C. Configuration, Collection, Progressing, and Reporting  
D. Collection, Configuration, Processing, and Reporting  
2. During data Processing, Google Analytics:  
A. transforms the raw data from Collection using the Configuration settings  
B. collects the data from Analytics tracking code added to a website, mobile application or other digital environment  
C. lets you access and analyze your data using the Reporting interface  
D. lets you adjust Configuration settings before data is collected  
3. Once your Google Analytics data has been processed, it can not be changed.  
A. True  
B. False

Activity 1.3 &#8211; The data model  
4. What is the hierarchy of the Google Analytics data model?  
A. Interactions > Users > Sessions  
B. Sessions > Users > Interactions  
C. Users > Sessions > Interactions  
D. Sessions > Visitors > Interactions  
5. Google Analytics is able to measure if a a user is a first time visitor or repeat visitor.  
A. True  
B. False  
6. Which of the following interactions are considered &#8220;hits&#8221; by default in Google Analytics? (select all that apply)  
A. Pageviews  
B. Reservations  
C. Events  
D. Transactions

Activity 2.1 &#8211; Data collection overview  
7. The tracking code in Google Analytics: (select all that apply)  
A. connects data to your specific Google Analytics account  
B. sends data back to your Google Analytics account for reporting  
C. tracks changes in your AdWords account  
D. identifies new and returning users  
8. The same type of Google Analytics tracking code should be used for both a website and a mobile app.  
A. True  
B. False

Activity 2.2 &#8211; Website data collection  
9. You should include Google Analytics tracking code on every page of a website you want to track.  
A. True  
B. False  
10. Where does the Google Analytics tracking code belong?  
A. After the closing tag in your HTML  
B. Before the closing tag in your HTML  
C. After the closing tag in your HTML  
D. Before the closing tag in your HTML  
11. In order to distinguish between users on web pages, Google Analytics:  
A. uses the IP address of a device that accesses the site  
B. uses the city, state and country of a visitor that access the site  
C. creates anonymous unique identifiers using third-party cookies  
D. creates anonymous unique identifiers using first-party cookies

Activity 2.3 &#8211; Mobile app data collection  
12. For mobile applications, Google Analytics will use the same Javascript tracking code as websites.  
A. True  
B. False  
13. Google Analytics stores mobile app usage data locally on the device and sends it to the Analytics account later using a batch process called:  
A. resending  
B. rerouting  
C. dispatching  
D. displacing  
14. If an app gets uninstalled and then reinstalled, Google Analytics will have to create a new unique identifier on the device instead of matching the session as coming from a returning user.  
A. True  
B. False

Activity 2.4 &#8211; Measurement Protocol data collection  
15. The measurement protocol can collect and send user activity data to Google Analytics from any web-connected device, such as a ticket kiosk.  
A. True  
B. False  
16. Similar to the JavaScript and mobile SDKs, you’ll need to include a tracking ID with each hit collected by the Measurement Protocol.  
A. True  
B. False

Activity 3.1 &#8211; Processing & configuration overview  
17. When Google Analytics processes data, one of the main tasks it completes is organizing hits into:  
A. users and sessions  
B. cohorts and interactions  
C. registered users and browsers  
D. purchasers and browsers  
18. Third-party data may be joined with the Google Analytics data collected via the tracking code.  
A. True  
B. False  
19. During aggregation, Google Analytics:  
A. exports the collected data into a Google Spreadsheet  
B. organizes the collected data into pivot tables  
C. organizes the collected data within database tables  
D. samples the data immediately

Activity 3.2 &#8211; Processing hits into sessions and users  
20. How is Google Analytics able to determine if a group of website interactions are all from the same user device?  
A. By detecting what city, operating system and browser the hits come from  
B. By setting a unique ID for the device that is attached to each hit  
C. By grouping together all hits that are collected within a 30 minute time period  
D. Google Analytics is not able to detect if a group of interactions are from the same user device  
21. Rather than using the random numbers that the tracking code creates, you can override the unique ID with your own number.  
A. True  
B. False  
22. A session in Google Analytics consists of:  
A. The reports generated by users over a specific period of time  
B. Interactions or hits from a specific user for all time  
C. Interactions or hits from a specific user over a defined period of time  
D. A group of users getting together in person to discuss analytics  
23. By default, an Analytics session ends when inactive for:  
A. 15 minutes  
B. 30 minutes  
C. 45 minutes  
D. 60 minutes

Activity 3.3 &#8211; Importing data into Google Analytics  
24. How can you add data to Google Analytics from other sources? (select all that apply)  
A. Link your AdWords account to Google Analytics to import advertising data  
B. Use Cost Data Upload to import click and cost data from non-AdWords campaigns  
C. Upload a .csv file to Google Analytics to attach new dimensions to existing dimensions  
D. Upload data to Google Spreadsheets and automatically sync it with your Google Analytics account  
25. To add external data to Google Analytics using the Data Import feature, you must have:  
A. a key that links the imported data with Google Analytics  
B. a key that links the imported data with your AdWords account  
C. an SDK that links the imported data with Google Analytics  
D. an API that links the imported data with your AdWords account  
26. What are the two methods of importing external data into Google Analytics using Dimension Widening? (select all that apply)  
A. Linking to Google Spreadsheets  
B. Using the Mobile SDKs  
C. Using the API  
D. Uploading a spreadsheet or CSV file

Activity 3.4 &#8211; Transforming & aggregating data  
27. Which of the following are configurations that permanently modify your data during the processing stage? (select all that apply)  
A. Channel Groups  
B. Content Groups  
C. Custom Reports  
D. Filters  
E. Goals  
F. Javascript Customization  
28. Filters can modify the data in your Google Analytics reports by: (select all that apply)  
A. including data  
B. excluding data  
C. exporting data  
D. changing how data looks in reports  
29. Google Analytics Goals let you specify:  
A. which users are likely to convert  
B. which interactions should be used to calculate conversions  
C. which users spend the most time on your home page  
D. which page or screen is the first of a user&#8217;s visit  
30. Which types of groups can you create in Google Analytics? (select all that apply)  
A. Channel Groups  
B. Conversion Groups  
C. Content Groups  
D. Conversation Groups

Activity 4.1 &#8211; Reporting overview  
31. You can retrieve Google Analytics reporting data through the following methods: (select all that apply)  
A. the account administration settings  
B. the reporting interface  
C. the SDKs  
D. an API  
32. The process Google Analytics uses to retrieve data from large, complex data sets faster is called:  
A. retrieval  
B. expediency  
C. sampling  
D. configuration

Activity 4.2 &#8211; Building reports with dimensions & metrics  
33. The following are examples of dimensions: (select all that apply)  
A. Traffic source  
B. Page name  
C. Country  
D. Unique visitors  
34. The following are examples of metrics: (select all that apply)  
A. Unique visitors  
B. Page name  
C. Average visit duration  
D. Traffic source  
35. Every metric may be combined with every dimension in Google Analytics.  
A. True  
B. False  
36. You want to create a report comparing the performance of pages on your site and decide to use the following dimensions and metrics: Page Title, Avg. Visit Duration, Goal 1 Conversion Rate. Which of the following statements is true about this report?  
A. Google Analytics will allow you to create this report, and the report makes sense since you chose to combine hit-level metrics with the hit-level dimension Page Title.  
B. Google Analytics will allow you to create this report, but the report does not make sense since you chose to combine session-level metrics with the hit-level dimension Page Title.  
C. Google Analytics will not allow you to create this report.

Activity 4.3 &#8211; The reporting APIs  
37. The reporting APIs can be used to: (select all that apply)  
A. automate complex reporting tasks  
B. automate your tracking code customizations  
C. retrieve Google Analytics data for use in your own applications  
D. build your own dashboard with Google Analytics data  
38. Each query sent to the Reporting API must specify: (select all that apply)  
A. the start and end dates  
B. the name of the standard report you wish to use  
C. which metrics to display  
D. the ID of the account view that the data should be retrieved from

Activity 4.4 &#8211; Report sampling  
39. If the data for a report you request is stored in a standard aggregate table, it will never be sampled in Google Analytics.  
A. True  
B. False  
40. If you decrease the sample size for a report, more sessions will be used to calculate the report and it will take longer to generate.  
A. True  
B. False  
41. You can adjust the sample size by: (select all that apply)  
A. adding a segment to your report  
B. adjusting the session timeout control  
C. adjusting a control in the reporting interface  
D. specifying the sample size when querying the API