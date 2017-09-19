---
layout: post
title: BlocChat
feature-img: "img/sample_feature_img.png"
thumbnail-path: "https://d13yacurqjgara.cloudfront.net/users/3217/screenshots/2030974/bloctalk_1x.png"
short-description: BlocJams for iOS is awesome!

---

<strong>Summary</strong>  

blocChat is a BLOC student project that uses Angular for a single-page messaging board. 

<strong>Explanation</strong> 

The BLOC curriculum introduced Angular in the form of translating a project that was previously done in Javascript and jQuery into Angular. Although the functionality was similar, the underlying structure was of course much different. In both cases, detailed instruction on how to develop the app was given in each of the checkpoints, even though many of the pieces had to be filled in by the student.

In contrast, most of the 'givens' for blocChat were much more loosely defined so it is up to the student to take more individual responsibility for the structure and layout of the application.   

<strong>Problem</strong> 

The blocChat application is an SPA (single-page application) that requires the following components:
<ol>
<li>A list of available chat rooms.</li>
<li>A modal dialog box that can add more rooms on demand.</li>
<li>A section for posting and reviewing messages for each room that has the focus.</li>
<li>Storage and display for the name of the user on the system.</li>
</ol>

<strong>Solution</strong>

The list of chatrooms is stored in a Firebase database and accessed through the Room service. Messages are
stored in a separate table but are keyed to each room through the room id which is stored with each posted
message. They are added through the Message service. 


The identity of the message poster is handled through the BlocChatCookies service and is stored in a cookie.
If the value is not already present, a modal dialog box pops up that requires the user to enter his/her name. 
The code for this is set to always run and is not configured as an on-demand service or factory. 

Routing is extremely simple, with only one page (home) in the routing table. The chatroom list and message lists are
coded in separate divs on the same page and the modal ctrl is included with the ngInclude directive. Even though the
modal control requires its own controller, it is directly referred to in the code instead of being included in the
routing.

<strong>Results</strong>

blocChat is a simple but functional messaging app which allows users to post messages to a publicly availablly set of
chat rooms. It only required a few hundred lines of code. 

<strong>Conclusion</strong> 

Angular offers an ecosystem of tools and a methodology of code partitioning that allows rich applications
to be developed with a minimal amount of coding. There may be a learning curve in taking advantage of the functionality
available. 


