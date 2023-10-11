# ChatBot

# How The Code Works?

## Libraries and Frameworks Used
- spacy: The code uses the spaCy library to load the English language model. SpaCy is a natural language processing library that provides tools for text processing and understanding.

- pandas: The Pandas library is used to read and manipulate the dataset from a CSV file. It allows data to be easily loaded and processed.

- Flask: This code creates a simple web application using Flask, a micro web framework for Python. It serves as the user interface for interacting with the chatbot.

- fuzzywuzzy: The fuzzywuzzy library is used to perform fuzzy matching of user queries with questions in the dataset. It calculates similarity scores to find the best matching question.

- nltk: The Natural Language Toolkit (NLTK) is used for tokenizing the user input.

  ## Custom Dataset
  - The code assumes you have a custom dataset stored in a CSV file, which includes questions and corresponding answers. The dataset is loaded into memory as a dictionary.
 
  ## Function Explanation
- load_custom_dataset(filename): This function loads the custom dataset from a CSV file. It uses Pandas to read the CSV, and it populates a dictionary where the questions are keys, and the answers are values.

- chatbot_response(user_input): This function takes user input, processes it, and returns a response. It does the following:

- Converts user input to lowercase.
- Tokenizes the user input using NLTK.
- Calculates fuzzy match scores between the user input and dataset questions. It keeps track of the best match.
- If the best match score is above a certain threshold (51 in this case), it returns the corresponding answer from the dataset.
- If no good match is found in the dataset, it uses spaCy to extract named entities (e.g., names) from the user input. If it finds a named entity of type "PERSON," it constructs a response indicating that the chatbot knows the name.
- If no match or named entity is found, it returns a default response.

## Web Application
The code defines a Flask web application with two routes:

- /: This is the home page where the chatbot interface is displayed. It uses an HTML template named "index.html."

- /ask: This route is used for receiving user input via a POST request. It calls the chatbot_response function to generate a response and then renders the response on the home page.

- When a user submits a question through the web interface, the ask() function is called. It passes the user input to the chatbot_response() function, which performs fuzzy matching to find the best-matching question in the dataset. If the match score is above a certain threshold (51 in this code), the corresponding answer is returned. Otherwise, the function uses spaCy to extract named entities from the user input and returns a response based on that.
- The Flask application renders an HTML template that displays the user input and the chatbot response on the home page.


## Link To Access The Chatbot 
- https://chatbotcl.azurewebsites.net/

## Snapshots

![chatbot2](https://github.com/CoderPartha012/ChatBot/assets/104616945/bf44efe8-d656-45a0-a131-0472b45aa977)

