---
published: false
---
## Some Quora Bookmarks

There's a bunch of stuff on Quora that I'll probably never get to. But I can at least summarize some of it here, and post links to some of the more interesting posts. Maybe I can expand on them later.

[What are the recent developments in one shot learning?](https://www.quora.com/What-are-the-recent-developments-in-one-shot-learning/answer/Jonathan-Gordon-23?share=3eba5158&srid=iyKL)

Talks about a paper that uses representations of the final hidden layer in a neural network to generalize to unseen classes for classification. A prior distribution is placed on the weights, which allows for posterior inference on their values for a new class.

Generative models usually entail a training scheme that updates latent variables in such a way that they represent semantically meaningful features.  These models fall under the umbrella term of "unstructured models" - there really isn't any expert knowledge built into these models. 

There's a link to an article called [General Game Playing with Schema Networks](https://www.vicarious.com/2017/08/07/general-game-playing-with-schema-networks/). The premise is that when playing a new game, a person develops a "conceptual understanding" of the game. When someone plays Breakout for the first time, they interpret the pixels of the game in terms of prior experience, and so they'll interpret what's happening in the game as "a red ball bounces between sides of the screen and a paddle near the bottom of the screen", rather than just as "a bunch of pixels flickering on the screen". They'll also notice things like how the bricks disappear when the ball hits them, and how this leads to numbers on the screen increasing, which reminds them of the "score" concept. They'll notice how the game ends when the ball falls under the paddle. All this data (and prior experience) tells the person what the goal of the game is in only a few frames. 

Naturally, we can then ask whether the agents trained with state-of-the-art RL algorithms are developing the same kind of conceptual understanding.

They train a deep RL agent using the A3C algorithm to play Breakout, which does very well. However, when they make minor changes to the game (adjusting the height of the paddle or placing another wall), the RL agent fails to demonstrate such a conceptual understanding. 

"A3C overfits to a narrow strategy that exploits specific statistics of the version of the game it was trained on, but it has not gained a conceptual understanding of the game's dynamics or rules. This kind of RL is called model-free because the agent does not develop a predictive causal model of the world. Deep RL behaviors that often get interpreted as 'intelligence' re simply stimulus-response mappings that rely on brittle cues."

Schema networks are generative graphical models that can purportedly "simulate the future, reason about cause and effect, and plan to reach distant rewards." Agents trained using these scheme networks can achieve high scores on the minor variations of Breakout that confounded the model-free agents.




