## Norman Malcolm's Argument
Malcolm says that Anselm maintained not only that existence contributes to greatness, and is in Descartes terms a perfection, but also in *Proslogion* III, that 'necessary existence' is a perfection.

If God exists his existence is [[Meaning, Modality, and Possible Worlds Semantics|necessary]]. Thus God's existence is either impossible or necessary. Assuming that it is not impossible, it follows that He necessarily exists.

Surely it's not impossible that there is a perfect being. So goes Malcolm's argument. Charles Hartshorne is sometimes represented as spelling out in formal terms Malcolm's Anselmian argument. 

There's a flaw in Malcolm's argument identified by Plantinga, that is not present in Hartshorne's argument. Malcolm supposes that it is enough for his argument that necessary existence should be a perfection. Hartshorne sees that more is needed and uses more.

## Charles Hartshorne's Argument
After detailing Hartshorne's argument, we'll relate it to the argument of *Proslogion* II.

### *Hartshorne's deduction.*
Hartshorne offers a deduction of the existence of a perfect being, $\exists x Px$, from two [[Necessity and Possibility|modalized premises]].  He dubs his first premise 'Anselm's Principle': $$\begin{align}\textbf{AP} && \Box[\exists x Px \to \Box\exists x Px]\end{align}$$
where: $\exists x Px := \text{there exists a perfect being}$

Since he does not in his argument 'break into this sentence', he could have used a single letter for it, say 'P', and made Anselm's principle $$\Box(P \to \Box P)$$
Hartshorne provides for **AP** the free translation "perfection could not exist contingently" for $$\neg\Diamond (P \land \neg \Box P)$$
which is logically equivalent to $\Box (P \to \Box P)$. Hartshorne may have supposed that **AP** is essentially Anselm's finding that "this being so truly exists that it cannot be even thought not to exist". Where Anselm writes of *what cannot be thought*, Hartshorne 'reads' *what is logically impossible*.

His second premise comes with the comment, 'Intuitive postulate'. It is the apparently innocuous proposition that perfection is possible: $$\begin{align}\textbf{IP} && \Diamond\exists xPx\end{align}$$
It follows from **AP** and **IP** that there is necessarily a perfect being, $\exists x Px$.

Following Hartshorne, let '$Q$' abbreviate '$\exists x Px$'. $$\begin{align}
&\Diamond Q && \text{Premise: IP}\\
&\Box(Q \to \Box Q) && \text{Premise: AP}\\
&\neg\Diamond\Box Q && \text{ACP}\\
&\Box(\neg \Box Q \to \neg Q) && \text{From AP}\\
&\Box\neg \Box Q \to \Box\neg Q && \text{4, S5}\\
&\Box\neg \Box Q && \text{3, Def of } \Diamond\\
&\Box\neg Q && \text{5, 6, MP}\\
&\neg\Diamond\neg\neg Q && \text{7, Def of }\Diamond\\
&\neg\Diamond Q && \text{8, DN}\\
&\neg\Diamond\Box Q \to \neg\Diamond Q&& \text{3, 8, ACP}\\
&\Diamond\Box Q && \text{1, 9, MT}\\
&\Box Q && \text{10, S5}
\end{align}$$
The major argument of *Proslogion* II can be cast as from two premises, each delivered by a subsidiary argument. The first is that: $$\text{a perfect being exists }\textit{in the mind},$$
which is Anselmian speech for Hartshorne's "a perfect being is *possible*": $$\begin{align}\textbf{IP} && \Diamond\exists xPx\end{align}$$
The second is that: $$\text{it cannot be that a perfect being exists in the mind, though no perfect being exists in reality,}$$
which is Anselmian speech for $$\begin{align}\textbf{AnLP }\text{Anselm's Leibnizian Principle} && \neg\Diamond[\Diamond\exists xPx \land \neg \exists x Px]\end{align}$$
or equivalently: $$\Box[\Diamond \exists x Px \to \exists x Px]$$
which is to say, necessarily, if a perfect being is possible, then a perfect being exists. Or in Anselmian speech, that if a perfect being exists in the mind, then a perfect being exists in reality.

Hartshorne got his second premise, ***AP***, from Proslogion III's idea that a perfect being would exist, and be perfect, necessarily. ***AnLP*** is delivered in *Proslogion* II without anticipation of ideas in *Proslogion* III. Yet ***AP*** and ***AnLP*** are strictly equivalent.

## Fly in the Ointment?
Plantinga finds fault with an argument hat he implies is the best that one can get from the ideas of Charles Hartshorne and Norman Malcolm. The argument uses the premises, ***IP*** and ***PERFnecEx***, "A being is perfect in a possible world only if it *exists in every possible world*": $$\Box\forall x\Box(Px \to \Box\exists!x)$$
which can be taken to say that 'necessary existence is a perfection.' The trouble he identifies with the argument is that, though is seeks to prove that there is a perfect being, $\exists x Px$, all it 'gets' is that *there is a necessary being that is possibly perfect*. $$\exists x (\Box\exists! x \land \Diamond Px)$$
## Unfair to Hartshorne.
Plantinga may in his critique do justice to Malcolm's idea, which seems to have been that an Anselmian argument is available as soon as one counts necessary existence as perfection. But Hartshorne would see that ***PERFnecEx*** leaves out an important Anselmian enhancement, namely that a perfect being would not only necessarily exist, but be necessarily perfect.

Part of what lies behind Hartshorne's ***AP*** is that "anything exemplifying perfection merely contingently would be imperfect, and so would not exemplify it at all".

Plantinga implies that though Hartshorne says that "necessary existence is a perfection", he, just as Malcolm, does not say that necessary or essential perfection is a perfection. By principle of charitable interpretation, however, we should find that Hartshorne says both things.

To be fair to Hartshorne, Plantinga needs to amend the argument of the previous section, replacing ***PERFnecEx*** with ***PERFnecEx&necPerf***, $$\Box\forall x \Box[Px \to \Box(\exists!x \land Px)],$$
which can be taken to say that both necessary existence and necessary perfection are perfections. The conclusion sought, that $\exists x Px$, then follows. 

