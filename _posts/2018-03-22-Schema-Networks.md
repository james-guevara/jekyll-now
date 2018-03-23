---
published: true
---
## General Game Playing with Schema Networks (by Vicarious)

An interesting model: [General Game Playing with Schema Networks](https://www.vicarious.com/2017/08/07/general-game-playing-with-schema-networks/). 

The article gives a good overview, but essentially a "schema network" is a generative graphical models that models various things in an environment as schemas. 

When playing a new game, a person develops a conceptual understanding of the game. So when someone plays Breakout for the first time, they interpret the pixels of the game in terms of prior experience, e.g. "a red ball bounces between the sides of the screen" (rather than "a bunch of pixels flickering on the screen"). They also notice things like how the bricks disappear when the ball hits them, and how this leads to numbers on the screen increasing (i.e. a reward). They notice how the game ends when the ball falls under the paddle. This data and the prior experience tells the person what the goal is in relatively few frames.

Naturally, we can then ask whether the agents trained with state-of-the-art RL algorithms are developing the same kind of conceptual understanding. They train a deep RL agent using the [A3C algorithm](https://cgnicholls.github.io/reinforcement-learning/2017/03/27/a3c.html) to play Breakout, and it performs very well. But when they make minor changes to the game (adjusting the height of the paddle or placing another wall), the agent fails to demonstrate such a conceptual understanding:

"A3C overfits to a narrow strategy that exploits specific statistics of the version of the game it was trained on, but it has not gained a conceptual understanding of the game's dynamics or rules. This kind of RL is called model-free because the agent does not develop a predictive causal model of the world. Deep RL behaviors that often get interpreted as 'intelligence' re simply stimulus-response mappings that rely on brittle cues."

Schema networks model things in the game as schemas (nouns), their attributes (adjectives), and interactions between entities (verbs). In practice, they assume that a vision system has already segmented these schemas (which would be objects like a paddle, bricks, etc.).  New schemas can be instantiated in new situations to make sense of the situation. 

"A schema describes how the future value of an entity’s attribute depends on the current values of that entity’s attributes and possibly other nearby entities. Each schema can be thought of as a predictor. These predictors are learned automatically from data. For instance, a schema might dictate that the Breakout ball’s velocity will change in the next frame, based on its current velocity and the relative position of a brick. Another schema might predict that the paddle will move to the left when the “left” action is taken by the player and there is an empty space to the left. Schemas may also predict rewards, entity creation, and entity deletion. The schema representation allows for automated forward and backward causal reasoning."

Also, the probabilistic graphical model structure allows for use of inference algorithms like belief propagation and Monte Carlo Tree Search (MCTS). For learning, they use a greedy algorithm based on linear and binary programming. 

The schema networks perform relatively well on the games Breakout, Space Invaders, and Sokoban. For Space Invaders, they introduced "creation" and "deletion" schemas into the learning pipeline. MCTS allows for a better visualization of future actions. 

What I like most about schema networks is their  interpretability. It's easy to understand what's going on the environment based on the "schemas" (they're usually objects on the screen like bricks or paddles). The article talks very little about obtaining these schemas (pretty much use an autoencoder for Atari games), but near the end they talk about integrating the schema network with a "generative model for vision". I assume work such as [Composing graphical models with neural networks for structured representations and fast inference](https://arxiv.org/abs/1603.06277) would be useful. 

The work also, in my view, serves as a bridge between machine learning and cognitive science. So far deep learning algorithms have been uninterpretable, and the methods to disambiguate what's happening when particular neurons activate don't seem well grounded. But maybe interpretability won't be necessary.

I think the deep learning paradigm is here to stay (based on some neuroscience stuff), and will be integrated with things like schema networks, knowledge graphs (via GCNs perhaps?), "intuitive physics engines", memory networks, neural Turing machines, attention, predictive processing, and other inductive priors. I hope to go over all this stuff in later posts.

Anyway, here's their paper: [Schema Networks: Zero-shot Transfer with a Generative Causal Model of Intuitive Physics](https://arxiv.org/abs/1706.04317)
