# Heuristics 1001

These are the heuristics that I and some of my colleagues find useful in our software engineering practice. We call “heuristics” everything that helps us to write better code given we keep them in mind.

Some heuristics are of our own, sometimes we also learn from good books: heuristics here that are cited always have reference to original.

All of those heuristics work for us only if taken altogether. Taken away from the rest, some of them can even contradict each other: if you take only few of them and exaggerate them, they will lose their value or even break things on your behalf. So do not be very serious about them :) 

Currently this is just a draft, very far from complete, with some random notes arbitrarily organized, do not expect it to be solid. If still this folklore genre works for you, feel free to share heuristics you might have in mind.

## General

- Habitability Heuristics. Habitable software is better than perfect software, both for its users and its developers (Richard Gabriel - Patterns of Software).
- Poor Abstraction Heuristics.

> Duplication is better than poor abstraction (Sandi Metz, Rails Club 2014, Moscow).

> "...ill-fitting structure is worse than none..." (Eric Evans - Domain-Driven Design, p.446)

- If feature is hard to implement it might indicate that it is something wrong with feature (or product).

- If you know [True Name](https://en.wikipedia.org/wiki/True_name) of something you have power over it. Good class - this is what True Name is in OOP. See also [Mass and Gravity](http://www.carlopescio.com/2008/12/notes-on-software-design-chapter-2-mass.html).
- Prima Materia Heuristics. Sometimes to make further progress you need to un-implement (break!) particular pattern/architecture/solution and put it back into [Prima Materia](Prima materia - Wikipedia, the free encyclopedia) state and only then thansform it into a something new. Metaphors similar to Prima Materia are "primordial soup" and "indifferentiated soup of ideas" (Eric Evans - DDD).

- Always leave code in a better state than it had been before you got it, save a time for future you or someone else to make it even better (dedicated to folks who enjoy fixing things "in just a few minutes").

- Ignorance Heuristics. Bad code comes from ignorance, not from evil will, inspite of the fact that both bad code and evil will share ignorance as their root. Sometimes it helps a lot to wear imaginary ignorance hat to understand an intention behind a code you're reading.

- Crash Early Heuristics. If you know how to not program defensively in a particular situation go ahead! Otherwise make your code to Crash Early to catch bugs as early as possible: use sensible assertions and stress edge-cases with tests. See [Some notes C in 2016: Code offensively](http://blog.erratasec.com/2016/01/some-notes-c-in-2016.html#.VtGEKBg7T5c) and [Spotify engineering culture (part 2): "We aim to mistakes faster than anyone else"](https://labs.spotify.com/2014/09/20/spotify-engineering-culture-part-2/).

### Complexity

- Black Box with Green Play Button Heuristics. Ideal interface for a system of arbitrary complexity is a black box with a green play button on it - you take the box, press green button and it just works. The second ideal interface is when you also have red button to stop a system.
- Periphery Heuristics. If your reasoning is complicated by cognitive overload that you have after a problem you are trying to solve and there is no obvious way to make a first step towards solution, take a step back and start working with Periphery. Good example is legacy code: poor periphery like bad variable names, wrong responsibilities in classes, even those who are distant to your problem, bad folder structure, etc might look completely irrelevant to the core of your problem but still it contributes to the cognitive overload - try to clean up periphery and you will see that the core of your problem is now more clear and approachable than it was before. Another word for Periphery is Background, see also [Deconcentation of Attention](http://deconcentration-of-attention.com/).

### Control

- One of the key concerns is Control: where control should or should not be, what should have control (be active) and what should not have (passive).
- The lower-level modules should not have control over higher-level modules. It is not only about not having higher-level module imported in lower-level modules and making everything to work through protocols/interfaces but more about what is the flow of control: "what controls what".

### Separation / partitioning

- Separate stable from unstable
- Separate synchronous from asynchronous
- Separate construction from operation (one example: Factory vs Command).
- Separate data from behavior and behavior from data unless you do have good OOP class/object with good data/behavior balance.
- Separate application-level code from system-level code
- Separate methods that read and methods that write

## Testing

- If you do not write tests you will never learn how to write them, it is better to write bad tests then not to write any.
- Ability to do TDD is not about black and white: “can or can not”, it is about having 1001 things in your toolbox: techniques, patterns, tricks and hacks - when you have enough of them you can test almost everything.
- “Legacy code is a code without tests” (“Working effectively with Legacy Code” by Michael Feathers).
- “If you can’t measure it then it can’t be called engineering” (taken from “Object-Oriented Software Engineering: A Use Case Driven Approach” by Ivar Jacobson). We of course also read “measure” as “test” which is another way of measurement.
- Ideally we should be able to test everything: if something is hard to test, then we are just not there with quality of our code or corresponding tool set and infrastructure for testing but we will manage to find or improve them and get there.
If you don’t know or not sure how to test something properly, try the ugliest version first: stub everything in an ugly way, stub network in an ugly way, assert what you want to assert and only then iterate on refactoring of both test and SUT (system-under-test).

## Similar resources

- [Kent Beck - Mastering Programming](https://www.facebook.com/notes/kent-beck/mastering-programming/1184427814923414/)
- [The Law of Leaky Abstractions](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/)


