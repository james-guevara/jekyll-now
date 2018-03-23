---
published: false
---
## Some Quora Bookmarks


[What are some interesting feature-space techniques in machine learning?](https://www.quora.com/What-are-some-interesting-feature-space-techniques-in-machine-learning/answer/Muni-Sreenivas-Pydi)

Good explanation of random projections, which are useful for efficiency. Basically you can reduce the dimensionality of your data while preserving the distances between your datapoints (up to some small factor) by multiplying your data matrix with a random matrix, the entries of which can be Gaussian or Bernoulli random variables. Sounds useful as a preprocessing step for clustering algorithms like k-means or nearest neighbors (which only take into account pairwise distances between datapoints).

I'll have to remember to dive into Alex Clemmer's answer to [What is a simplified explanation and proof of the Johnson-Lindenstrauss lemma?](https://www.quora.com/What-is-a-simplified-explanation-and-proof-of-the-Johnson-Lindenstrauss-lemma/answer/Alex-Clemmer). 



[What is the interpretation and intuitive explanation of Gini impurity in decision trees?](https://www.quora.com/What-is-the-interpretation-and-intuitive-explanation-of-Gini-impurity-in-decision-trees/answer/Sriraman-Madhavan)

Gini impurity quantifies how good your threshold is for a decision tree. Gives an example (using height to predict gender).


[What is renormalization in quantum theory?](https://www.quora.com/What-is-renormalization-in-quantum-theory-explained-to-graduated-only-not-doctors/answer/Teddy-Baker)

Renormalization refers to a set of procedures that allows one to analyze how a theory changes under a scale transformation. The use of a regulator in physics, a high energy cutoff, can be seen as a short distance cutoff due to the uncertainty principle (higher energy means a shorter distance scale). Block spin diagrams give a good picture.


[What is topology? How does it relate to machine learning?](http://qr.ae/TU1v81)

Talks about using topology to describe data. If you're interested in the connectivity of your data, or how many holes there are in the data, then you may want to use a tool like persistent homology, which, as far as I can tell, tells you how the connectivity of your data changes as the distance threshold (for samples to be connected) changes. Probably easier to understand with a visualization - just look up persistent homology on Google Images. Anyway, I skimmed a paper recently that uses persistent homology to characterize the generalizability of neural networks, which I may write about later: [On Characterizing the Capacity of Neural Networks using Algebraic Topology](https://arxiv.org/abs/1802.04443)
