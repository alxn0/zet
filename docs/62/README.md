# Adjusting creativity/randomness in LLMs

## What is it

- Can control LLMs behavior by adjusting `temperature`, `top-k` and `top-n`.
- For task where you want the same result for the same input (e.g., classification, information extraction), set `temperature` to 0.
- For task where you want more creativity (e.g., brainstorming, summarization), choose higher `temparature` (up to 1)

## Temperature

see this [post](https://medium.com/mlearning-ai/softmax-temperature-5492e4007f71)

Temperature is a hyperparameter of neural networks used to control the randomness of predictions by scaling the logits before applying [softmax](https://en.wikipedia.org/wiki/Softmax_function).

In simple words, it changes the mapping between the logits (i.e., real-value) to a probability.

The effect of temperature is that it **flatten the probability distribution**

![Screenshot from 2024-02-26 22-37-41.png](/Screenshot%20from%202024-02-26%2022-37-41.png)

## Top-p and -k
- **Top-p**: sample the minimum set of tokens whose probabilities add up to probability `p` or greater.
- **Top-k**: Take the `k` option with highest probability
- If you want to adjust `top_p` and `top_k` and see different results, remember to set `temperature` to be greater than zero, otherwise the model will always choose the token with the highest probability.
- The decoding strategy applies `top_k`, then `top_p`, then `temperature` (in that order).


## References

<https://learn.deeplearning.ai/courses/google-cloud-vertex-ai/lesson/6/text-generation-with-vertex-ai>
