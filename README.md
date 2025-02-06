# testing01
this is just a test
<!DOCTYPE html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8"/>
    <title>Prototype: Flickr API - Display Photos (JSON)</title>
  </head>
  <body>
    <h1>Search/Filter the Flickr API</h1>
    <div id="feed"></div>
    <script type="text/javascript">
    //run function to parse json response, grab title, link, and media values - place in html tags
    function jsonFlickrFeed(fr) {
      var container = document.getElementById("feed");
      var markup = '<h1>' + '<a href="' + fr.link+ '">' + fr.title + '</a>'+ '</h1>';
      for (var i = 0; i < fr.items.length; i++) {
        markup += '<a title="' + fr.items[i].title + '" href="' + fr.items[i].link + '"><img src="' + fr.items[i].media.m + '" alt="' + fr.items[i].title + '"></a>';
      }
      container.innerHTML = markup;
      }
     </script>
     <!-- use script tag to make request to flickr api, specify json format and tag to search -->
     <script type="text/javascript" src="https://api.flickr.com/services/feeds/photos_public.gne?tags=alaac14&format=json"></script>
  </body>
</html>
