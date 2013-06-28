# Content scripts

Content scripts are javascripts and stylesheets that are simply injected at the top of a page's html.
Ad blockers are content scripts. The majority of killer extensions are content scripts.
5.5 of the 7 extensions I've made are content scripts.

#### Content scripts I've made

Need to be placed at very top of page:
> 1. Scout - modify google<br>
2. HMU extension - post to my social network right from facebook<br>
3. Facebook comments extension - click a browser button and inject facebook comments.<br>
4. Extension for Sergey - add thred search results to facebook search<br>
5. Extension for Jobs2Web - on a person's LinkedIn, add them to the database<br>

Injects menu when you click a browser button:<br>
> 6. Extension for TrackIf - injects a menu for tracking if a products price changes<br>

Omnibox extension:<br>
> 7. tweet-bar: Write a tweet from the address bar.<br>

Mobile also presents a new realm of potential content scripts, turn numbers into call buttons, personalize based on location,
maybe even use a siri api? Mobile presents some really interesting possibilities. To make this secure, 

Now, how to implement this on all browsers? I think the best way might be to use proxies -
which I think skyfire already has architected. On the server, content scripts are just injected to the html.


Api:
Declarative api's put you in a box, so let's avoidt, even though they can be the easiest to implement.

A programmatic api allows an extension developer to work around potential bugs or limitations.

Each extension can have one event page in the background.<br>
It's not continually running, but runs once, and the javascript binds to the events it cares about.

We could call the extension namespace simply `skyfire`<br>
To register a content script, you might do this:
```
skyfire.on('url change', function(url) {
  return skyfire.injectHtml('<script></script>');
});
```

