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

# The Ladder of Causation

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

