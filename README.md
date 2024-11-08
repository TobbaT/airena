# SingularGames (formerly AIrena)

Welcome to SingularGames, where LLMs rival in creativity to produce memorable games. 

**Note:** This project is undergoing a rename to SingularGames. You might still find some files and references to the old name (AIrena) as this transition is in progress.

**Concept:**

The idea is simple: a Referee model is given a prompt explaining the system it evolves in, and another for game-specific rules. The referee then explains these rules to the LLM players, and they start playing! ...Usually.  This framework allows for a wide variety of games and interactions, pushing the boundaries of what LLMs can achieve in creative collaboration. (Gemini might have been a bit overenthusiastic there!)

**Description:**

SingularGames explores the capabilities of AI in understanding and participating in structured game formats. This project is a fun experiment, designed for flexibility. You can easily create custom game-specific prompts (see the examples in the `prompts` folder) using plain text or markdown (just suggestions : anything the LLM Referee understands goes). 

**Current Status:**

SingularGames can currently run games with 2 LLM players and a referee. The complexity of the games that can be run largely depends on the capabilities of the referee model.

* **Successful Implementations:**  Simple games like 20 Questions run smoothly.
* **Ongoing Challenges:** More complex games, such as the story co-building game, have encountered issues with scoring, but the core gameplay functions as intended.

**Roadmap:**

* **Empower the Referee:**
    * Provide the referee with tools to better manage and interact with the game.
    * Enable the referee to check out the rules folder and files itself, enabling user to prompt the referee for games in natural language and enabling the referee to adapt them based on that description (eg. 20 questions game themed around LLMs)
* **Flexible Player Management:**
    * Allow the referee to create new players during a game. This will increase flexibility and enable games with a variable number of participants.

**Requirements:**

* Python 3.8 or higher
* pip , a python package manager 
* An OpenAI API key
* A Google GenAI API key

**Important Note on API Usage:**

SingularGames utilizes both OpenAI and Google GenAI APIs.  Please be aware that running this project will consume API tokens and may result in charges on your accounts.  

* **OpenAI:** [https://www.openai.com/](https://www.openai.com/)
* **Google GenAI:** [https://aistudio.google.com/welcome](https://aistudio.google.com/welcome)

While the project currently requires both keys, the use of Langchain allows for adaptation.  Users with some technical knowledge can easily modify the constructors in `run_arena.py` to utilize different language models. Keep in mind that the project makes a fair amount of API calls with substantial context, which can impact cost.

**Installation:**

1. **Clone the repository:**

   ```bash
   git clone https://github.com/TobbaT/airena.git
   ```

2. **Set up the environment:**

First, rename .env.example to .env and set up your actual keys

   ```bash
   mv .env.example .env # Put your API keys in this file 
   ```
Then set up the virtual environment.

   ```bash
   source setup.sh # This will set up a python venv, and source your .env file as well as load dependencies from requirements.txt
   ```

**Usage:**

   ```bash
   python3 run_arena.py -game "20Questions.txt"
   ```

You can select different game rules by specifying a different file from the prompts folder. You can also add your own Game files to that folder and select them.

The game will be displayed in console, and logged in a file under the outputs folder.

**Contributing:**

Contributions are welcome! Feel free to open issues, submit pull requests, or suggest new game ideas.

**License:**

This project is licensed under the MIT License - see the LICENSE file for details.