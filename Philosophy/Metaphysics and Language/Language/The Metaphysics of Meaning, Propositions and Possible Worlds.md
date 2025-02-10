# Loci of Controversy
---
No notions are more central to meaning and philosophy of language than *proposition* and *possible world*. They are sources of controversy.

Propositions are bearers of truth, semantic contents of sentences, and that which we assert, believe and know. Possible worlds are parameters to which truth is relativized, *ways the world could've been*.

The controversy about propositions and possible worlds concerns whether they exist at all, what sorts of things they are if they do exist, and if they're explanatorily fundamental. 

For some, e.g. Davidson, theories of language don't require either one and their existence is doubtful. For others, e.g., Lewis and Stalnaker, possible worlds are fundamental, and propositions are sets of worlds. For others, e.g., Robert Adams, propositions are fundamental, and possible worlds are sets of propositions.

# Propositions
---
## Why We Need Them and Why Theories of Truth Conditions Can't Provide Them
Propositions are needed in semantics
1. As referents of names like 'Church's Thesis' and 'Logicism,' and of demonstratives in examples like 'That's true,'
2. As entities quantified over in sentences like 'At least six of those theses are unsupported by evidence,'
3. As objects of attitudes in 'Alex believes the proposition that all mean are created equal'.

Propositions are also needed to state the goals of semantic theory. Since propositions are what is asserted and believed, and since semantic content is a prime determinant of those assertions and beliefs, propositions are presupposed by our best account of what semantic theories do.

We know Davidsonian truth theories, which shun propositions, [[Truth, Interpretation, and Meaning#The Semantic Approach of Donald Davidson|do not provide enough information to qualify as theories of meaning]].

There is no hope of using such truth theories as theories of meaning, or of extracting propositions from them. The leads us back to Frege and the early Russell, who recognized propositions as explanatorily primary.


## Why Traditional Propositions Won't Do
According to Frege and Russell, propositions are meanings of sentences, bearers of truth, and objects of the attitudes. Despite this, both believed there to by a mystery at the heart of propositions, which they took to be a complex constructed from the meanings of the constituents of a sentence expressing it.

Propositions aren't mere collections of unrelated expressions, but rather have a structural unity that distinguishes them from a mere list, so propositions aren't mere collections of the meanings of expressions, but rather have a unity that distinguishes them from arbitrary aggregates of their parts. Frege and Russell found this unity mysterious.

From example, certainly there is more to the proposition *that A differs from B* than the fact that its constituents are A, B, and difference. There is also the manner in which the constituents occur. Presumably, this has to do with the fact that the proposition *predicates* difference of A and B, and so *represents A as being different from B*. Since a list doesn't predicate anything of anything else, it isn't representational.

Is this problematic? Consider sentence 1 in which 'difference' and 'identity' are abstract nouns, 'different' is an adjective that combines with the copula to form a predicate, and 'from difference' is a prepositional phrase modifying the predicate.
1. (s (n Difference) (vp (v is different) (pp (p from) (np identity))))

The constituents of the proposition expressed by 1 are the relations identity and difference, the latter occurring twice. Understanding 1 involves understanding its word, which provide the proposition's constituent, plus the hierarchial structure in which the words are arranged, which indicates what is predicated of what.

Just as one who understands the sentence recognizes one expression as predicate and others as arguments, so, it might be argued, one who entertains the proposition recognizes from its structural configuration which of its constituents is predicated of which.

On this view what distinguishes a proposition from a mere aggregate of constituents parallels what distinguishes a sentence from a mere list. The structural relations that constituents bear to one another carry the information about predication needed for representational content.

Problems arise when one asks how exactly does the arrangement of the constituents of the proposition expressed by (1) show that difference is predicated of difference and identity?

One could provide structures that serve as a formal model of the proposition (see the book for examples) expressed by 1 but none could be the proposition. The proposition *represents* difference as being different from identity, because it *predicates* difference of difference and identity. But there is nothing is any formal structure we might specify that, by its very nature, indicates that anything is predicated of anything, such structures are neither intrinsically representational nor capable of being true or false.

We could adopt rules that allow us to read off information about predication from the structures and so *interpret* them. This would not make them propositions in the traditional sense, since propositions are not things we *give meanings*. They *are* the meanings we assign to sentences, when we interpret them.

The problem with Russell's discussion is his assumption that propositions are intrinsically representational, independent of us, and also that from which the representational features of our cognitive states and sentences are inherited.

Since this assumption makes it impossible to answer the question "*What makes propositions representational?*", there are no Russellian propositions.

The same conclusion holds for Fregean propositions, which are assumed to be representational independent of us. Frege differs from Russell in postulating "unsaturated" senses that are intrinsically predicative, and so always occur in a predicative role. This leads him to conclude that neither the sense nor referent of any predicative expression can be designated by a non-predicative expression, and thereby, made the subject of a further predication.

This thesis, that if Pred is a predicate, then *the sense of Pred* is unsaturated, *the referent of Pred* is incomplete, and neither can be designated by any non-predicative expression, is self-defeating.

## Towards a Naturalistic Theory of Propositions
Since we need propositions in our linguistic and cognitive theories, the failure of traditional conceptions calls for a new conception that reverses explanatory priorities.

Propositions are not the source of representationality is mind and language. Sentences, utterances, and cognitive states are not representational because of their relations to inherently representational propositions.

Instead propositions are representational because of their relations to inherently representational cognitive states.

Representations in mind and language result form the cognitive acts agents perform. One who sees an object o *as red* predicates redness of it. Since one's perceptual experience represents o as *being red*, one bears a propositional attitude to the proposition *that o is red*. Attitudes like this are often not linguistically mediated.

The same is true of much, but not all, of our thought. Language learning changes our cognitive calculus by expanding cognitive reach. In making objects and properties with which we have had no prior acquaintance cognitively available to us, as well as providing the means of predicating one of the other, language vastly increases our stock of beliefs and other attitudes.

As a result, we come to bear attitudes to many propositions to which our only cognitive access is mediated by sentences that express them. Because of this language is not merely a means of encoding and communicating prior independent thought, but also a fertile source of new thought. 

There are two ways of fleshing out a theory of proposition along these lines.

On the *deflationary account*, propositions are theorists' constructs used to track predications, and other events, that make up our cognitive lives. On the *cognitive-realist account*, they are the very event-types instances of which deflationary propositions are used to track.

### The Deflationary Approach
Deflationary propositions are structured complexes constructed out of, or encoding, the semantic contents of the constituents of sentences that express them.

Whatever the right syntax for a language turns out to be, all semantically significant aspects of syntactic structures must be encoded by the deflationary propositions its sentences express.

If there is one system of semantic structures meeting this condition, there will be many. For any unambiguous sentence S, each such system identifies a unique structure as *the proposition S expresses*.

To entertain a simple proposition is to predicate something of something else. When we see an object o *as red*, we predicate redness of it, and so entertain the proposition *that o is red*.

The proposition entertained in these ways may be identified with the following:
2. (prop (arg o) (pred Redness))

```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd}
                       & Prop \arrow[rd, no head] \arrow[ld, no head] &                         \\
arg \arrow[d, no head] &                                              & Pred \arrow[d, no head] \\
o                      &                                              & redness                
\end{tikzcd}
\end{document}
```

Structures like these are the theorist's creations. The theorist *stipulates* that to entertain the above is to predicate redness of o, thereby assigning a new technical meaning to the verb 'entertain' that explains what is meant by the theoretical claim that an agent entertains this structure.

Next the theorist advances 3, which relates that claim to the ordinary claim on the left.
3. An agent entertains the proposition that o is red iff the agent entertains 2

The strategy generalizes for every propositional attitude.

To *judge* that o is red is to predicate redness of o, while endorsing that predication. To *believe* that o is red is to be disposed to judge that o is red. To *know* that o is red is to believe that o is red while being justified so doing in a case in which o is red. To *assert* that o is red is to make a conversational commitment, by assertively uttering something, to treat the proposition *that o is red* as something one knows.

Given these characterizations, the theorist adds 4, 5, and 6 to 3, thereby generating empirical predictions relating the theoretical claims on the right to ordinary attiude ascriptions on the left.

4. An agent believes the proposition that o is red iff the agent believes 2
5. An agent knows that o is red iff the agent knows 2
6. An agent asserts that o is red iff the agent asserts 2

More complex propositions are treated similarly. For example, to entertain the proposition *that it is not the case that o is red*, represented by 7, is
1. to predicate redness of o and thereby to entertain 2
2. and to predicate not being true of 2 by saying to oneself, "That is not true", referring to the result of one's initial predication.

7. (prop (pred NEG) (arg (prop (arg o) (pred redness))))
```tikz
\usepackage{tikz-cd} 
\begin{document}
\begin{tikzcd}
                          & Prop_1 \arrow[ld, no head] \arrow[rd, no head] &                                                &                           \\
Pred_1 \arrow[d, no head] &                                                & Arg_1 \arrow[d, no head]                       &                           \\
NEG                       &                                                & Prop_2 \arrow[ld, no head] \arrow[rd, no head] &                           \\
                          & Arg_2 \arrow[d, no head]                       &                                                & Pred_2 \arrow[d, no head] \\
                          & o                                              &                                                & Redness                  
\end{tikzcd}
\end{document}
```

This approach depends on
1. the inclusion of information about what is predicated of what in abstract structures playing the role of propositions
2. the deflationary conception of what it is to bear cognitive attitudes to these structures
3. their status as representational bearers of truth conditions in virtue of what is required to entertain them.

What makes 4 represent o as red is that predicating its Pred-constituent of its Arg-constituent is necessary and sufficient for entertaining it.

It's in virtue of this we speak of 4 as predicating redness of o.

On this approach the function of propositions in our theories is to identify and track the cognitive states of agents. In physical theory we use numbers and other abstract objects to specify the relations that physical magnitudes bear to one another. In semantic and cognitive theory we use abstract propositional structures to talk about the relations that representational cognitive states bear to one another, and to the world.

### The Cognitive-Realist Approach
Since propositions are needed to track cognitive acts, why not take them to be *event-types*, instances of which involve those very acts?

The proposition *that o is red* is identified not with the tree structure previously given, but with the event-type in which an agent *predicates redness of o*.

Thus it's intrinsically connected to the cognitive acts it is need to track. It's also something to which all agents who entertain it bear the same, natural, relation. Finally, this analysis gives us an account of what propositions *really are*, rather than merely choosing abstract structures, about which there is bound to be some arbitrariness, to play the role of propositions.

Consider a spoken utterance of 'Snow is white,' thought of as both an event that occurs at a particular time and place, and a token of the sentence uttered. So construed, sentences are event-types that can have multiple occurrences, which are their tokens.

Next imagine an utterance of the sentence followed by an utterance of "That's true." In such a case, the demonstrative may refer either to the utterance, or to the sentence uttered, illustrating that some event-types can be bearers of truth value.

Finally, there are events in which one doesn't utter anything, but simply thinks of snow as white, thereby predicating whiteness of it.

These cognitions are events that occur at particular times and places, which are instances of the corresponding event-type in which an agent predicates whiteness of snow.

Just as the sentence ‘Snow is white’ can be identified with the event-type of which utterances of it are instances, so the proposition that snow is white can be identified with the event-type of which particular cases of predicating whiteness of snow are instances. Thus, both event-types have truth conditions.

Since the proposition *that o is red* is the event-type in which one predicates redness of o, and since every attitude one bears to this proposition involves this predication, any agent acquainted with his own cognitive processes will be acquainted with the proposition *that o is red*, by virtue of being acquainted with events in his cognitive life that are instances of it.

Like the deflationary account, this approach provides entities needed as contents of sentences, bearers of truth, and objects of the attitudes. But while the deflationary account sees nothing beyond the unavoidably arbitrary formal structures that play the role of propositions in our theories, the realist account views such structures as merely useful devices that *represent* the real propositions to which agents bear natural cognitive relations.

The labeled trees encode the structure and sequence of cognitive acts that are necessary and sufficient for entertaining the real propositions these structures represent, where entertaining a proposition is performing the acts involved in tokening the event-type that it is.

There are many propositions that have never been entertained i.e., many cognitive event-types that haven't been tokened. But this is no more problematic than there being many sentences that have never been uttered. For a proposition to represent the world as being a certain way is for any *possible* predication that tokens it to do so.

Unlike the Platonic epistemology traditionally required, the cognitive-realist account takes knowledge of propositions to be knowledge of events that make up one's cognitive life. It also avoids the pseudo-problem of "the unity of the proposition". By locating the representational character of propositions in their intrinsic connection to inherently representational cognitive events, the cognitive-realist account offers a solution.