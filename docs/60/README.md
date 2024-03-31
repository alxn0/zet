# Text embedding

## What is it?
- A way of representing data as points in space where the locations are **semantically meaningful**

## How it is computed?

### Simple method / Legacy
- Embed each word separately, and take the sum or mean of all the word embeddings.
- Have a list of commonly occuring words and separately train a set of parameters to give embedding for each words.
- Does not understand context of a word.
	- E.g., The kids play | See a play.

### Modern embeddings
- Use a transformer neural network to compute a context-aware representation of each word, then take an average of the context-aware representations.
- Take each words, and compute an embedding while taking account of the surrounding words embedding.
- Compute embeddings for each token (e.g., sub-word) rathen than word. Works with misspelt and novel words.
- Much more sophisticated embedding. Open the way to modern LLMs

## References

<https://learn.deeplearning.ai/courses/google-cloud-vertex-ai/>
