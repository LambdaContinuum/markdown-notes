Let's review the simplest paradox of truth: the Liar paradox (*aka* "the Strengthened Liar (see footnote on chapter 1)). The paradox arises because of our ability to formulate sentences that assert their own untruth: more formally a sentence, 'Q', that is equivalent to $\neg \text{True}(\langle Q \rangle)$, where 'Q' is an abbreivation of the Liar sentence.

The relevant sense of equivalence is at least material equivalence: $$Q \leftrightarrow \neg \text{True}(\langle Q \rangle)$$
But the notion of truth seems governed by the Tarski schema (T): for arbitrary sentences A, $$\text{True(\langle A\rangle)} \leftrightarrow A$$
Instantiating (T) on Q, we have $$\text{True(\langle Q\rangle)} \leftrightarrow Q$$
which yields $$\text{True(\langle Q\rangle)} \leftrightarrow \neg \text{True}(\langle Q \rangle)$$
This is a contradiction in classical logic.  (as well as intuitionist logic, much of the following discussion could be extended to intuitionist logic).

There is four broad possibilities to block this paradox:
1. Give up the notion of truth, perhaps replacing it with related notions that don't obey the truth schema.
2. Keep the notion, but prevent the construction of Liar sentences.
3. Restrict the Tarski schema (T)
4. Restrict classical logic so whats yielded isn't a contradiction, or doesn't imply everything.

Most of the possibilities subdivide. In this part, we'll focus on (1)-(3), especially on (3) and its subdividisions. We'll discuss (1) last because discussion on (3) will have relevant.

It used to be often said that (2) is the best solution to the Liar Paradox, but it seems to Hartry quite hopeless. In the first place, although some sorts of self reference can be easily banned (like the artificial self-reference mentioned before), there are other forms that would be very difficult to keep from arising without seriously crippling the expressive capacity of the language: this includes both the "Contingent Self-Reference" and the "Godel-Tarski Self-Reference". Even if we were to come up with some artificial restrictions on the formation rules of a language that would prevent self-referential constructions, it would be of little general use in the theory of paradoxes. It might block the Liar Paradox, but it wouldn't block paradoxes that superficially seem quite analogous like the Heterologicality Paradox.

So let's turn to (3). If we keep classical logic, then it isn't enough to restrict which instances of schema (T) we accept. Some instances lead to contradiction, and classical logic then requires that we not only not accept them, but that we accept their negations.

It requires that we accept $$\neg[\text{True(\langle Q\rangle)} \leftrightarrow Q]$$
In classical logic it follows that: $$[\text{True(\langle Q\rangle)} \land \neg Q] \lor [\neg \text{True(\langle Q\rangle)} \land Q]$$
Prima facie we have three options:
1. Accept the first disjunct
2. Accept the second disjunct
3. Remain agnostic

If we consider possibilities about the claim $\text{True}(\langle \neg Q \rangle)$, from the above we can derive the following 4 possibilities using LEM and classical principles:
1. $\text{True}(\langle Q \rangle) \land \text{True}(\langle \neg Q \rangle) \land \neg Q$
2. $\text{True}(\langle Q \rangle) \land \neg \text{True}(\langle \neg Q \rangle) \land \neg Q$
3. $\neg \text{True}(\langle Q \rangle) \land \text{True}(\langle \neg Q \rangle) \land Q$
4. $\neg \text{True}(\langle Q \rangle) \land \neg \text{True}(\langle \neg Q \rangle) \land Q$

We have four options that don't involve agnosticism or anything akin to it. Of these four options, the second and third seem to offer few advantages. We seem to have two strong convictions about incoherence:

**First Incoherence Principle:** For any sentence A, it is incoherent to accept: A, but nonetheless $\langle A \rangle$ isn't true.

**Second Incoherence Principle:** For any sentence A, it is incoherent to accept: $\langle A \rangle$ is true, but nonetheless $\neg A$.

Option (1) on which Q is both true and false, clearly violates the second principle. Option (4), on which Q is neither true nor false, clearly violates the first principle. But (2) and (3) violate both principles!

Violating both seems gratuitous, and for this reason my discussion of the options involving nothing akin to agnosticsm shall focus on (1) and (4).

It remains to consider those options that involve agnosticism between the two disjuncts, or at least something akin to agnosticism. It seems agnosticism has little to offer for the following seems compelling:

**Third Incoherence Principle:** If one has gotten oneself into a commitment to a disjunction of several options, accepting any of which would be incoherent, one has already gotten oneself into an incoherent position.

Maybe one could reject this third principle? Perhaps there would be an advantage in this. This line could be made more appealing if we could argue that accepting the disjunction while refusing to accept either disjunct isn't a case of agnosticism as ordinarily understood, but rather, an appropriate response to a kind of indeterminacy as to which disjunct is correct. The position would be analogous to a certain sort of supervaluationist view about borderline cases of vague terms. The supervaluationist view in mind is:
1. that we should accept classical logic for vague terms, so that Joe is either bald or not bald even if he is a borderline case;
2. than in such a borderline case, we can't know whether Joe is bald, but that this is not ignorance of any straightforward sort, because the question is baldness is somehow "indeterminate". There is no determine fact of the matter for us to be ignorant about.

Supervaluationism in this sense needn't identify truth with "super-truth"; that is, it needn't involve the view that "indeterminate" implies "neither true nor false", and the version hartry has in mind will specifically reject that implication. It will still imply neither determinately true nor determinately false.

It is not evident that supervaluationism succeeds in providing an alternative to the ignorance view. This will be discussed later.
