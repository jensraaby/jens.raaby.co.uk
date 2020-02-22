---
comments: true
date: 2012-03-19 21:36:47
template: post
draft: false
slug: notes-data-context-interaction
title: 'Notes: Data, Context & Interaction'
wordpress_id: 342
category: Computing
description: "My notes from a talk given by James Coplien on DCI."
---

These are my brief notes based on a talk given by James Coplien ([@jcoplien](http://twitter.com/jcoplien)), at the [Copenhagen Ruby Brigade](http://copenhagenrb.dk/) meet up hosted by [Zendesk](http://zendesk.com) on 19/03/2012. It was great to see a talk given by someone with so much passion and now I feel I have some idea of what [DCI](http://en.wikipedia.org/wiki/Data,_context_and_interaction) is.

Apologies for the sparsity of the notes - they were my attempt at jotting down the talk on my iPad in realtime.

----------<!-- more -->

**Start** with Alan Kay's vision of objects.

Objects are actually used mostly for code libraries.

Software is a service not a product. It has a business value.

Listen to the tests. Code is so simple there are no obvious deficiencies. Or so complicated there are no obvious deficiencies. (Hoare)

Objects take use cases and blow them up. Algorithms are split up all over the place. Polymorphism makes it even worse. Testing comes along because you can't understand the code anymore.

Agile techniques are horseshit when it comes to TDD. It (empirically) makes your code worse.

Unit tests make it hard to refactor. Comment out all code so tests fail. Then rebuild. Coverage tests are stupid. Really hard (impossible) to cover all bases.

Test the use cases not the classes. Classes are scaffolding. Architecture is dynamic - relationship between objects changes all the time. Programming in classes is at odds with business needs. This is what DCI is about.

For Ruby and its programmers' mindset, it is possible once again to do real OOP. Every language apart from Java allows this (!).

Abstraction is evil. It removes information. Don't use it!! To infer any meaning you must flatten hierarchy. You cannot test a class; you must test an object.

DCI is trying to bring us back to OOP. Modern programming destroyed it.

What is a class? You must flatten the hierarchy to understand it. Inheritance is a fancy way to do ”include” statements. Just hiding stuff which is still there. Worst thing is too much coupling between components. Don't sweat class size; worry about use case size.

We need to compress: worry about service we are providing, not the classes. Don't worry about the bricks your building is made from.

You CAN'T TEST A CLASS. what happens in a program occurs between objects not within objects. Methods are simple. A good class is extremely dumb.

Book ”how buildings learn”. About making buildings last a long time. Flimsy = flexible, evolvable.

What is an object about? Object has state (usually), identity (uniqueness), behaviour; it represents a stakeholder mental model; wrappers destroy this.

Models should capture a cognitive concept. A tool sits between the user and computer. Presents a model using a view. The controller coordinates the views. All about people and what they are doing. (Programmers are also people, but that's another matter).

The interesting stuff happens BETWEEN objects.

Classic OO architecture. Tools at the top. Domain models lie underneath.

Fast evolving stuff should be easy to change. Classes are slow to evolve.

Problem with objects is there is no place to put the interesting functions. ”form follows function”. Does function have form?
'Roles' are the form of function.

When you call a method on an object from a class hierarchy: How do you know where the algorithm actually is?
You should wrap this in the context. The objects are dumb. Inject the role into the object, just before executing. The object learns or evolves to have the necessary behaviour and when done unloads that functionality. In Ruby these are modules.

Get objects to collaborate. Separate shear layers. Make money by adding new use cases. Simply load a new context. Nothing else has to change. No models need to be altered. DCI is the only real way to do this.

See [Fulloo.info](http://fulloo.info)

This works - it's not just research.
