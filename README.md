# 🟦🟨🟥 Tetris AI 🟥🟨🟦

A Tetris game developed in **Python and Pygame** with an integrated **Machine Learning model** capable of learning gameplay strategies from recorded human plays and using them to make decisions during the game.

This project was developed collaboratively as part of a Computer Science project by the **Naige's Bots Team**.

## 📌 About the Project

**Tetris AI** combines a classic Tetris implementation with a Machine Learning component designed to learn from gameplay data.

The project provides two main game modes:

* 🎮 **Manual Mode** — Allows the user to play Tetris using keyboard controls.
* 🤖 **AI Mode** — Allows the trained model to play automatically based on the current board state and available pieces.

The Machine Learning component is trained using a dataset generated from approximately **20,000 records of human gameplay**, allowing the model to identify patterns and strategies used during real games.

## ✨ Features

* 🎮 Classic Tetris gameplay
* 🤖 Machine Learning-based automatic gameplay
* 📊 Training data generated from human gameplay
* 🗄️ SQLite database for storing gameplay data
* 📈 Data visualization and graph generation
* 🎵 Audio assets and game sound effects
* 🖼️ Graphical interface developed with Pygame
* 🧩 Modular project structure separating game logic, services, models, and supporting resources

## 🎲 How the Game Works

In the manual game mode, Tetris pieces fall onto the game board and the player must position them to complete horizontal rows.

When a complete row is formed, it is cleared and the player receives points. The game continues until there is no available space for a new piece.

The game can be accessed through the **Start** option in the main menu.

### 🎮 Controls

| Key            | Action                                        |
| -------------- | --------------------------------------------- |
| ⬅️ Left Arrow  | Move piece left                               |
| ➡️ Right Arrow | Move piece right                              |
| ⬇️ Down Arrow  | Move piece down                               |
| ⬆️ Up Arrow    | Rotate piece                                  |
| `C`            | Hold current piece                            |
| `Space`        | Drop piece                                    |
| `Esc`          | Exit / return depending on the current screen |

> **Note:** Controls may depend on the current implementation and game state.

## 🤖 How the AI Works

The AI component uses gameplay data collected from human players to learn how to make decisions during a Tetris game.

The general process is:

```text
Human Gameplay
      ↓
Gameplay Data
      ↓
Data Storage
      ↓
Data Processing
      ↓
Model Training
      ↓
Trained Machine Learning Model
      ↓
Current Game State
      ↓
AI Decision
      ↓
Tetris Action
```

The model uses information about the current board and available pieces to determine an appropriate action.

The trained model can then be accessed through the **Auto-Play** option in the main application.

## 🧠 Machine Learning Pipeline

The Machine Learning component can be understood as four main stages:

### 1. Data Collection

Gameplay information is collected from human players while they interact with the Tetris game.

The resulting dataset contains approximately **20,000 gameplay records**.

### 2. Data Storage

Gameplay records are stored in the project's database:

```text
tetris.db
```

This allows the collected information to be reused during the model training process.

### 3. Model Training

The training process is handled through:

```text
train_model.py
```

This module uses the collected gameplay information to train the Machine Learning model.

### 4. AI Gameplay

Once trained, the model can be used by the game to make decisions automatically.

The AI receives information about the current game state and uses the learned patterns to select an action.

## 🏗️ Project Structure

```text
Test-Tetris/
│
├── assets/
│   └── audio/
│       └── Game audio resources
│
├── fonts/
│   └── Fonts used by the interface
│
├── images/
│   └── Images and graphical resources
│
├── models/
│   └── Machine Learning models
│
├── services/
│   └── Supporting services and application logic
│
├── .gitignore
│
├── TetrisEngine.py
│   └── Core Tetris game engine
│
├── main.py
│   └── Main application and graphical interface
│
├── graphs.py
│   └── Data visualization and graph generation
│
├── train_model.py
│   └── Machine Learning model training
│
├── tetris.db
│   └── Gameplay database
│
└── README.md
    └── Project documentation
```

## 🛠️ Technologies Used

| Technology            | Purpose                                       |
| --------------------- | --------------------------------------------- |
| 🐍 Python             | Main programming language                     |
| 🎮 Pygame             | Game development and graphical interface      |
| 🤖 Machine Learning   | Automated gameplay and pattern learning       |
| 🗄️ SQLite            | Gameplay data storage                         |
| 📊 Data Visualization | Analysis of gameplay and training data        |
| 🔧 Git & GitHub       | Version control and collaborative development |

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/ValeriaNaige/Test-Tetris.git
cd Test-Tetris
```

### 2. Create a virtual environment

It is recommended to use a virtual environment to isolate the project's dependencies.

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

On macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install dependencies

Install the required Python packages according to the project's dependency configuration.

If a `requirements.txt` file is available:

```bash
pip install -r requirements.txt
```

Otherwise, install the required dependencies used by the project, including Pygame and the Machine Learning libraries configured in the source code.

### 4. Run the application

From the project root directory:

```bash
python main.py
```

The Pygame interface should open and display the main menu.

From there, the available game modes can be selected.

## 📊 Data & Visualization

The project includes functionality for analyzing gameplay information and generating visualizations.

The main components involved are:

```text
tetris.db
graphs.py
train_model.py
```

The database provides the gameplay data used by the Machine Learning pipeline, while `graphs.py` supports the analysis and visualization of the collected information.

## 🧪 Working With the Project

When modifying the project, it is recommended to preserve the separation between:

* 🎮 Game engine and gameplay logic
* 🤖 Machine Learning functionality
* 🗄️ Data storage
* 📊 Data analysis
* 🎨 Graphical resources
* 🔊 Audio resources

For changes involving the AI, the general workflow is:

```text
Modify / collect data
        ↓
Verify database records
        ↓
Train or update model
        ↓
Evaluate behavior
        ↓
Integrate model into gameplay
        ↓
Test Auto-Play mode
```

For changes to the game itself, test both **Manual Mode** and **AI Mode** to ensure that changes to the game state do not interfere with the model's inputs or decisions.

## 👩🏻‍💻 My Contribution

As a member of the development team, I contributed to the project across
data management, analysis, documentation, and software development.

### Data & Analysis
- Contributed to the generation and population of the project's gameplay dataset.
- Worked with the database containing approximately 25,000 gameplay records.
- Contributed to the analysis and interpretation of gameplay data.
- Collaborated on the generation and updating of data visualizations.

### Software Development
- Contributed to the implementation and refinement of game logic and project functionality.
- Participated in code review, debugging, and code organization.
- Helped integrate different components of the application during development.

### Documentation
- Designed and updated the project's README and technical documentation.
- Organized project information to improve its structure, usability, and reproducibility.
- Contributed to documenting the project's functionality and workflow.

> My contributions were developed collaboratively with the rest of the team.
> The commit history reflects the changes authored under my GitHub account,
> while additional contributions were made jointly during the development
> and analysis process.

## 👥 Collaborators

The original project was developed by the **Naige's Bots Team**:

* [@Artu-GR](https://github.com/Artu-GR)
* [@An-Isa93](https://github.com/An-Isa93)
* [@ValeriaNaige](https://github.com/ValeriaNaige)
* [@RebecaJara](https://github.com/RebecaJara)
* [@yayo81236](https://github.com/yayo81236)

## 🎯 Learning Objectives

This project provided practical experience in:

* Object-oriented programming with Python
* Game development with Pygame
* Machine Learning applied to interactive systems
* Data collection and preprocessing
* Database management
* Data visualization
* Integration of Machine Learning models into applications
* Collaborative software development
* Version control with Git and GitHub

## 🔗 Original Repository

This repository is a fork of the original team project:

**[An-Isa93/Test-Tetris](https://github.com/An-Isa93/Test-Tetris)**

The original repository contains the team's complete development history and contributions.

---

⭐ *Academic project combining game development, data, and Machine Learning.*
