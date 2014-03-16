Git based registry - the idea in general
========================================

Intro
-----

There are things like npmjs and bower and their primary functionality is
to act as a repository of various components. To function they need cpu time,
bandwith, maintenance and whatever not. This is too much hassle. Why not set
up something that can function without all of those thing needed to be performed
by you and just use it and forget all the hassle. The only work is done is the 
initial kick off, from there it all functions by itself. Which means, all the
processing is handled by github and all the maintenance is done by component
owner.

How would this work
-------------------

Well, first of all, github provides nice feature of creating the *organization* and
a bunch of repos under it. It also provides nice api.

Theres another thing, called [Webshell](http://webshell.io) which lets you combine
apis and create your own custom api access points.

Utilizing the above two we end up with something like that:
-----------------------------------------------------------

We create an organization on github, lets name it *foobar-registry* and set up a simple
api with webshell. The api is set up in a way that it can create repositories under
our *foobar-registry* organization. The repositories are actually just forks of other
github repositories. The forked repository name should be statically *prefixed*.
The repository will not be forked if the name is already taken.

So, assuming we have successfully managed to utilize webshell and github features,
and created the working *foobar-registry*. This is how it functions:

1. User *moga* creates some *component* which happens to be a valid component.

2. User *moga* goes to our *foobar-registry* and submits a request to fork his repo.

3. The requrest is passed to our webshell api and creates the *component* repo fork,
   also, giving commit rights to the user *moga*

4. PROFIT!!!

From here on, *moga* is responsible for maintaining his *component*

The client for the registry is not something complicated, because it utilizes the features
github provides.

Thats basically it.

