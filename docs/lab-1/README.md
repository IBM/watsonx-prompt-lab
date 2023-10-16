# Basics of Prompt Engineering

**Note:** The following images show actual results from watsonx.ai. The slight gray text is what we provided to the model.  The blue highlighted text is how the model responded.

### 1.0 LLM Foundations
Before we jump into exploring the capabilities of watsonx.ai, we first need to lay a foundation for how Large Language Models (LLMs) work, and how we can tune the model and parameters to change their output. Gaining this understanding will make us more effective prompt engineers.

<img src="../images/0.1.png" width="80%" alt="prompt" />

When you open up watsonx.ai and click the `Freeform` mode-option, this is what you will be shown. The large central text area is the prompt editor. On the right-side, you can display the model parameters that you can use to select to optimize how the model responds to your prompt. On the bottom-left, is a summary of the number of tokens used by your prompt during execution.

### 1.1 Tokens

Each time you enter a prompt, your **input** tokens and **generated** tokens will update. Tokens are an important concept to understand as they constrain the performance of your model plus determine the cost of using models. As you will learn throughout the labs, tokens are not a 1:1 match with words in natural language. On average, one token is equal to 4 characters. Before sending your prompt to the model, the prompt's text is _tokenized_ or broken into smaller subsets of characters better understood by a model.

It is important to monitor your token usage to know how much information you are feeding into the model with each prompt, as well as how much text is generated for you. Depending on the model selected in Prompt Builder, you will see a max of 2048 or 4096 tokens. Keep in mind that the more expressive you are with your prompt instructions, the less room the model has to respond back to you.

### 1.2 Everything is text completion

watsonx.ai is not a chatbot interface, so just specifying an instruction or question rarely produces a good result. For instance, what if we ask watsonx.ai to
list ideas to start a dog-walking business?

<img src="../images/1.1.png" width="80%" alt="prompt" />

We can see from the example that simple prompts do not work with smaller LLMs.

### 1.3 Cue the output structure 
To improve the response, we can start by addressing its structure. Include a cue to start the response in the desired structure to receive a structured response. For example, just adding the two characters `1.` to the end of our original prompt can dramatically improve the response:

<img src="../images/1.2.png" width="80%" alt="prompt" />

### 1.4 Provide an example as guidance (One-Shot Prompting)

To receive a higher-quality response, provide an example of the kind of response you want:

<img src="../images/list-ideas-03.png" width="70%" alt="prompt" />

Providing an example before generating with your LLM is called _one-shot prompting_, but adding more examples (i.e. _few-shot prompting_) into your prompt is common practice as well. Generally, increasing the number of examples is a powerful tool to ensure you generate a specific output.

Here's the text from the example for your own experimenting:

```
List ideas to start a lemonade business:
1. Set up a lemonade stand
2. Partner with a restaurant
3. Arrange for a celebrity to endorse the lemonade

List ideas to start a dog-walking business:
1. 
```

### 1.5 Include descriptive details

The more guidance, the better. Below, we add more detail to the prompt.

<img src="../images/list-ideas-04.png" width="80%" alt="prompt" />

# Model Parameters

### 2.0 Adjusting the model's behaviour
The first change we can make is the model (LLM) we use to evaluate our prompt. This is one of the biggest changes you can make, as certain models are better suited for specific tasks. The exercises later on this lab will require you to change the model you use if you want to answer some of the more challenging questions.

In general, some models perform better working with summarization, keywords, and semantics, while other models do better with structured text such as HTML, markdown, or JSON. The best way to figure out which models apply for your use case is to simply test them, but it is important to know that choice of model can make a big difference.

watsonx.ai also provides multiple parameters for configuring how LLMs respond to a prompt.  Selecting the correct parameters can often be more of an art than a science, but investing time into understanding them will be rewarded by better responses.

Explore these parameters using the same text from earlier:
```
List ideas to start a lemonade business:
1. Setup a lemonade stand
2. Partner with a restaurant
3. Arrange for a celebrity to endorse the lemonade

List ideas to start a dog-walking business:
1. 
```

### 2.1 Set the min and max tokens

If you're finding the generated text is too short or too long, try adjusting the parameters that control the number of new tokens:

- The `Min tokens` parameter controls the minimum number of tokens (~words) in the generated response.
- The `Max tokens` parameter controls the maximum number of tokens (~words) in the generated response.

<img src="../images/2.1.png" width="80%" alt="prompt" />

<img src="../images/2.1-2.png" width="80%" alt="prompt" />


### 2.2 Specify stop sequences

If you specify stop sequences, the output will automatically stop when one of them appears in the generated output.

The example below shows an output that continues for longer than wanted it to.

<img src="../images/2.2-0.png" width="80%" alt="prompt" />

To combat this behaviour, we can specify a stop sequence of two carriage returns:

<img src="../images/list-ideas-11.png" width="80%" alt="prompt" />

Now, we have a more satisfying response. The output stops after two carriage returns:

<img src="../images/2.2.png" width="80%" alt="prompt" />


### 2.3 Adjust decoding parameters

If the response is too generic or going on wild tangents, consider adjusting the decoding parameters. Or conversely, the response may not be creative and varied enough.

_Decoding_ is the process of finding the output sequence given the input sequence:

- _Greedy decoding_ selects the word with the highest probability at each step of the decoding process. 
- _Sampling decoding_ selects words from a probability distribution at each step:
  - _Temperature_ refers to selecting high- or low-probability words. Higher temperature values lead to more variability.
  - _Top-p_ (nucleus sampling) refers to selecting the smallest set of words whose cumulative probability exceeds _p_å.
  - _Top-k_ refers to selecting _k_ words with the highest probabilities at each step.  Higher values lead to more variability.

An advantage of greedy decoding is that you will see reproducible results. This can be useful for testing. Setting temperature to `0` in a sampling decoding approach gives the same variance as greedy decoding.

<img src="../images/2.3-0.png" width="80%" alt="prompt" />

<img src="../images/2.3-1.png" width="80%" alt="prompt" />

Additional reading on decoder methods:

- [Most-used decoder methods](https://medium.com/nlplanet/two-minutes-nlp-most-used-decoding-methods-for-language-models-9d44b2375612)
- [Using different decoding methods](https://huggingface.co/blog/how-to-generate)

### 2.4 Add a repetition penalty

Sometimes, you will see text being repeated over and over:

<img src="../images/2.4.png" width="85%" akt="Repeated text" />

You could try to increase the temperature to resolve the problem, however, when text is still repetitive, you can try adding a _repetition penalty_. The higher the penalty, the less likely the results will include repetitive text.

<img src="../images/2.4-1.png" width="85%" alt="Repetative penalty" />

One of the many challenges of prompt engineering is exposed in the example above: bullet points are a type of repetition that we want. In this case, penalizing repetition might work against you too. 

### 2.5 Additional reading on model parameters

While we provided you with an introduction to model parameters, this  
The descriptions above provide a good introduction to model parameters. However, [this third-party blog post on model parameters](https://txt.cohere.com/llm-parameters-best-outputs-language-ai) provides excellent additional examples and visualizations of how model parameters work to help you better understand the concepts.

# General Tips

### 3.1 Try different models

The watsonx.ai documentation describes the available models: [watsonx.ai models](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/fm-models.html?context=wx&audience=wdp)

<img src="../images/3.png" width="80%" alt="prompt" />

### 3.2 Understand your use case

LLMs have great potential, but they do not have logic, knowledge, or domain expertise.  Some use cases are a better fit than others: LLMs excel at tasks that involve generating generic text or common code patterns and transforming given input.

If your prompt includes all the tips and best practices discussed here, yet you're not getting satisfactory results from any of the models, take time to consider whether LLMs actually suit your use case. For example, although we can get reasonable results for simple arithmetic, [LLMs generally cannot handle math well](https://venturebeat.com/business/researchers-find-that-large-language-models-struggle-with-math/)

# Balancing intelligence and security
With great artificial intelligence comes higher security risks. Solutions like ChatGPT are known as _Very Large language Models_ (VLLMs) with 175 billion parameters. They are fine-tuned by the OpenAI team using an additional non-public Chat datasets along with Reinforcement Learning Human Feedback (RLHF) dataset. It is a chatbot-enabled LLM. 

In watsonx.ai, we are interacting directly with smaller LLMs (3-20 billion parameters).  This is a wise choice with regard to security. Prompt injection is a major risk for enterprise-use of LLMs. In prompt injections, a hacker will create an intricate prompt in order to cause a LLM such as ChatGPT to ignore/bypass security protocols and reveal sensitive company information. 

Just imagine you're a hacker. Which model would you choose to target for prompt injection hacking? OpenAI's ChatGPT with 175 billion parameters capable of thousands of tasks or a smaller, more-focused 3 billion parameter model highly tuned for a few isolated tasks?  Which has a larger attack surface for prompt (re-)engineering?

The smaller, simpler models in watsonx.ai present a more difficult challenge for potential hackers. Using many small models rather than a single large one such as ChatGPT creates a wider distribution of sensitive entry points. Each small language model is much harder to manipulate due their limited functionality and high level of prompt engineering that was required to perform their primary tasks. They don’t have the wide range of functions such as ChatGPT.  As programmers know, putting all your resources into a single point of failure is unwise. It's far better to decompose your solution for security, scalability, and control. 


# Further learning

- [Tips for writing foundation model prompts](https://www.ibm.com/docs/en/watsonx-as-a-service?topic=models-prompt-tips)
- [Open source models in watsonx.ai](https://www.ibm.com/blog/ibm-watsonx-ai-open-source-pre-trained-foundation-models-make-ai-and-automation-easier-than-ever-before/)
- [Prompt engineering tutorial](https://txt.cohere.com/llm-parameters-best-outputs-language-ai)