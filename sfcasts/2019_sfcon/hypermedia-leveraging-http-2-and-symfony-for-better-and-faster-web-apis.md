# HYPErmedia: leveraging HTTP/2 and Symfony for better and faster web APIs (Kévin Dunglas)

***TIP
SymfonyCon 2019 Amsterdam presentation by [Kévin Dunglas](https://connect.symfony.com/api/alternates/38ddfa21-7c76-42d5-a191-e984d53e7367).

[Talk slides](https://speakerdeck.com/dunglas/2-server-push-and-the-rise-of-client-driven-rest-apis)

Over the years, several formats have been created to fix performance bottlenecks of web APIs: the n+1 problem, over fetching, under fetching… The current hipster solution for these problems is GraphQL. It’s a very smart network hack for HTTP/1, but a hack that is not necessary anymore with HTTP/2 and HTTP/3.

The new versions of the protocol of the web now have native capabilities allowing to create fast and idiomatic web APIs: multiplexing, server push, headers deduplication, compression, persistent connections (Mercure)… Leveraging HTTP/2 and HTTP/3 unveils the true powers of the web (hypermedia architecture) with no compromises with performance.

During this presentation, we’ll learn how to design our APIs to be able to maximize the benefits provided by HTTP/2.
Better, Symfony already contains all the tools you need to create (WebLink, API Platform) and consume (HttpClient) such APIs.
We will discover these gems together.

HATEOAS is the new hype!
***

Transcript & caption for the talk will be added soon.
