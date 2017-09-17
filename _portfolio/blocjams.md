---
layout: post
title: BlocJams
feature-img: "img/sample_feature_img.png"
thumbnail-path: "https://d13yacurqjgara.cloudfront.net/users/3217/screenshots/2030966/blocjams_1x.png"
short-description: BlocJams organizes your songs into albums and lets you play each song in an easy-to-navigate interface.

---


Summary: This is a BLOC student project that allows the developer to organize songs into a collection of albums, and to play each song in the album.

Explanation: Modules 1 and 2 of BLOC focus on building a core foundation of the following skill sets: 
1. Web-based development using HTML, CSS, JavaScript, and jQuery using the Atom IDE.
2. Version control using Git and Github, and Git bash. 

The BlocJams project made use of all of the coding, IDE, and version control skills.

Problem: BlocJams consists of the following components: a landing page with selling points that pop up unobtrusively, a collections page that lists the albums, 
and a songs page where individual songs of the album can be played. On the songs page, there must be a means to navigate from one song to another, play/pause 
the songs, and control the volume. There must also be a picture on top of the songs page which dsplays a carousel of choices - clicking on the picture navigates 
to the next picture. The application must be usable on a variety of devices ranging from laptops to iPhones. 

Solution:

1. Landing page - unobtrusive pop up through animations
2. Landing page - display on wide variety of devices (viewport, breakpoints, and media queries)
3. Landing page - choice of box-sizing (border box)
4. Overall philosophy - responsive web design.
5. Album pages - display of multiple albums. Used a table grid. 
6. Songs. Represented as JavaScript objects. SongRows are dynamically generated with JavaScript. 
7. Songs. Playing/pausing - event delegation tracks the mouse's position. Event bubbling allows firing on a child element to propage up. Song number - keeping track of. Mouseover t change icon. 
8. Adding player controls and volume controls. 
9. Using jQuery selectors on landing.js to animate the points when scrolling down - lnding page. 
10. Refactoring into jQuery using selectors on album page. 
11. Creating a song row with jQuery. 
12. Next and previous song navigation. 
13. Buzzfeed library usage. 
14. Getting song durations and updating seek bars. 

Results: 

Conclusion:
