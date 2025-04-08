### **🧠 Project: Build Your Own AI Chatbot with Groq API! 🤖**  

![Groq Logo](https://cdn.asp.events/CLIENT_Informa__AADDE28D_5056_B739_5481D63BF875B0DF/sites/ai-summit-NY-2022/media/libraries/exhibitors/0b84f0a6-3bbd-11ee-bff906bd0f937899-cover-image.png/fit-in/1500x9999/filters:no_upscale())  

In this project, we will bring **artificial intelligence to life** by creating a chatbot powered by the **Groq API**. This chatbot will respond to user messages in real time using advanced AI models! Instead of a graphical interface, we’re keeping it sleek and **console-based**—just like real-world API integrations.  

## **🛠️ Step 1: Get Your API Key**  
Before we start coding, you'll need access to the **Groq API**. Here’s how to get your key:  

1️⃣ Go to **[Groq’s official website](https://groq.com/)** and create an account.  
2️⃣ Navigate to your **dashboard** and generate an API key.  
3️⃣ Copy the key (keep it secret 🤫) and **paste it into the code** below.  

---

## **🖥️ Step 2: Build Your AI Chatbot**  

Replace `'YOUR API KEY HERE'` with your actual **Groq API key**, then run this script:  

```python
import groq

api_key = "YOUR API KEY HERE"  # Replace with your actual API key

# Initialize Groq API client
client = groq.Client(api_key=api_key)


# Function to get AI response from Groq API
def get_ai_response(user_input):
    try:
        response = client.chat.completions.create(
            model="llama3-8b-8192",
            messages=[{"role": "user", "content": user_input}]
        )
        return response.choices[0].message.content  # Corrected access
    except Exception as error_message:
        return f"Error: {error_message}"


# Main loop for user input
if __name__ == "__main__":
    print("Welcome to your AI chatbot! Type 'exit' to quit.")
    while True:
        user_input = input("\nYou: ")
        if user_input.lower() in ["exit", "quit"]:
            print("\nGoodbye! 👋")
            break
        response = get_ai_response(user_input)
        print("AI:", response)
        with open("groq_responses.txt", 'a') as f:
            f.write("You: " + user_input + "\n\nAI: " + response + "\n\n")
```

### **🛠️ Step 3: Run Your Chatbot!**  
- Open your **IDE or terminal**.  
- Run the script and start chatting with your **AI assistant!**  
- Type `"exit"` or `"quit"` to stop the conversation.  

---

## **🔧 Extra Challenges (Level Up Your Bot!)**  
Want to **supercharge** your chatbot? Try these upgrades:  

✨ **Chat History** – Save all messages to a `.txt` file.  
✨ **Multi-Turn Conversations** – Make the AI remember context!  
✨ **Model Selection** – Let users pick different AI models.  
✨ **Custom Prompts** – Allow users to change the chatbot’s personality!  

---

## **📌 Helpful Resources**  
🔗 [Groq API Documentation](https://console.groq.com/docs/quickstart)  
🐍 [Python Documentation](https://docs.python.org/3/)

## IMPORTANT!
All credits to this project go to **[Mario Zahariev](https://github.com/zahariev-webbersof)**, who was my lecturer during the Programming Fundamentals with Python course in January 2025 at SoftUni.
