Feedutil is a lightweight app for pulling RSS/Atom feeds onto your site with django template tags, or custom views. This is not a full feed aggregator like feedjack, but you could write one with it. This is more along the lines of the blogger plugin which allows you to have the latest 5 entries from an RSS feed appear on your sidebar. We use it on the PyCon website for the main about page which has summaries of the latest PyCon Blog entries via Atom, and on an organizer page which replicates a Trac RSS issue feed for open website bugs. This does not use any django models, and there is no database interaction. You could create your own models for managing your feeds, but that is not the purpose of feedutil.

The feedutil provides two primary template tags {% feed feed\_url [posts\_to\_show](posts_to_show.md) [cache\_expires](cache_expires.md) %} and {% get\_feed feed\_url [posts\_to\_show](posts_to_show.md) [cache\_expires](cache_expires.md) as var %}. There is also a higher level interface to feedparser which includes caching pull\_feed(feed\_url, posts\_to\_show=None, cache\_expires=None) => posts\_dict.

This provides a consistent standard interface to all feed types. Extended support for binary blobs coming soon.