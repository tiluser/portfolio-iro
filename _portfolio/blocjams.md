---
layout: post
title: blocJams
feature-img: "img/blocJams.jpg"
thumbnail-path: "https://d13yacurqjgara.cloudfront.net/users/3217/screenshots/2030966/blocjams_1x.png"
short-description: blocJams can organize and play your favorite tunes. 

---

<strong>Summary</strong> 

blocJams is a BLOC student project that allows the developer to organize songs into a collection of albums, and to play each song in the album.

<strong>Explanation</strong>

Modules 1 and 2 of BLOC focus on building a core foundation of the following skill sets: 
<ol>
<li>Web-based development using HTML, CSS, JavaScript, and jQuery using the Atom IDE.</li>
<li>Version control using Git and Github, and Git bash. </li>
</ol>

The BlocJams project makes use of all of the coding, IDE, and version control skills listed above.

<strong>Problem</strong> 

BlocJams minimally requires the following components and pieces of functionality: 
<ol>
<li>A landing page.</li>
<li>A collections page that lists the albums.</li>
<li>A songs page where individual songs of the album are listed and can be played.</li>
<li>Song navigation code.</li>
<li>Volume control.</li>
<li>An audio library to play the songs.</li>
<li>Usability on a variety of devices ranging from laptops to iPhones</li>
<li>Storage of song and album information.</li> 
</ol>


<strong>Solution(s)</strong>

<ol>
<li>The landing page is configured to pop up an animation of selling points via jQuery. The trigger that pops it up is the distance the user has scrolled down. </li>

{% highlight javascript %}
    var scrollDistance = $('.selling-points').offset().top 
        - $(window).height() + 200;

    $(window).scroll(function(event) {
        if ($(window).scrollTop() >= scrollDistance) {
            animatePoints();
        }
    });
{% endhighlight %}

<li>A collections page that lists the albums is displayed using a div grid.</li>
<li>Songs on the songs page are represented as JavaScript/jQuery objects. Song rows are dynamically generated with JavaScript as below.</li> 
{% highlight javascript %}
var createSongRow = function(songNumber, songName, songLength) {
    var template =
      '<tr class="album-view-song-item">'
    + '  <td class="song-item-number" data-song-number="' + songNumber + '">' 
    + songNumber + '</td>'
    + '  <td class="song-item-title">' + songName + '</td>'
    + '  <td class="song-item-duration">' + songLength + '</td>'
    + '</tr>'
    ;
    var $row = $(template);
    var songItemNumber;
    var songItemNumbers = [];
    var onHover = function (event) {
        // Placeholder for function logic
       if ($(event.target.parentElement).find('.song-item-number').text() !== ""
              && $(event.target.parentElement).find('.song-item-number').html() 
              !== pauseButtonTemplate) {
           songItemNumber = parseInt($(event.target.parentElement).find('.song-item-number').text());
           $(event.target.parentElement).find('.song-item-number').html(playButtonTemplate);
       }
    };
// remainder of code ...
};
{% endhighlight %}
<li>
Song navigation is based on the song number. The interface allows navigation through a navigation bar or by directly clicking on a song row. The code to handle navigation is the most complex piece of the application, with code specific for the onclick, onHover, offHover, mousedown, mousemove, and mouseup events.
</li>
<br />
<li>Volume control is coordinated with a thumb bar using the updateSeekPercentage function.</li>
{% highlight javascript %}
var updateSeekPercentage = function($seekBar, seekBarFillRatio) {
    var offsetXPercent = seekBarFillRatio * 100;
    // #1
    offsetXPercent = Math.max(0, offsetXPercent);
    offsetXPercent = Math.min(100, offsetXPercent);

    // #2
    var percentageString = offsetXPercent + '%';
    $seekBar.find('.fill').width(percentageString);
    $seekBar.find('.thumb').css({left: percentageString});
};
{% endhighlight %}

<li>Songs are played using the Buzzfeed library.</li> 
<br />
<li>Viewports and media ranges allow the app to be usable on a variety of devices.</li>
<br />
<li>Song and album information is stored in a separate JavaScript source file in a hierarchical key/value format.</li>
<br />
{% highlight javascript %}
var albumPicasso = {
    title: "The Colors",
    artist: "Pablo Picasso",
    label: "Cubism",
    year: "1881",
    albumArtUrl: 'assets/images/album_covers/01.png',
    songs: [
        { title: 'Blue', duration: 161.71, audioUrl: 'assets/music/blue' },
        { title: 'Green', duration: 103.96, audioUrl: 'assets/music/green' },
        { title: 'Red', duration: 268.45, audioUrl: 'assets/music/red' },
        { title: 'Pink', duration: 153.14, audioUrl: 'assets/music/pink' },
        { title: 'Magenta', duration: 374.22, audioUrl: 'assets/music/magenta' }
    ]
};
{% endhighlight %}
</ol>

<strong>Results</strong>

Through systematic development and the use of HTML5, CSS, JavaScript, jQuery, and the Buzzfeed audio library, a small
song organizing and playing application was developed. The amount of code that needed to be written was moderate (less than 1500 lines).

<!-- author-classification-278...872.netlify.com -->

Screenshot 1. Landing page
{:.center}
![]({{ site.baseurl }}/img/blocjams_landing.png)
<br />

Screenshot 2. Collections page
{:.center}
![]({{ site.baseurl }}/img/blocjams_collection.png)
<br />

Screenshot 3. Album/song page
{:.center}
![]({{ site.baseurl }}/img/blocjams_albumsong.png)
<br />


<strong>Conclusion</strong>

The usage of the jQuery library offered a definite advantage in terms of compactness of code and easy accessibiity of the DOM. 
Some possible negatives are the overhead of using a library, and the "black-box" nature of its use. Since the BLOC checkpoints often involved
coding first in JavaScript and then recoding with jQuery, the impact of the second issue was minimized.  
