# Omnis2Lightbox for Omnis 8.1
Demo how to call the lightbox library from an Omnis remote form

The BasicLightbox js library provides a simple a straightforward way to display images and videos by filling the screen, and dimming out the rest of the web page. 

The project page is https://basiclightbox.electerious.com/

Its github is https://github.com/electerious/basicLightbox

Ths Omnis2Lightbox library for Omnis 8.1 demoes how to call BasicLightbox from an Omnis remoteform, eventually passing parameters from Omnis to the lightbox.



## Installation

1. Put basicLightbox.min.css and basicLightox.min.js in the html folder of your Omnis environment.

2. Backup your jsctempl.htm file located in the html folder then replace it with the jsctempl.htm provided or alternatively you can modify your jsctempl.htm file :

- Add the link to basicLightbox style in the head section

~~~~
<link type="text/css" href="basicLightbox.min.css" rel="stylesheet" media="print, screen" />
~~~~ 

- Add the script below in the end of the body section 

~~~~javascript 
    <script src="basicLightbox.min.js"></script>
    <script>
        function showImage(src, width, height) {
            src = typeof src !== "undefined" ? src : "https://placehold.it/1400x900";
            width = typeof width !== "undefined" ? width : "1400";
            height = typeof height !== "undefined" ? height : "900";

            basicLightbox.create(`<img width="${width}" height="${height}" src="${src}">`).show()
        }

        function playVideo(src, width, height) {
            src = typeof src !== "undefined" ? src : "";
            width = typeof width !== "undefined" ? width : "560";
            height = typeof height !== "undefined" ? height : "315";

            basicLightbox.create(`
                <iframe width="${width}" height="${height}" src="${src}" frameborder="0" allowfullscreen></iframe>
            `).show()
        }

        function showHtml(html) {
            html = typeof html !== "undefined" ? html : "<h2>Message</h2>";

            basicLightbox.create(`${html}`).show()
        }
    </script>
~~~~



## Use

You can then open the Omnis2LightBox.lbs library and do a "test form" on the omnisform class.

![Omnis Form] (https://brunobydesign.github.io/Omnis2LightboxForm.jpeg)


Clicking on one the form's button will call the Lightbox functions with the provided parameters

![Video on top of Omnis Form] (https://brunobydesign.github.io/Omnis2LightboxForm2Video.jpeg)







    

