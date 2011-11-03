Nut 0.1.7
=========

Nut is a concise query selector engine that just allows you to do extremely simple queries.

First of all, nut is, most of the time, faster than `querySelectorAll` (take a look at the benchmark) and then faster than all selector engines. But please note that nut doesn't implement request caching (to avoid unnecessary code additions and performance loss) because the user can easily keep a request and pass it as a context to another request. This is, nut aims to be minimal to have a very tiny footprint and extreme velocity based on the observation that much of CSS requests could be kept as simple as we can since javascript can handle a lot of things.

Use
---

Here's it can handle:

    #foo
    section
    .bar p
    section #foo .bar p
    div,#foo,.bar

And here's it can't:

    div#foo div.bar
    div *
    div > p
    div + p

So, all pseudo-classes, attribute selectors and other advanced syntax are not allowed. But, let's dig in:

    // Return an array
    nut('#foo');

Of course, queries can have a context (an array, a NodeList, or a node):

    // Get nodes from the #foo context
    nut('.bar p',nut('#foo'));

And that's all you need to know ;)

Ender
-----

Nut can be integrated to ender and is already in NPM! 