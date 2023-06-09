# Text Summarizer using OpenAI API

![image](https://github.com/amandotexe/Text-Summariser/assets/71628234/bd13c8db-e7a4-47f6-abc3-d1e0e867dd34)

This is project uses the OpenAI API to generate a summary of a given text. The summary will consist of a few sentences that capture the main idea of the text.

## Installation

Before using this program, you need to install the OpenAI library by running the following command:

```
pip install openai
```

You will also need to set up an OpenAI account and obtain an API key. You can do this by visiting the [OpenAI website](https://openai.com/).

## Usage

To use the text summarizer, first import the `openai` library and set your API key:

```python
import openai
openai.api_key = "YOUR_API_KEY"
```

Then, you can call the `summarize_text` function, passing in the text you want to summarize as a string:

```python
def summarize_text(text, num_sentences=3):
    response = openai.Completion.create(
      engine="text-davinci-002",
      prompt=f"Please summarize the following text into {num_sentences} sentences:\n{text}\n",
      temperature=0.5,
      max_tokens=100,
      n=1,
      stop=None,
      timeout=10,
    )
    summary = response.choices[0].text.strip()
    return summary
```

The function will return a summary of the text as a string.

By default, the function generates a summary of three sentences. You can specify a different number of sentences by passing in a different value for the `num_sentences` parameter.

## Example

Here's an example of how to use the `summarize_text` function:

```python
text = "The quick brown fox jumps over the lazy dog. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla facilisi. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Sed vel blandit nibh. Sed tempus erat vel sapien laoreet, nec eleifend odio viverra. Sed non tellus lacus. Donec non mi justo. Sed nunc sapien, elementum id vestibulum a, volutpat sit amet velit."
summary = summarize_text(text)
print(summary)
```

Output:

```
The quick brown fox jumps over the lazy dog. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed tempus erat vel sapien laoreet, nec eleifend odio viverra.
```

## Limitations

This text summarizer uses the OpenAI API, which is a powerful tool for generating natural language. However, it has some limitations. The API can only summarize up to 100 tokens, which is equivalent to about 2-3 sentences of text. Therefore, the summary generated by this program may not capture all the important details of longer texts.

Additionally, the quality of the summary may depend on the quality of the input text. The summarizer may not be able to generate an accurate summary if the input text is poorly written or contains unclear or ambiguous language.

## Credits

This program was created by ChatGPT, a large language model trained by OpenAI. It is based on the GPT-3.5 architecture and was trained on a vast corpus of text data to generate human-like responses to natural language queries.
