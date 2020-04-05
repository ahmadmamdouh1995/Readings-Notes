## “Roy Fielding”

It helped write the first web servers, that sent documents across the Internet… and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.

## How does that work?

Well, it's all pretty amazing really. And the funny thing is that it's all very undervalued. The protocol I mentioned, that he helped write, HTTP, it's capable of all sorts of neat stuff that people ignore for some reason

## “http” like the beginning of what I type into the browser
it is capable of describing the location of something anywhere in the world from anywhere in the world. It's the foundation of the web. You can think of it like GPS coordinates for knowledge and information.
For anything really. That guy, Roy Fielding, he talks a lot about what those things point to in that research I was talking about. The whole world wide web is built on an architectural style called “REST”. REST provides a definition of a “resource”, which is what those things point to.

##  A web page is a resource?

Kind of. A web page is a “representation” of a resource. Resources are just concepts. URLs--those things that you type into the browser

## other kinds of representations

Actually, representations is one of these things that doesn't get used a lot. In most cases, a resource has only a single representation. But we're hoping that representations will be used more in the future because there's a bunch of new formats popping up all over the place.

The URL, of course. If everything that machines need to talk about has a corresponding URL, you've created the machine equivalent of a noun. That you and I and the rest of the world have agreed on talking about nouns in a certain way is pretty important, 

## Machines don't have a universal noun - that's why they suck. Every programming language, database, or other kind of system has a different way of talking about nouns. That's why the URL is so important. It let's all of these systems tell each other about each other's nouns.

## There's a powerful concept in programming and CS theory called “polymorphism”. That's a geeky way of saying that different nouns can have the same verb applied to them.

## Our brains are somehow smart enough to know that the same verbs, like GET, can be applied to many different nouns. Some verbs are more specific than others and apply only to a small set of nouns. For instance, I can't drive a cup and I can't drink a car. But some verbs are almost universal like GET, PUT, and DELETE.

##  HTTP—this protocol Fielding and his friends created—is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you type in and back comes a web page.

Web pages usually have images, right? Those are separate resources. The web page just specifies the URLs to the images and the browser goes and does more GETs using the HTTP protocol on them until all the resources are obtained and the web page is displayed. But the important thing here is that very different kinds of nouns can be treated the same. Whether the noun is an image, text, video, an mp3, a slideshow, whatever. I can GET all of those things the same way given a URL.

Especially when you're using a web browser because browsers pretty much just GET stuff. They don't do a lot of other types of interaction with resources. This is a problem because it has led many people to assume that HTTP is just for GETing. But HTTP is actually a general purpose protocol for applying verbs to nouns.

web pages are designed to be understood by people. A machine doesn't care about layout and styling. Machines basically just need the data. Ideally, every URL would have a human readable and a machine readable representation. When a machine GETs the resource, it will ask for the machine readable one. When a browser GETs a resource for a human, it will ask for the human readable one.

## 