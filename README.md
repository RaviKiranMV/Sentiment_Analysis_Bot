# Sentiment Analysis Chatbot :
* This project is a simple sentiment analysis chatbot that uses Python's NLTK and TextBlob libraries to analyze the sentiment of user inputs and respond accordingly.
* The chatbot categorizes the sentiment as positive, negative, or neutral.
* RequirementsBefore running the code, ensure you have the following Python libraries installed: nltk & textblob
* You can install these libraries using pip:
    pip install nltk textblob

# How to Run :
* Save the provided code into a Python file, e.g., sentiment_chatbot.py.
* Open a terminal or command prompt and navigate to the directory containing the sentiment_chatbot.py file.
* Run the script using the following command:python sentiment_chatbot.py
* The chatbot will start and greet you with "Chatbot: Hi! How can I assist you today?".
* You can type your input, and the chatbot will analyze the sentiment and respond with "Positive", "Negative", or "Neutral".
* To exit the chatbot, type exit.
  
# Code Explaination :
* Import Libraries
    import nltk
    from textblob import TextBlob

* nltk : Natural Language Toolkit for text processing.
* TextBlob : Library for processing textual data, providing an easy-to-use API for NLP tasks.
* Download NLTK Data :
    nltk.download('punkt')
* Downloads the necessary NLTK data for tokenization.

# Preprocess the Text:
    def preprocess_text(text):
        words = nltk.word_tokenize(text)
        words = [word.lower() for word in words if word.isalnum()]
        return " ".join(words)
* Tokenizes the input text into words.
* Converts all words to lowercase and removes non-alphanumeric characters.
* Joins the processed words back into a single string.

# Get Sentiment :
    def get_sentiment(text):
        text = preprocess_text(text)
        analysis = TextBlob(text)
        if analysis.sentiment.polarity &gt; 0:
            return "+ve"
        elif analysis.sentiment.polarity &lt; 0:
            return "-ve"
        else:
            return "neutral"
* Uses TextBlob to analyze the sentiment of the preprocessed text.
* Returns "+ve" for positive sentiment, "-ve" for negative sentiment, and "neutral" for neutral sentiment.
  
# Chatbot Interaction :
    def chatbot():
        print("Chatbot: Hi! How can I assist you today?")
    
        while True:
            text_input = input("You: ")
        
            if text_input.lower() == "exit":
                print("Chatbot: Goodbye!")
                break
        
            sentiment = get_sentiment(text_input)
        
            if sentiment == "+ve":
                print("Chatbot: Positive")
            elif sentiment == "-ve":
                print("Chatbot: Negative")
            else:
                print("Chatbot: Neutral")
* Greets the user and enters an infinite loop to interact with them.
* Takes user input and exits if the input is "exit".
* Analyzes the sentiment of the input and prints whether it is positive, negative, or neutral.
  
# Start the Chatbot : 
    chatbot() 
* Calls the chatbot function to start the chatbot.

# Example Interaction : 
    Chatbot: Hi! How can I assist you today?
    You: I love programming!
    Chatbot: Positive
    You: This is too difficult.
    Chatbot: Negative
    You: I have no opinion on this.
    Chatbot: Neutral
    You: exit
    Chatbot: Goodbye!

# Notes :
* The chatbot uses basic preprocessing and sentiment analysis. 
* For more advanced applications, consider improving text preprocessing and using more sophisticated sentiment analysis techniques.
* This chatbot is designed for educational purposes to demonstrate basic sentiment analysis using Python.
