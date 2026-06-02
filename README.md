 # AGENTS OF JUSTICE 

AI-Driven Autonomous Courtroom Simulation

Agents of Justice is a sophisticated multi-agent simulation system designed to replicate the complexities of a courtroom trial. By leveraging the Groq API for ultra-fast inference with LLaMA (llama3-8b-8192) and orchestrating the trial flow through LangGraph, the system enables autonomous, context-aware interaction between legal personas.
 
## Key FEATURES
- Multi-Agent Ecosystem: Independent agents for the Judge, Defense Lawyer, Prosecution Lawyer, Defendant, Plaintiff, and Witness, each operating under specific legal personas.

- Persistent Context & Memory: Unlike static chatbots, every agent maintains a dynamic memory of the trial. Agents retain awareness of previous testimony, objections, and evidence presented, ensuring coherent, long-term narrative consistency.

- Structured Flow via LangGraph: The trial progression is not linear; it is managed by LangGraph to handle complex decision-making, conditional logic (e.g., handling objections), and procedural sequencing.

- Groq-Powered Performance: Real-time reasoning capabilities allow for fluid, conversational interaction without the latency typical of standard LLM implementations.

-  Customizable Legal Logic: Modular prompt templates allow users to tweak agent behaviors, inject new case files, or alter the legal jurisdiction of the simulation.

- Interactive Gradio UI: A clean, user-friendly web interface for initiating, monitoring, and influencing the courtroom proceedings.


## Architecture & Technical Stack
The system is designed for modularity, separating agent logic from the state-management flow of the trial


Folder Structure
bash
Copy
Edit


courtroom-sim<br>
│
├── agents/                            # Contains agent logic <br>
│   ├── base_agent.py            
│   ├── witness.py           

│
├── config/                            # Stores prompt templates for agents and env<br>
│   └── prompts.py<br>
│   └── env.py<br>
│   └──utils.py


├── trial.py                           # LangGraph flow logic<br>
├── file.py                            # To preprocess the cases.csv file <br>


├── app.py                            # Main entry point with Gradio UI<br>
├── requirements.txt                  # List of dependencies<br>
└── README.md                         # Project documentation<br>

├── processed_data.csv          
├── cases.csv

## Core Components
- Agent Module: The foundation of all characters. Each agent class integrates with the Groq API and manages its own short-term and long-term memory, allowing them to "remember" previous arguments and evidence during the cross-examination process.

-LangGraph Controller (trial.py): Acts as the courtroom clerk and judge. It manages the state of the trial, ensuring that the dialogue follows logical procedural steps and handling transitions between arguments and witness statements.

-Prompt Engine: Located in config/, this layer allows for dynamic injection of legal context. By modifying these templates, you can change a trial from a civil dispute to a criminal proceeding seamlessly.

-Gradio Interface: The main gateway (app.py) provides real-time visibility into the dialogue history and the current state of the simulation.

## IMPLEMENTATION

1. Clone the Repository
"git clone (https://github.com/TechTinkerKetki/Courtroom_Simulator)"

2. Create a Virtual Environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

3. Install Dependencies
pip install -r requirements.txt

4. Add Your Groq API Key
Create a .env file and add the following:
GROQ_API_KEY=your_groq_api_key

5. Run the Application
python app.py


# Scope for Improvement
1. Witness Agent Integration:
Add functionality to introduce a witness during the trial for cross-examination, making the simulation more dynamic.

2. TTS Integration:
    Integrate speech synthesis with gradio with different for for different agents (based on gender) and emotions and tone of the speech based on the roles of the agents.

3. Extended Agent Interactions:
Implement more complex interactions, including objections, evidence presentation, and more nuanced legal dialogue.

Introduce roles for jury members, clerks, and other courtroom personnel.

4. Memory Retention & Context:
Use vector-based memory storage (like FAISS or other vector databases) to store and retrieve long-term conversation context for agents.

5. Better Case Upload/Parsing:
Allow users to upload case files (PDF, DOCX) and parse them into structured data to drive the trial simulation.

### Ketki Patil and Vanshika Gupta
