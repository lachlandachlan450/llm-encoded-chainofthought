# llm-encoded-chainofthought
Im investigating chain of thought reasoning in LLMs, specifically Qwen (2.5-3B, small model to start with).
This is a result of reading [this article](https://www.lesswrong.com/posts/Lz8cvGskgXmLRgmN4/current-language-models-struggle-to-reason-in-ciphered).

## Process
We start by getting the gsm8k dataset from huggingface - This is a bunch (~10k) of maths problems with reasoned answers. Like the Fabien Roger paper, we are going to encode the chain of thought in rot13 (or some other encoding).
Then we will fine tune Qwen on this dataset (training set size is ~70%), and then we will give it some problems to reason in rot13 on. Hopefully we will see the same result when comparing the answers.
The code for this in Finetuned_Qwen_1, but note that as this was first run in Colab, we only trained a shorter section of the training data set and with lower epochs, higher batch rate, etc.
