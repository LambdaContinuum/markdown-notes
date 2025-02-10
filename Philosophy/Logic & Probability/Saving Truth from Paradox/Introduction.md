# 1. Grelling's Paradox
---
The predicate 'red' is true of all and only the red things; and the predicate 'has mass greater than 10 kilograms' is true of all and only things that have mass greater than 10 kilograms.

Generally, for any predicate of our language that one substitutes for the letter 'F' the following holds:

- (TO) 'F' is true of all and only the things that are F.

Consider the predicate 'is not true of itself', TO yields:

'Is not true of itself' is true of 'is not true of itself' if and only if 'is not true of itself' is not true of itself

which is to say,

'Is not true of itself' is true of itself if and only if it is not true of itself.

This has the form

B if and only if not-B

which is a contradiction.

This is often called Grelling's paradox, or the heterologicality paradox.

# Russell's Paradox for Properties
---
Grelling's paradox concerns linguistic expressions, but underlying it is a more basic paradox concerning properties. The property of being red is instantiated by all and only the red things. More generally, for any intelligible predicate of our language that one substitutes for the letter 'F', the following would seem to hold:

- (INST) The property of being F is instantiated by all and only the things that are F.

Consider the 'Russell property', the property of not instantiating itself. (INST) yields

The Russell property is instantiated by all and only those things that don't instantiate themselves.

Particularly,

The Russell property instantiates itself if and only if it doesn't instantiate itself.

This has the classically contradictory form

B if and only if not B.

# Russell's Paradox for Sets
---
When writes speak of Russell's paradox they don't usually mean the paradox above, but a paradox involving the mathematical notion of set. The paradox is analogous, with 'is a member of' instead of 'instantiates': it seems that there is a set whose members are precisely those things that are not members of themselves; but then in analogy with the above we argue that this set is a member of itself if and only if it isn't, which is classically contradictory.

Russell's paradox for sets has a standard solution: there simply is no such set. This is not an *ad hoc*  solution, there is a natural picture of sets according to which it is inevitable. On this picture, the sets form a hierarchy, the rank hierarchy. Putting aside the empty set for simplicity, we have at the bottom layer the "rank 1" sets, whose members aren't sets but things. At the next layer we have "rank 2" sets, all of whose members are either non-sets or sets of rank 1, with at least one of the latter (This condition ensures that no rank 2 set is also rank 1).  In general, the sets of each layer have members only of preceding layers.. This ensures:
1. that no set can be a member of itself. This in turn ensures
2. that there can be no universal set, i.e. no set of which everything is a member; for then it would have to be a member o itself, which we've just seen is ruled out.
3. There can be no Russell set, i.e., no set of all things that are not members of themselves, for by (1) it would have to be a universal set, but by (2) there is no universal set.

This solution to Russell's paradox is motivated by the hierarchial picture of sets. This picture is not only natural, but mathematically fruitful. It provides the framework for virtually all of contemporary mathematics. 

Godel is reported to have remarked "There never were any set-theoretic paradoxes, but the *property-theoretic* paradoxes are still unresolved." The idea behind the first part of his remark is presumably that the notion of set was hierarchical from the start, so it should have been obvious all along there was no Russell set (Cantors work seems to provide reason to think the hierarchial picture was underlying set theory from the beginning). The idea behind the second part is that the obvious resolution of Russell's paradox for sets simply doesn't carry over to the paradox for properties.

This seems correct, at least for the notion of property that Godel had in mind. This qualification is made because the term property is used in more then on way.
1. *Natural properties*, on this use what properties there are is something discovered in part by science: e.g. science tells us there is no such property as being de-phlogisticated, but there are properties like spin and charm.
2. Godel had in mind properties as *concepts*. This term is ambiguous, it is often used for mental entities, whereas what is intended here is an objective correlate of mental entities.

Hartry uses the term *conceptual property*. The whole point of the notion of conceptual property is that there is a conceptual property corresponding to every intelligible predicate. 'Indentical' is intelligible, so there is a 2-place conceptual property of *being identical to*. (That is, a conceptual *relation*).  From this we can form a one-place conceptual property of *being identical to itself*: this is a universal property so the hierarchical picture simply can't apply to conceptual properties.

Similarly, 'instantiates' is intelligible, so there is a conceptual relation of instantiation, and a conceptual property of instantiating itself and a conceptual property of not instantiating itself, which is the Russell property. If this is right, the standard solution to Russell's paradox for sets doesn't carry over to the paradox of conceptual properties. (Standard solution refers to the solution embodied in set theories such as Zermelo-Fraenkel, Russell's solution was the theory of types, in which there is no single membership predicate, but a hierarchy of different ones. One might offer a resolution to the property-theoretic analog according to which there is no single instantiation predicate, but a hierarchy of different ones. These theories will be considered but we'll say for now that they've been almost universally abandoned for sets and unattractive for properties for the same reasons and more)

One possible response is that we should, with Quine, declare there to be no such things as conceptual properties. This is not much help in the present context since the apparently analogous heterologicality paradox, which involves only linguistic expressions would still remain. Another possible reaction is that our common-sense conception of conceptual properties should be replaced with a hierarchical conception; thought that would be a very radical alteration of the common-sense conception.

I'm skipping a bunch of parts here, it's mostly an introduction meant to signify the approach being taken

# Change of Logic and Change of Meaning
---
There are many paradoxes related to the ones discussed here. The most well-known is the Liar paradox. It will be the starting point, but there are many others: the troublesome Curry Paradox, and the even more troublesome iterated Curry paradoxes. There are paradoxes of denotation and definability. It's important we don't just deal with each paradox piecemeal, but provide a systematic account that can be shown to handle them all. We'll survey a wide range of options for such an account.

A theme of this book will be that we ought to seriously consider restricting classical logic to deal with all these paradoxes. In particular, we should seriously consider restricting the law of excluded middle (not in the way intuitionists propose). Hartry says restrict instead of abandon because there is a wide range of circumstances in which classical logic works fine.

He takes excluded middle to be clearly suspect only for certain sentences that have a kind of "inherent circularity" because they contain predicates like 'true'; and most sentences with those predicates can be argued to satisfy excluded middle too.

The idea isn't that we need two distinct logics, classical logic and a paracomplete logic without excluded middle. The idea is that we can take the paracomplete logic to be our single all-purpose logic. But we can recognize the truth of all instances of excluded middle in certain domains (e.g. those that don't contain 'true', 'true of', 'instantiates', or other suspect terms). We may not count these instances of excluded middle as *logical truths* (though you can if you like, this is a matter of verbal stipulation), but we can recognize them as truths, and truths with something of the high degree of certitude that many logical truths have. So we can reason with them and reasoning from them will look just like classical reasoning in the domains in question.

Weakening classical logic is not something to be done lightly. There are obvious advantages to keeping classical logic even for "circular" predicates: advantages of simplicity, familiarity, and so on. Choosing to forgo these advantages has its costs. But Hartry will argue that the disadvantages of keeping classical logic for "circular predicates" are also very great, so that the undoubted cost of weakening the logic is worth bearing.

Perhaps there are some who think this cost-benefit analysis is inappropriate, that the very idea of tinkering with classical logic is irrational on its face since classical logic is obviously superior. Let's call the view 'Logical Dogmatism'.

One possible defense of such Dogmatism is that if logic is not held fixed then anything goes. As an anonymous referee put it to me, ‘‘We didn’t weaken the logic as a way of hiding the defects in Ptolemaic astronomy or old quantum theory; why should we modify the logic to hide the blemishes in the naive theory of truth?’’

Hartry answers, there is no known way and little prospect of finding a way to save either Ptolemaic astronomy or the old quantum theory by change of logic, and little benefit to so doing since we have far most satisfactory alternatives. The proposal that we save the naive theory of truth by a change of logic is not the cheap non-solution that the objection envisages: it is something that must be earned by working out the details of the logic and of the theory based on it. Once we've worked out such a theory, we must weight it against competing theories that keep classical logic but restrict the naive principles of truth, using the usual criteria for theory choice. With Ptolemaic astronomy or the old quantum theory there is no serious prospect for such a theory being worked out that survives such a competition.

A second defense is based on the idea that change of logic requires change of meaning. To this Hartry says
1. The paradoxes force a change in the basic laws either of logic in a narrow sense or of the logic of truth, instantiation, etc.; or if you like, it forces a change in opinion about those laws. If change of (opinion about) the basic laws of logical connectives counts as change of meaning, why doesn't change of (opinion about) the basic laws of truth and the basic laws of instantiation. Adhering to the principles of classical logic requires a huge change in standard principles about truth and instantiation. The upshot of this is that there is at least a good case that the classical truth theorist is "changing the meaning of 'true" as that the defender of the Intersubstitutivity principle who restricts excluded middle is "changing the meaning of 'not".
2. Why make a fetish about whether these things involve a change of meaning? As Putnam taught us, there is a distinction to be made between change of meaning and *mere* change of meaning. The switch from Euclidean geometry to generalized (variable curvature) Riemannian geometry involved revision of enough basic principles about straight lines that it may be somewhat natural to say that 'straight line' took on a different meaning. But if so,  an abandonment of the old meaning and the invention of a new one was required to get a decent physical theory that is observationally adequate: for no reasonably simple observationally adequate theory allows for the existence of "straight lines in the Euclidean sense". We need not have carried over the old term 'straight line' from Euclidean geometry to Riemannian, but there is enough continuity of doctrine to make it natural to do so. This is certainly not a mere change of meaning, i.e. a relabelling of terms without alteration of basic theory. The situation with truth is similar: here the "old theory", involving both classical logic and the naive theory of truth, is simply inconsistent. Indeed it's trivial: it implies everything. If you don't want to be committed to the view that the Earth is flat you need a theory that differs from the naive theory in basic principles, either principles about truth or principles about logical matters more narrowly conceived. If giving up those basic principles involves a change of meaning, so be it: for then old meanings are really coherent and they need changing. 

Any resolution of the paradoxes will involve giving up or restricting some firmly held principles: either principles of a narrowly logical sort or principles central to the ordinary use of truth and instantiation predicates, or both. The principles to be given up are ones to which the average person simply can't conceive of alternatives. That's why the paradoxes are *paradoxes*.

# Some Connections to Other Issues
---
Resolution to the paradoxes has bearing on many other topics. It's crucial for our investigation into the nature of truth that we have a consistent theory of truth, and likewise for properties. What this consistent theory looks like will affect our answers to general philosophical issues about truth and properties.

For example, there's been discussion about the purpose the notion of truth serves. One common answer (particularly among deflationists or minimalists) is that 'true' is primarily a logical device that enables us to make generalizations we would otherwise be unable to make or enable to make succinctly.