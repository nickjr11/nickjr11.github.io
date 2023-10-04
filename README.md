import openai

# Replace with your OpenAI API key
api_key = 'your_api_key_here'

# Initialize the OpenAI API client
openai.api_key = api_key

def chat_with_gpt3(prompt):
    response = openai.Completion.create(
        engine="davinci",
        prompt=prompt,
        max_tokens=150  # Adjust the max tokens as needed
    )
    return response.choices[0].text.strip()

# Example conversation
conversation = ""
print("Bot: Hello! How can I assist you today?")
while True:
    user_input = input("You: ")
    conversation += f"You: {user_input}\n"
    response = chat_with_gpt3(conversation)
    print("Bot:", response)
    conversation += f"Bot: {response}\n"

