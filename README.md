# Ai-agent-playground
this my ai agent playbook,it contains my journey from beginner to professional ai agent administrator.
here is the code lines in python odef detect_intent(message):
    if "price" in message:
        return "sales"
    elif "help" in message:
        return "support"
    else:
        return "general"


def generate_reply(intent):
    replies = {
        "sales": "Our prices start from ₦20,000.",
        "support": "Please explain your issue, I’m here to help.",
        "general": "Hello! How may I assist you today?"
    }
    return replies[intent]


def save_conversation(user_message, agent_reply):
    with open("chat_log.txt", "a") as file:
        file.write(f"User: {user_message}\n")
        file.write(f"Agent: {agent_reply}\n\n")


while True:
    message = input("Customer: ").lower()

    if message == "exit":
        print("Agent: Goodbye!")
        break

    intent = detect_intent(message)
    reply = generate_reply(intent)

    save_conversation(message, reply)
    print("Agent:", reply)f my automated agent

