# testing01
this is just a test
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8"/>
    <title>Prototype: Flickr API - Display Photos (JSON)</title>
  </head>
  <body>
    <h1>Search/Filter the Flickr API</h1>
    <div id="feed"></div>
    <script type="text/javascript">
      // This function parses the JSON response and displays the photos
      function jsonFlickrFeed(fr) {
        var container = document.getElementById("feed");
        var markup = '<h1>' + '<a href="' + fr.link+ '">' + fr.title + '</a>'+ '</h1>';
        for (var i = 0; i < fr.items.length; i++) {
          markup += '<a title="' + fr.items[i].title + '" href="' + fr.items[i].link + '"><img src="' + fr.items[i].media.m + '" alt="' + fr.items[i].title + '"></a>';
        }
        container.innerHTML = markup;
      }
    </script>
    <!-- Make request to the Flickr API specifying the JSON format, callback function, and search tag -->
    <script type="text/javascript" src="https://api.flickr.com/services/feeds/photos_public.gne?tags=alaac14&format=json&jsoncallback=jsonFlickrFeed"></script>
  </body>
</html>
