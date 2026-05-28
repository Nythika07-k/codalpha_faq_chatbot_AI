import datetime
import random


class AIChatBot:

    def __init__(self):

        self.name = "Leo AI Chatbot"

        # Knowledge Base
        self.responses = {

            "what is ai":
            "Artificial Intelligence is the simulation of human intelligence in machines.",

            "what is java":
            "Java is a high-level object-oriented programming language used for developing applications.",

            "what is python":
            "Python is a powerful and easy programming language used in AI, web development, and data science.",

            "what is machine learning":
            "Machine Learning is a branch of AI that allows systems to learn from data automatically.",

            "what is deep learning":
            "Deep Learning is a subset of Machine Learning based on neural networks.",

            "what is nlp":
            "Natural Language Processing enables computers to understand and process human language.",

            "what is computer":
            "A computer is an electronic device that processes data and performs calculations.",

            "who invented computer":
            "Charles Babbage is known as the father of the computer.",

            "what is ram":
            "RAM stands for Random Access Memory used for temporary storage during processing.",

            "what is cpu":
            "CPU stands for Central Processing Unit and is called the brain of the computer.",

            "what is coding":
            "Coding is the process of writing instructions for computers using programming languages.",

            "what is programming":
            "Programming is the process of designing and building software applications.",

            "what is database":
            "A database is an organized collection of data stored electronically.",

            "what is cloud computing":
            "Cloud computing provides computing services over the internet.",

            "what is cybersecurity":
            "Cybersecurity protects systems and networks from digital attacks.",

            "what is data science":
            "Data Science is the study of extracting insights from data.",

            "what is html":
            "HTML is the standard language used to create web pages.",

            "what is css":
            "CSS is used to style and design web pages.",

            "what is javascript":
            "JavaScript is a scripting language used to make web pages interactive."
        }

    # Greeting Function
    def greeting(self):

        greetings = [
            "Hello! How can I help you today?",
            "Hi Friend! Ask me any technical question.",
            "Welcome! I am ready to answer your questions."
        ]

        return random.choice(greetings)

    # Time Function
    def get_time(self):

        current_time = datetime.datetime.now().strftime("%I:%M %p")

        return "Current time is " + current_time

    # Date Function
    def get_date(self):

        today = datetime.date.today()

        return "Today's date is " + str(today)

    # Main Response Function
    def get_response(self, user_input):

        question = user_input.lower()

        # Greetings
        if question in ["hi", "hello", "hey"]:
            return self.greeting()

        # Basic Questions
        elif "how are you" in question:
            return "I am functioning properly and ready to help you."

        elif "your name" in question:
            return "My name is " + self.name

        elif "time" in question:
            return self.get_time()

        elif "date" in question:
            return self.get_date()

        elif "thank you" in question:
            return "You are welcome!"

        # Knowledge Base Matching
        for key in self.responses:

            if key in question:
                return self.responses[key]

        # Default Response
        return (
            "Sorry, I do not have information about that question. "
            "Please ask another technical question."
        )


# Main Program
def main():

    bot = AIChatBot()

    print("=" * 50)
    print("         PROFESSIONAL AI CHATBOT")
    print("=" * 50)
    print("Type 'exit' to quit the chatbot")
    print("=" * 50)

    while True:

        user_input = input("\nYou : ")

        if user_input.lower() == "exit":

            print("\nChatbot : Goodbye! Have a great day.")
            break

        response = bot.get_response(user_input)

        print("\nChatbot :", response)


# Run Program
if __name__ == "__main__":

    main()
