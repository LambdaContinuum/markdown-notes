## Introduction
---
The focus here will concern the global structure of space and time. General relativity, our best large-scale physical theory, will be presupposed. Investigation of global structure will allow us to step away from the complex details of this theory and instead examine space and time with an eye towards a number of fundamental features (e.g. topology, causal structure)

## Possible Worlds
---
General relativity determines a class of cosmological models. Each model represents a physically possible world which is compatible with the theory. We take such a model (also called a spacetime) to be an ordered pair (M, g). M is a connected smooth n-dimensional manifold ($n \geq 2$) and g is a smooth Lorentzian metric on M. (Usually n is taken to be four, but possible worlds with other dimensions are also considered. For ease of presentation a number of two-dimensional models will be examined here).

The manifold M captures the shape (topology) of the universe and each point in M represents a possible event. It seems that any event can be characterized by n numbers (one temporal and n - 1 spatial coordinates). So, the local structure of M is characterized by an n-dimensional cartesian coordinate system. Globally, M need not have the same structure. M can have a variety of possible shapes. A number of two-dimensional manifolds are familiar to us: the plane, the sphere, the cylinder, the torus. Any manifold with any closed set of points removed also counts as a manifold. The sphere with the north pole removed is a manifold for example.

A manifold does a fine job of representing the totality of possible events but more structure is needed to capture exactly how these possible events are related. The Lorentzian metric g provides this extra structure. Think of g as a type of function which assigns a length to any vector at any point in M. It's crucial that, at every point in M, the metric g not only assign some positive lengths but also some zero and negative lengths as well. In this way, g partitions all vectors at a point in M into three non-empty classes: the timelike (positive length), the lightlike (zero length), and the spacelike (negative length). The result is a light cone structure at each point in M.  Physically, the light cone structure demarcates the upper bound to the velocities of massive particles (it's central to relativity theory that nothing can travel faster than light).

The light cone structure can certainly change smoothly from point to point. BUt it need not. A number of interesting physcailly possible worlds, and all examples given here, have a light cone structure which remains constant. A metric with this property is said to be flat.

We are now in the position to ask some interesting questions.

**Question.** Given any shape, is there a physically possible world with that shape? The answer is No.

First translate the question itno the formalism: Given any n-dimensional manifold M, can a Lorentzian metric g be put on M? Notice that a manifold admits a Lorentzian metric if and only if it admits a non-vanishing timelike vector field/ But an n-dimensional sphere does not admit a non-vanishing timelike vector field if n is even (this essentially follows from the famous hairy ball theorem of Brouwer) so the answer to our question is no. There is no physically possible world with an even number of dimensions shaped like a sphere.

## Orientability
---
Consider a physically possible world (M, g). The light cone which g assigns to any event in M has two lobes. And at any given event, we can certainly label one lobe as "future" and the other as "past". But can we do this for every event in M in a way that involves no discontinuities? If such a labeling is not possible, there could be no proper distinction between particles traveling "forward" and "backward" in time. If one the other hand, such a labeling is possible, then we could in a globally consistent way give time a direction. A natural question arises.

**Question.** Can time be given a direction in all physically possible worlds? Answer is no.

We know that any spacetime (M, g) must admit a timelike vector field on M. The question above amounts to whether any spacetime (M, g) must admit a continuous timelike vector field as well. Here's a counter-example: a physically possible world shaped like the Mobius strip with a flat metric. In such a world, global notions of past and future are not meaningful.

A spacetime which does admit a continuous timelike vector field is temporally orientable. Many other global conditions presuppose temporal orientablility so it's customary to consider only spacetimes with this property. In what follows, we adhere to the custom.

## Chronolgy
