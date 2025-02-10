## Basic Notions of Theory Development
---
The three different kinds of theory development are:
- expansion
- contraction
- revision by empirical evidence.

These and other distinctions require *formal tools* for their reconstruction. We assume the logical framework of a 1st order language with the standard logical symbols and $x_i$ $(i = 1, 2, ...)$ for individual, variables $a_i$ for individual constants, $P_i, R_i, ...$  for $n$-ary predicates.

$\mathcal{L}$ is our language and $S(\mathcal{L})$ the set of $\mathcal{L}$-sentences. Small letters $s_i \in S(\mathcal{L})$ denote arbitrary sentences, $h_i$ hypotheses, $e_i$ evidence statements, $T_i$ stands for theories which are sets of sentences, $E_i$ for sets of evidence statements, and $S_i$ for arbitrary sets of statements. $\Vdash$ denotes logical inference and $Cn$ logical consequence, i.e. $Cn(S) := \{s_i \in S(\mathcal{L}): S \Vdash s_i\}$.

In this framework, a theory $T_i$ is reconstructed as a consistent and logically closed set of sentences of a given set of a characteristic axioms $A_i$ of $T_i$. i.e. $T_i = (Cn(A_i))$. $A_i$ is also called the (axiomatic) *base* of $T_i$.

Within this formal background the ordinary *expansion* of a theory $T$ by a new and $T$-compatible piece of information $s$ is denoted as $T + s$ and defined as $T + s := Cn(T \cup \{s\})$. If $T = Cn(A)$, an equivalent definition is $T + s := Cn(A \cup \{s\})$.

If $s$ contradicts $T$, (which is to way $T \Vdash \neg s$), then one must first contract $T$ by $\neg s$ before one can expand $T$ by $s$. The so-called *contraction* of $T$ by $s$ is denoted as $T \div s$ and intended to be some preferred $T$-subset which no longer entails $s$. Different methods of defining contraction operations have been suggested (e.g. via intersections of maxchoice contractions, or via epistemic ordering or ranking functions over sentences or over corresponding possible worlds).

Finally, the ordinary *revision* of $T$ by a $T$-incompatible proposition $s$ is denoted as $T*s$ and defined via the Levi-identity as $T*s := (T \div \neg s) + s$. In other words, one revises $T$ by a new piece of information $s$ by first contracting $T$ by $\neg s$ and then expanding this contraction by $s$. 

The information by which scientific theories are typically expanded or revised are so called *evidences*, i.e. observations of measurement results; they are expressed by so-called *basic statements*. These are unnegated or negated atomic sentences of an assumed *empirical* (or non-theoretical) *sublanguage* $\mathcal{L}_e$ of $\mathcal{L}$ whose concepts are directly observable or measurable (i.e. $S(\mathcal{L}_e) \subseteq S(\mathcal{L})$).

Important for philosophy of science is the distinction between *AGM-contraction* and *base-contraction*. In AGM-contraction the contraction-operation is applied to the entire set of $T$'s consequences, whether basic or derived, in base-contraction this operation is only applied to $T$'s axioms $A$, i.e. $T \div s := Cn(A \div s)$. 

The difference is this: If an axiom $s \in A$ of a theory $T = Cn(A)$ is removed, then in base-contraction $T$-consequences whose justification support depends on axiom $s$ have been removed from $T$ too. In AGM-contraction this need not be so: one may retain consequences from $T$ even after their premises have been removed.

While base-revision is reasonable from a *foundation-oriented* viewpoint, AGM-revision makes sense if one adopts a *coherentistic* position. Beyond these ordinary notions of expansion and revision, there are stronger notions of *abductive* expansion and revision introduced later.

## Theory Development Under Empiricist Assumptions
---
The empiricist view of scientific theories has been defended by classical empiricists and early logical empiricists. This view makes two assumptions:
1. That evidences are certain
2. That all non-logical concepts of scientific theories can be defined by empirical concepts, or in other words, the scientific language contains no genuinely theoretical concepts, i.e, $\mathcal{L} = \mathcal{L}_e$

Let $E(\mathcal{L}_e)$ stand for the set of all basic (i.e. evidence) statements of $\mathcal{L}_e$. Each maximally consistent subset of $E(\mathcal{L}_e)$ is denoted by $EW_k$ and represents a possible empirical world or "$\mathcal{L}_e$-world" over a given countably infinite domain of named individuals.

We formalize the history of scientific evidences *over* a given $\mathcal{L}_e$-world $EW$ in the form of an *evidence stream* $(e) = (e_0, e_1, ...)$ such that $EW = \{e_i : i \in \omega\}$ and the $e_i$ are pairwise distinct. Given the empiricist assumptions, $EW$ determines the *complete true* theory $T(EW)$, which is semantically given as the set of all true $\mathcal{L}_e$-statements in $EW$ and syntactically as the uniquely determined maximally consistent and $\omega$-complete extension of $EW$ in $\mathcal{L}_e$. Given this formal construction, empiricist theory-development has the following properties:
1. The accumulation of evidence is *cumulative* because evidences are true and are never taken back. Formally, this means that $e_i$ are mutually compatible.
2. At every finite time point $n$, only a finite subset of $EW$ is known. Therefore, $T(EW)$ is never known with certainty. Popper has stressed, no purely *universal hypotheses* $\forall x Px$ is verifiable by finitely many evidences, although it is falsifiable ($\neg Pa$) and dually, no purely *existential hypothesis* $\exists x Px$ is falsifiable by finitely many evidences, although it is verifiable $Pa$. Later, it was discovered that quantificationally mixed hypothesis such as $\forall x \exists x Rxy$ are neither verifiable nor falsifiable by finitely many evidences. It follows that even under empiricist assumptions it need not be that theory development is cumulative at the level of hypotheses: false universal theories may be held for an arbitrarily long time before they get falsified; and theories with mixed quantifiers will never get verified or falsified.

## Convergence in the Limit and Formal Learning Theory
---
The empiricist setting is the major framework of formal learning theory. Evidence streams are called *data streams*. 

Of course there exists theories with theoretical terms to which the empiricist setting doesn't apply, but we may regard the setting as a legitimate idealization in all contexts in which one may assume an unproblematic background knowledge (e.g. concerning measurement techniques) by which one can determine the truth value of all basic statements of the language in which theories are formulated. Let's understand $\mathcal{L}_e$ in this extended sense.

Verification and falsification *with certainty* (in the sense of Carnap and Popper) are defined as follows:
1. $h \in S(\mathcal{L}_e)$ is *verifiable* (or falsifiable, respectively) *with certainty* over an $\mathcal{L}_e$-world $EW$ iff for every evidence stream ($e$) over $EW$ there exists a time point $n$ at which $e_n$ entails $h$ (or entails $\neg h$ resp.)

Purely existential hypotheses are verifiable and purely universal hypotheses are falsifiable with certainty; but quantificationally mixed hypotheses are neither nor. In view of this negative results formal learning theorists suggest to use the *weaker* epistemic standard of verifiability in the limit. Let $SQ(\mathcal{L}_e)$ be the set of all evidence sequences over $\mathcal{L}_e$-worlds; let $(e_{1-n})$ denote the sequence of the first $n$ elements of $(e)$; and let $E_n := \{e_i:1 \leq i \leq n\}$ be the corresponding evidence set at time $n$. An assessment function for the hypotheses $h \in H$ in a given set of hypotheses $H$ is a function $\alpha : H \times \{(e_{1-n}):(e)\in SQ(\mathcal{L}_e), n \in \omega\} \to \{\text{true, false}\}$ which conjectures at every time point $n$ of any evidence stream $(e)$ whether $h$ is true or false. Then:
2. A hypothesis $h \in S(\mathcal{L}_e)$ is verifiable (or falsifiable, resp.)  *in the limit* iff there is an assessment function such that for every $\mathcal{L}_e$-word $EW$ which verifies (or falsifies, resp.) $h$ and evidence stream $(e)$ over $EW$ there exists a time point $n$ after which $\alpha$ conjectures the correct truth value of $h$ in $EW$ forever (i.e. $\alpha(h, (e_{1-m})) = \text{true}$ for all $m \geq n$)

One of the major results of formal learning theory is:
3. An $\exists$-$\forall$-hypothesis (e.g. $\exists x \forall y Rxy$) is verifiable but not falsifiable in the limit. Dually a $\forall$-$\exists$ -hypothesis (e.g. $\forall x \exists y Rxy$) is not verifiable but falsifiable in the limit.

In particular, a $\forall$-hypothesis is verifiable in the limit but falsifiable with certainity (and dually for $\exists$-hypothesies). The basic idea underlying result (3) is the following.

Define Dom($E_n$) to be the subdomain of those individuals which appear in $E_n$. Then an assessment method $\alpha$ for $\exists x \forall y Rxy$ can be defined as follows: conjecture "true" as long as the so far observed evidence set $E_n$ does not falsify $\exists x \forall y Rxy$ over Dom($E_n$); otherwise conjecture "false".  Then if $h$ is true in $EW$ there exists an individual $a_k$ which appears at some time $t(a_k)$ and for which $\forall y Ra_ky$ is true,  when after time $t(a_k)$ $\alpha$ will conjecture "true" forever. However, if $\exists x\forall yRxy$ is false in a given $EW$, then for every assessment method $\alpha$ one may construct a "demonic" evidence stream over $EW$ such that $\alpha$'s conjectures don't stabilize but switch endlessly between "true" and "false".

Although the method $\alpha$ for $\exists x \forall y Rxy$ is guaranteed to stabilize to the conjecture "true" after *some finite* time, one can never know *when* this time is reached, and hence, one can never know whether one has achieved the truth or not. Even if this intrinsic weakness of "verification in the limit" is accepted, the other bad news it that already hypotheses with three alternating quantifiers are neither verifiable nor falsifiable in the limit. Kelly shows that these hypotheses are at least *gradually* verifiable or falsifiable in the limit which is a still weaker property. However, for hypotheses with four alternating quantifiers even gradual verification or falsification fails.

Most contemporary philosophers of science would argue that even evidence statements may fail: perceptions may be erroneous and measurement devices may be malfunctioning.  If we drop the infallibility assumption for evidences, then evidence statements in ($e$) may mutually contradict each other. It follows that evidence streams are no longer cumulative: $E_n \subseteq E_{n+1}$ does not always hold and we cannot define $E_n = \{e_i:1\leq i \leq n\}$. We have to construct the evidence history ($E$) as a sequence of evidence sets $(E)= (E_0, E_1, E_2, ...)$ that is defined by revision or expansion operations: $E_{n + 1} = E_n * e_{n+1}$. The axiom of success, $e_n \in E_n$, is no longer mandatory for revisions over contradicting evidence statements. To retain the positive results concerning verifiability and falsifiability it is necessary to set up the following constraint of stable error-correction: every false evidence in ($e$) is corrected once-and-forever after some time. This implies that for every true evidence $e$ in $EW$ (the given empirical world) there exists a time n such that for all $m \geq n, e \in E_m$.

## Inductive Confirmation and Convergence with Probability
---
The major conclusion previously was that even under empiricist idealizations and in regard to the weak "in the limit" notions of verification and falsification, the range of those hypotheses which are verifiable or falsifiable is very restricted. 

As soon as one assumes *inductive confirmation* as legitimate justification principle, things get better. A simple qualitative definition may run as follows:
4. A hypothesis $h$ is inductively *confirmed* by a finite evidence set $E_n$ iff $h$ is not falsified by $E_n$ over the subdomain Dom($E_n$), and this the confirmation is stronger, the greater the part of Dom($E_n$) which verifies $h$ over Dom($E_n$)

However, since David Hume it is known that induction is not generally reliable inference: it may fail in worlds (or event sequences) which are *non-uniform*, i.e. in which the future differs radically form the past. What one can only show is that (under mild conditions) induction is an *optimal strategy*.

Often confirmation principles are formalized in the framework of [[A User's Guide to Bayes Theorem|Bayesian]] probabilities, i.e. rational degrees of beliefs. If $P:S(\mathcal{L}_e) \to [0, 1]$ is a Bayesian probability function over the total set of statements, then the posterior probability of a hypothesis $h_k$ given evidence $e$ is given by the famous Bayes-formula as
5. $P(h_k \mid e) = P(e \mid h_k) \times P(h)/\sum_{1 \leq i \leq n} P(e \mid h_i) \times P(h_i)$.

where $\{h_1, ..., h_n\}$ is a pragmatically given partition of possible hypothesis that contains $P_k$. 

Since most  contemporary Bayesians agree that prior probabilities are subjective, the dependency of posterior probabilities on priors seems to constitute a counterargument to Bayesian confirmation theory. Bayesians counter that the dependency of the posterior probabilities of hypotheses on the priors becomes smaller and smaller the more evidences come in. Bayesians cite here *convergence* theorems, for example the following general convergence theorem:
6. Under the assumption that $P$ is *countably additive* it holds for every possible $\mathcal{L}_e$-hypothesis $h$ and evidence stream over a world $EW$ with probability $1$ that $h$'s posterior $P(h \mid E_n)$ converges to the truth value of $h$ in $EW$ for $n \to \infty$.

Probabilistic convergence theorems of this sort are restricted in three ways:
1. They hold only under the empiricist assumption that $\mathcal{L} = \mathcal{L}_e$.
2. They hold only with the probability 1, whence convergence may fail in an uncountably infinite subset of the uncountably many $\mathcal{L}_e$-worlds
3. They hold only under the condition of countable additivity, which involves inductive assumptions. Stronger convergence properties require stronger inductive assumptions.

## The Rational Choice and the Construction Paradigm of Theory Discovery: Learning Sentences and Abductive Theory Revision
---
We've studies the development of *scientific assessments* of hypotheses in the face of an evidence stream, but not the *discovery* of hypotheses. For Popperians theory discovery is a matter of psychology, not of logic, there are no rules for theory discovery.

Formal learning theory, provides rules for theory discovery. These rules assume that there exists a countably enumerable set $H$ of possible hypotheses in $\mathcal{L}_e$ which contains at least one true hypothesis, and an infinitely repetitive ordering $(h) = (h_0, h_1, ...)$ of the hypotheses in $H$, i.e. every hypothesis occurs in $(h)$ infinitely many often.

With such an enumeration at hand, an assessment method $\alpha(h_i, (e_{1-n}))$ can be transformed into a discovery method $\gamma$ that assigns to each initial subsequence $(e_{1-n})(n \in \omega)$ a hypothesis in $H$. Recursively defined as follows::
7. $\gamma((e_0)) = h_0$, and for each time $n$, if $\alpha(\gamma((e_{1-n}), (e_{1-n}))) = \text{"true"}$, then $\gamma((e_{1-(n+1)})) = \gamma((e_{1-n}))$, and otherwise $\gamma((e_{1-(n+1)})) :=$ the next hypothesis

$\gamma$ stabilizes to conjecturing the first truth hypothesis in $H$ for which $\alpha$ stabilizes to the assessment "true".

This discovery rule of formal learning theory is an example of the *rational choice paradigm* of theory discovery. Here one assumes that a list $H$ which contains all possible and interesting hypothesis is given *in advance*, i.e., before any evidences have been received. The list H is often assumed to form a partition, that is, the hypotheses in H are pairwise incompatible and exhaustive in relation to an assumed background knowledge. Theory development consists in choosing the optimal (best confirmed) hypotheses in the face of the received evidence set $E_n$.

Scientists rarely possess a list of all interesting hypotheses in advance from which they choose. Usually new hypotheses are constructed in science from given evidence by inductive or abductive learning mechanisms and are then put to subsequent empirical test. We call this view the *construction* paradigm of theory development. To fill his paradigm with content we need algorithms which tell us how to construct and revise plausible theories in the face of an ongoing evidence stream.

There's more to this but I'm not interested currently

## Theoretical Concepts, Lakatosian Research Programs and Refined Falsificationism
---
Most scientific theories contain *theoretical concepts* such as "electron" or "magnetic force" which don't occur in the evidence stream but go beyond the observable.

For theoretical hypotheses, i.e. hypotheses containing theoretical terms, the empircist assumption fails: their truth value is not determined by the evidence stream, even not int he limit, moreover, they are not obtainable from evidences by inductive generalizations from finite evidence sets. How are theoretical hypotheses confirmed?

Popper pointed out that scientific theories entail observational consequences and are, though not being verifiable, at least falsifiable via the rule of Modus Tollens. Popper's account of theory development rests on the idea that theories which are falsified by actual evidences are laid aside.

This account was criticized by Kuhn and Lakatos. Kuhn showed that in the history of science, theories which contradict data are not rejected or laid aside; scientists rahter introduce *auxiliary assumptions* which save the theory core or theory "paradigm" from being falsified.

Lakatos's account of falsification elaborates on this. [[The Duhem Thesis and the Quine Thesis|Scientific hypotheses are never assessed in isolation]].  They form theories, which are systems of statements together with an *epistemic ranking* over them. This ordering decides which elements are to be given up when conflicts between theory and data arise. Lakatos speaks of theories as consisting of a *theory core* that is surrounded by a *periphery* which contains less and less important parts, the more one moves from inside into outside layers of the theory. The outermost layer of theory contains auxiliary assumptions, which assert the existence or non-existence of *disturbing factors*. They figure like a protective belt because by introducing new disturbing factors, the theory core can always be protected from falsification.

Consider J. Adams and U. Le Verrier discovering a discrepancy between the predicted and actually observed orbit of the planet Uranus, instead of throwing out the core of Newontian physics they postulated the existence of a yet undiscovered planet, Neptune, whose gravitational effect on Uranus was assumed to be responsible for its divergence from the predicted orbital path.

A similar scenario occurred when Le Verrier observed a divergence of the planet Mercury form its predicted orbit and postulated the existence of a yet smaller planet named Vulcan, this time a failed prediction.

Similar accounts of theory development had already been given by Duhem and Quine. Duhem's thesis of the holism of theory falsification says that if a particular version $T$ of a theory, consisting of $T$'s core plus a particular periphery, contradicts a datum e, then all what one knows is that some part of $T$ is false, but logic alone doesn't dictate which part of $T$ should be given up,

Lakatos provides an answer to this question: the theory-parts which are given up should be as peripheral and unimportant as possible. This is a version of "prioritized base contraction" in the sense of Rott. It is always logically possible to solve conflicts with data by peripherical theory-revisions, but Lakatos sets up an important rationality constraint to steps of this sort: a theory-revision should be *theoretically progressive*, by which Lakatos means that the new theory contains all the confirmed empirical content of the old theory plus some additional new empirical "excess" content. Lakatos calls the new theory version empirically progressive if part of this excess content has been independently confirmed. If theory revisions reduce the empirical content of a theory they are called degenerative.

In Lakatos' account of research programmes a theory is a historical entity: if it changes its periphery, it is merely another version of the same theory; only if it changes its core, is it a new theory. Formally speaking, a *theory history* in the sense of Lakatos is a sequence $(T) = (T_0, T_1, ...)$ which is associated with a sequence of evidence sets asa defined previously.

In line with Popper and Lakatos we do not assume that evidence statements are infallible, i.e. the evidence sequence is not necessarily cumulative. Though the evidence sequence is theory-neutral in regard to all those theories whose success is being compared.

Theory-subsequences of the theory history whose theories share the same theory core are called in line with Kuhn *normal* periods of science; while theory-successions in which the theory core changes are called scientific revolutions. 

The following is the Lakatosian criteria for the rational evaluation of theory-development:
11. $E(T) = T \cap S(\mathcal{L}_e)$ is the set of all confirmed or unconfirmed empirical consequences of $T$, and $EC_n(T) = E(T) \cap E_n$ as the set of $T$'s confirmed empirical consequences at time $n$.
12. A theory succession $(T_n, T_{n+1})$ is called(look at paper again for all the ways of calling it)

Lakatos' model fo theory development allows for the rational evlauation of theory development and the rational assessment of theory progress even if one allows fallible evidences and for theories whose truth value is not determined by the complete empirical truth.

## Verismilitude and Truth-Approximation by Theory-Revision
---
Popper has argued that the main goal of science consist in progress in [[Induction and Inductive Logic#Popper|verisimillitude]] or truthlikeness. Although most theories involve idealizations and hence are strictly speaking false, some are much closer to the truth than others. A theory $T_1$ is closer to the truth than another theory $T_2$ iff $T_1$ has more true and less false consequences than $T_2$.

Popper's original definition turned out to be inadequate, in the following period two major families of accounts have been developed which cured the mistake in Popper's original definition. They have been called the disjunctive and the conjunctive approach to truthlikeness.

Without explaining the precise definitions of verismilitude, a major result is that neither the expansion nor revision of a false theory $T$ by a true evidence leads always to an increase of $T$'s verisimilitude.

This holds even if the evidence is a single true basic statement. Truth approximation can still be upheld as a major goal of theory development, althought the paths towards this goal may have intermittent phases in which theories move away from truth.

## From Progress in Empirical Success to Progress in Theoretical Truth: Instrumentalism versus Realism
---
Scientific realism is the view that the empirical success of a theory is a reliable indicator of the approximate truth of the theory, including the truth of its theoretical superstructure. In contrast, scientific instrumentalism holds that the theoretical superstructure of a theory has merely the instrumental purpose of entailing the evidences in a most simply and unifying way, but there's no reason to assume that this theoretical superstructure corresponds to an unobservable external reality.

For scientific realists, decisive progress in theory development consists in progress in truth approximation at the theoretical level.

For instrumentalists, scientific progress is confined to progress in empirical success or empirical adequacy.

The standard justification of scientific realism is the *no-miracles* argument, which goes back to Putnam. The argument says that the empirical success of contemporary scientific theories would be a sheer miracle if we would not assume that their theoretical superstructure is approximately true in the science of scientific realism. This argument is beset by two counterarguments, an empirical and theoretical counterargument.

The empirical theoretical counterargument is the pessimistic meta-induction argument of Laudan. This argument points to the fact that in the history of scientific theories one can recognize radical changes at the level of theoretical superstructures, although there was continuous progress at the level of empirical success. On simple inductive grounds one should expect therefore that the theoretical superstructures of our presently accepted theories will also be overthrown in the future, and hence can in no way be expected to be approximately true.

The theoretical counterargument is the no-speculation argument. It points out that for every set of possible observations $E$ one may construct ex-post and ad-hoc some speculative theory $T$ which just entails $E$, but has no independent empirical consequences. The empirical success of such speculative ad-hoc theories is in no way a reliable indicator of their approximate truth.

