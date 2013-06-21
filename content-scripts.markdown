# Content scripts

Content scripts are javascripts (and perhaps stylesheets) that are simply injected
into the page before the network responds with html. Ad blockers are content scripts.
5.5 of the 7 extensions I've made are content scripts.

Content scripts:
Need to run before or with the page's load:
1. Scout - modify google
2. HMU extension - post to my social network right from facebook
3. Facebook comments extension - click a browser button and inject facebook comments.
4. Extension for Sergey - add thred search results to facebook search
5. Extension for Jobs2Web - on a person's LinkedIn, add them to the database

Injects menu when you click a browser button:
Extension for TrackIf - injects a menu for tracking if a products price changes

Omnibox extension:
tweet-bar: Write a tweet from the address bar.

There's shit a mobile content script extension could do to make skyfire the best browser out there.
Mobile web developers would know, I don't do enough with mobile web to know how to make the browsing experience better.

Maybe you even expose a siri api to content scripts! The possibilities are endless, and very interesting on mobile.


Api:
Declarative api's put you in a box, so let's not do that, even though it's the easy way out.

Each extension can have one event page in the background.
It's not continually running, but runs once, and the javascript binds to the events it cares about.

We could call the extension namespace simply `skyfire`
To register a content script, you might do this:
```
skyfire.on('url change', function(url) {
  
  return skyfire.injectHtml('<script></script>');
});
```

