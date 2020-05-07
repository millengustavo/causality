# The Book of Why: The New Science of Cause and Effect
Author: Dana Mackenzie and Judea Pearl

<img src="https://images-na.ssl-images-amazon.com/images/I/41GY4%2B3eAyL._SX320_BO1,204,203,200_.jpg" title="book" width="150" />

# Introduction: Mind over Data

Book mission:
1. to lay in nonmathematical language the intellectual content of the Causal Revolution and how it
is affecting our lives as well as our future;
1. to share some of the heroic journeys, both successful and failed, that scientists have embarked on when confronted by critical cause-effect questions.
2. to describe how robots can be constructed that learn to communicate in our mother tongue—the language of cause and effect

> "The human brain is the most advanced tool ever devised for managing causes and effects (...) Data is profoundly dumb. Data do not understand causes and effects; humans do."

Calculus of causation consists of two languages: 
- Causal diagrams, to express what we know
- A symbolic language (resembling algebra), to express what we want to know

The *do*-operator signifies that we are dealing with an intervention rather than a passive observation

"Algorithmization of counterfactuals"

## A Blueprint of Reality
![Blueprint of reality](../images/book_of_why_flowchart.png)

We collect data only after:
- we posit the causal model
- we state the scientific query we wish to answer
- we derive the estimand

Information about the effects of actions or interventions is simply not available in raw data, unless it is collected by controlled experimental manipulation

> "If we ever want robots to answer 'Why?' questions or even understand what they mean, we must equip them with a causal model and teach them how to answer counterfactual queries"

# Ch1. The Ladder of Causation

The world is not made only of dry facts, these facts are glued together by cause-effect relationships. Causal explanations, not dry facts, make up the bulk of our knowledge, and should be the cornerstone of machine intelligence.

The connection between imagining and causal relations is almost self-evident. It is useless to ask for the causes of things unless you can imagine their consequences.

## The three levels of causation

Three distinct levels of cognitive ability: seeing, doing and imagining

1. **Association (seeing)**

One event is associated with another if observing one changes the likelihood of observing the other

2. **Intervention (doing)**

We cannot answer questions about interventions with passively collected data, no matter how big the data set or how deep the neural network

3. **Counterfactuals (imagining)**

“What if I had done…?” and “Why?” -> Both involve comparing the observed world to a counterfactual world. Experiments alone cannot answer such questions. 

While rung one deals with the seen world, and rung two deals with a brave new world that is seeable, rung three deals with a world that cannot be seen (because it contradicts what is seen). To bridge the gap, we need a model of the underlying causal process, sometimes called a “theory” or even (in cases where we are extraordinarily confident) a “law of nature.” In short, we need understanding.

## The mini-Turing test

Take a simple story, encode it on a machine, and then test to see if the machine can correctly answer causal questions that a human can answer

## Scheme for passing the mini-Turing test

- Translate the story into a diagram
- Listen to the query
- Perform a surgery that corresponds to the given query (intervetional or counterfactual; if the query is associational then no surgery is needed)
- Use the modified causal model to compute the answer

## On Probabilities and Causation

Probabilities lie on the first rung of the Ladder of Causation and cannot ever (by themselves) answer queries on the second or third rung. Any attempt to "define" causation in terms of seemingly simpler, first-rung concepts must fail

> While probabilities encode our beliefs about a static world, causality tells us whether and how probabilities change when the world changes, be it by intervention or by act of imagination

# Ch3. From evidence to causes: Reverend Bayes meets Mr. Holmes

A causal diagram is a Bayesian network in which every arrow signifies a direct causal relation, or at least the possibility of one, in the direction of that arrow. 

Not all Bayesian networks are causal, and in many applications it does not matter. However, if you ever want to ask a rung-two or rung-three query about your Bayesian network, you must draw it with scrupulous attention to causality

> The most important role of Bayes's rule in statistics: we can estimate the conditional probability directly in one direction and use mathematics to derive the conditional probability in the other direction.

In Bayesian networks, we tell the computer the forward probabilities, and the computer tells us the inverse probabilities when needed

Bayes's rule: a way to update our belief in a particular hypothesis. An empirical claim to faithfully represent the English expression "given that I know". Bayes's rule informs our reasoning in cases where ordinary intuition fails us or where emotion might lead us astray

## Scientific method

In many ways, Bayes’s rule is a distillation of the scientific method. 

The textbook description of the scientific method goes something like this: (1) formulate a hypothesis, (2) deduce a testable consequence of the hypothesis, (3) perform an experiment and collect evidence, and (4) update your belief in the hypothesis. 

Usually the textbooks deal with simple yes-or-no tests and updates; the evidence either confirms or refutes the hypothesis. All evidence comes with a certain amount of uncertainty. Bayes’s rule tells us how to perform step (4) in the real world.

## Bayesian Networks: what causes say about data

### A -> B -> C
Chain, or mediation

B = the mechanism, or mediator, that transmits the effect of A to C

### A <- B -> C
Fork

B = common cause or confounder of A and C

A confounder will make A and C statistically correlated even though there is no direct causal link between them

### A -> B <- C
Collider

E.g. Talent -> Celebrity <- Beauty

If A and C are independent and we condition on B, we will see a negative correlation between A and C  (Finding out that a celebrity is unattractive increases our belief that he or she is talented)

This negative correlation is sometimes called collider bias or the "explain-away" effect

**Chains, forks and colliders**: keyholes through the door that separates the first and second levels of the Ladder of Causation. Secrets of the causal process that generated the data we observe; in the form of conditional dependences and independences in the data

## Bayesian networks
Is nothing more than a compact representation of a huge probability table

The most interesting thing to do with Bayesian networks is to solve the inverse-probability problem

Whereas a Bayesian network can only tell us how likely one event is, given that we observed another (rung-one information), causal diagrams can answer interventional and counterfactual questions

> Statisticians consider it permissible to talk about causes and effects in one situation: a **randomized controlled trial (RCT)** in which a treatment A is randomly assigned to some individuals and not to others and the observed changes in B are then compared. Here, both orthodox statistics and causal inference agree on the meaning of the sentence “A causes B.”

# Ch4. Confounding and Deconfounding: or Slaying the Lurking Variable

**Controlled experiment**: Give one group a new treatment, while the other group (control) either gets the old treatment or no special treatment at all. If, after a suitable amount of time, you see a measurable difference between the two supposedly identical groups of people, then the new treatment must be the cause of the difference

*Prospective*: the groups are chosen in advance

Confounding bias occurs when a variable influences both who is selected for the treatment and the outcome of the experiment. Sometimes the confounders are known; other times they are merely suspected and act as a “lurking third variable.”

In a causal diagram, confounders are extremely easy to recognize: the variable Z at the center of the **fork** is a confounder of X and Y. 

> The term “confounding” originally meant “mixing” in English, and we can understand from the diagram why this name was chosen. The true causal effect X -> Y is “mixed” with the spurious correlation between X and Y induced by the fork X <- Z -> Y

- (1) Confounding needs and has a causal solution
- (2) Causal diagrams provide a complete and systematic way of finding that solution

## The skillful interrogation of nature: why RCTs work

Randomization eliminates confounder bias and enables the researcher to quantify his uncertainty

**Double blinding**: clinical trials with human subjects that conceal the treatment/control information from both the patients and the experimenters

Randomization severs every incoming link to the randomized variable, including the ones we don't know about or cannot measure

> The *do*-operator gives us scientifically sound ways of determining causal effects from non experimental studies. Causal estimates produced by observational studies may be labeled **"provisional causality"**: causality contingent upon the set of assumptions that our causal diagram advertises

## The new paradigm of confounding
> “Confounding is not a statistical notion. It stands for the discrepancy between what we want to assess (the causal effect) and what we actually do assess using statistical methods. If you can’t articulate mathematically what you want to assess, you can’t expect to define what constitutes a discrepancy.”

**Back-door criterion**: operational test for confounding

## The do-operator and the back-door criterion

- (a) In a chain junction, A  B  C, controlling for B prevents information about A from getting to C or vice versa.
- (b) Likewise, in a fork or confounding junction, A  B  C, controlling for B prevents information about A from getting to C or vice versa.
- (c) Finally, in a collider, A  B  C, exactly the opposite rules hold. The variables A and C start out independent, so that information about A tells you nothing about C. But if you control for B, then information starts flowing through the “pipe,” due to the explain-away effect.
- (d) Controlling for descendants (or proxies) of a variable is like “partially” controlling for the variable itself. Controlling for a descendant of a mediator partly closes the pipe; controlling for a descendant of a collider partly opens the pipe.

> To deconfound two variables X and Y, we need only block every noncausal path between them without blocking or perturbing any causal paths. More precisely, a back-door path is any path from X to Y that starts with an arrow pointing into X. X and Y will be deconfounded if we block every back-door path (because such paths allow spurious correlation between X and Y). If we do this by controlling for some set of variables Z, we also need to make sure that no member of Z is a descendant of X on a causal path; otherwise we might partly or completely close off that path

# Ch7. Beyond Adjustment: the conquest of mount intervention

## The simplest route: the Back-door adjustment formula

Most familiar method of predicting the effect of an intervention is to "control" for confounder using the adjustment formula

This is the method to use if you are confident that you have data on a sufficient set of variables (deconfounders) to block all the back-door paths between the intervention and the outcome

> A regression coefficient not always represents a causal effect - you can't rely on the data alone to tell you the difference

The back-door criterion tells us which sets of variables we can use to deconfound our data. The adjustment formula actually does the deconfounding

## The Front-door criterion

It allows us to control for confounders that we cannot observe, including those that we can't even name (same as RCTs, the "gold standard" of causal effect estimation)

Front-door estimates do the same as RCTs, with the additional virtue of observing people's behavior in their own natural habitat instead of a laboratory.

## The Do-Calculus, or mind over matter

**Front- and back-door adjustment formulas** -> the ultimate goal is to calculate the effect of an intervention, P(Y | do(X)), in terms of data such as P(Y | X, A, B, Z,…) that do not involve a do-operator -> then we can use observational data to estimate the causal effect, allowing us to leap from rung one to rung two of the Ladder of Causation

### Rule 1
> P(Y | do(X), Z, W) = P(Y | do(X), Z)

Provided that the variable set Z blocks all the paths from W to Y after we have deleted all the arrows leading into X

### Rule 2
> P(Y | do(X), Z) = P(Y | X, Z)

If Z satisfies the back-door criterion. Is the same as saying: after we have controlled for a sufficient deconfounding set, any remaining correlation is a genuine causal effect

### Rule 3
> P(Y | do(X)) = P(Y)

If there is no path from X to Y with only forward-directed arrows. Same as: if we do something that does not affect Y, then the probability distribution of Y will not change

### Syntactic interpration of the rules
- Rule 1 permits the addition or deletion of observations. 
- Rule 2 permits the replacement of an intervention with an observation, or vice versa. 
- Rule 3 permits the deletion or addition of interventions

### One issue with do-calculus
It enables the construction of a proof, but it does not help us find one. It is an excellent verifier of a solution but not such a good searcher for one

### Instrumental variables
Important tool in that they help us uncover causal information that goes beyond the do-calculus. The latter insists on point estimates rather than inequalities and would give up on cases in which all we can get are inequalities. 

The do-calculus is more flexible than instrumental variables. In do-calculus we make no assumptions whatsoever regarding the nature of the functions in the causal model. But if we can justify an assumption like monotonicity or linearity on scientific grounds, then a more special-purpose tool like instrumental variables is worth considering
