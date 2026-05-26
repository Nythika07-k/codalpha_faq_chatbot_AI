# codalpha_faq_chatbot_AI

# Install first:
# pip install wikipedia

import wikipedia

print("===== AI CHATBOT =====")
print("Ask anything! Type exit to quit")

while True:

    user = input("You: ")

    if user.lower() == "exit":
        print("Chatbot: Goodbye!")
        break

    try:
        # Search related topics
        topics = wikipedia.search(user)

        if len(topics) > 0:
            topic = topics[0]

            response = wikipedia.summary(
                topic,
                sentences=3,
                auto_suggest=True
            )

            print("Chatbot:", response)

        else:
            print("Chatbot: I couldn't find an answer.")

    except wikipedia.exceptions.DisambiguationError as e:
        print("Chatbot: Multiple results found:", e.options[:5])

    except wikipedia.exceptions.PageError:
        print("Chatbot: No matching page found.")

    except Exception as e:
        print("Chatbot Error:", e)
