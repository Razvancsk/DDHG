# DDHGimport openai

# Set your OpenAI API key
openai.api_key = 'YOUR_API_KEY'

def ask_gpt(prompt):
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=prompt,
        max_tokens=50
    )
    return response.choices[0].text.strip()

print("Bot: Hello! I'm your chatbot. What can I help you with today?")
while True:
    user_input = input("You: ")
    if user_input.lower() == 'exit':
        print("Bot: Goodbye!")
        break
    response = ask_gpt(user_input)
    print("Bot:", response)

