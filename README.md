import openai
import os

openai.api_key = "sk-proj-UCF7Gh3pQ9Xa2ZLw4Rt6VwN8Bd5kJJ1HrQeCsTuVoMiXpAzEnLbYcDfGKFsjWhUoPlRAA"
openai.api_base = os.getenv("OPENAI_API_BASE")

# Call the ChatCompletion endpoint
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {
            "role": "system", "content": "You are a helpful teacher."
        },
        {
            "role": "user", "content": "My name is Professor Quigley."
        },
        {
            "role": "assistant", "content": "Hello Professor Quigley. How can I help?"
        },
        {
            "role": "user", "content": "What is my name?"
        }
    ]
)

# Extract the response
print(response.choices[0].message["content"])
