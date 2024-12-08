# ChatBot using Neural Network

This project demonstrates building a simple chatbot using a neural network and TensorFlow/TFLearn. It uses a JSON file (`intents.json`) to define intents, patterns, and responses, and trains a model to classify user input and provide appropriate responses.  It also incorporates the concept of context to handle more complex conversations.

## Features

* **Intent Recognition:** Classifies user input into predefined intents.
* **Pattern Matching:** Uses pattern matching to associate user input with intents.
* **Neural Network Model:** Employs a neural network (using TFLearn) for intent classification.
* **Contextual Awareness:** Maintains context to provide relevant responses in multi-turn conversations.
* **JSON Data Storage:**  Uses a JSON file to store intents, patterns, and responses, making it easy to customize the chatbot's knowledge.


## Requirements

* Python 3.6+
* TensorFlow
* TFLearn
* NLTK
* NumPy
* json
* pickle


Install required libraries using:
```bash
pip install tensorflow tflearn nltk numpy
```

Download NLTK resources:
```python
import nltk
nltk.download('punkt')
nltk.download('wordnet') # Although not directly used in the current code, 'wordnet' is often helpful for chatbot development.
```

## Usage

1. **Prepare the Data:** The `intents.json` file contains the training data. Customize this file by adding, modifying, or removing intents, patterns, and responses.

2. **Training:** Run `Chatbot.py` (or the provided Jupyter Notebook `Chatbot.ipynb`) to train the neural network. The trained model will be saved as `model.tflearn`, and training data will be pickled to `training_data`.

3. **Interacting with the Chatbot:** The `response()` function in `Chatbot.py` takes user input and returns a response. You can integrate this function into a larger application or use it directly for testing.

## File Structure

* `Chatbot.ipynb`: Jupyter Notebook containing the chatbot code (can be converted to `Chatbot.py` for running as a script).
* `Chatbot.py`: Python script version of the chatbot (generated from the notebook).
* `intents.json`: Contains the training data (intents, patterns, and responses).
* `model.tflearn`: Saved trained model file (generated after training).
* `training_data`: Pickled training data (generated after training).

## Customization

* **`intents.json`:** Modify this file to change the chatbot's knowledge base. Add new intents, patterns, and responses to expand its capabilities.
* **Model Parameters:** Adjust parameters like `n_epoch` and `batch_size` in the training section of the code to fine-tune the model's performance.
* **Error Threshold:**  Modify `ERROR_THRESHOLD` to control the confidence level required for the chatbot to select an intent.


## Contextualization

The code implements contextualization by using the `context_set` and `context_filter` keys within the `intents.json` file.  `context_set` sets the context after a specific intent is matched, and `context_filter` ensures that an intent is only matched if the correct context is active.

## Example Interaction

```python
response("Hi there!") #  Might print: "Hello, thanks for visiting"
response("What are your hours?") # Might print: "We're open every day 9am-9pm"
response("Do you deliver?") # Might print: "Yes, we provide home delivery through UBER Eats and Zomato?"  Sets context to "food"
response("What's on the menu?") # Because context is "food", the chatbot will now understand this question in the context of delivery and respond accordingly.
```


## Further Development

* **Improved Preprocessing:** Implement more advanced preprocessing techniques like lemmatization, stop word removal, and synonym handling to improve accuracy.
* **Integration with Messaging Platforms:** Integrate the chatbot with messaging platforms like Facebook Messenger, Slack, or Telegram.
* **Database Integration:** Connect the chatbot to a database to store and retrieve information.
* **More Sophisticated Models:** Explore more advanced neural network architectures like recurrent neural networks (RNNs) or transformers to handle more complex conversations and generate more natural responses.



This enhanced README provides clearer instructions, emphasizes key features like contextualization, and suggests further development possibilities, making the project more accessible and useful for both users and contributors.
