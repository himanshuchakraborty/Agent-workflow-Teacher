# Agent-workflow-Teacher
Agentic workflow - Physics Teacher
The notebook builds a simple AI agent that acts like a physics tutor using Groq as the LLM backend.
The first code cell installs the required libraries such as LangChain, Groq integration, and DuckDuckGo search support.
The second cell imports the main building blocks: ChatGroq for the model, ChatPromptTemplate for prompt construction, SystemMessage for persona instructions, and RunnableWithMessageHistory for conversation memory.
The notebook asks the user to enter a Groq API key securely using getpass, then stores it in the environment variable GROQ_API_KEY.
The @tool decorated function physics_search() wraps DuckDuckGo search so the agent can retrieve online information when needed.
The PhysicsTeacherAgent class encapsulates the agent’s behavior: it initializes the LLM, defines the teaching persona, and builds a prompt chain.
The system message tells the model to act as an expert physics teacher who explains simply, uses formulas, gives examples, and searches online when necessary.
The ChatPromptTemplate.from_messages([...]) object defines the input structure: a system message followed by a human question.
The ask_question() method builds a physics-specific query, invokes the runnable chain, and returns the model’s answer text.
The get_conversation_history() method exposes stored conversation messages, which is the basic memory mechanism used in the notebook.
