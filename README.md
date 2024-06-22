
# Running Local LLM Models on Docker

## Running Local LLM models on Docker 🦙 - Watch Video

[![Watch Video](https://youtu.be/j8R8SOgNr3g)](https://youtu.be/j8R8SOgNr3g)

This repository guides you through running local LLM (Large Language Models) models using Docker. By following the steps outlined below, you can set up and interact with LLM models on your local machine.

## Prerequisites
- Docker Desktop installed on your system.
- Basic knowledge of Docker commands and terminal usage.

## Getting Started

### Step 1: Download Docker Desktop
If you don't have Docker Desktop installed, download and install it from the [Docker official website](https://www.docker.com/products/docker-desktop). Follow the installation instructions for your operating system.

### Step 2: Update Package Database
Open your terminal or command prompt and update the package database:

```bash
apt-get update
```

### Step 3: Install Required Modules
Install the required modules:

```bash
apt-get install <module>
```

### Step 4: Pull the Ollama Image
Search for the Ollama image on Docker Hub and pull it:

```bash
docker pull ollama/ollama
```

### Step 5: Run the Ollama Image
After pulling the image, run a container from the image:

```bash
docker run -it ollama/ollama
```

### Step 6: Access the Container Terminal
To interact with the container, you need to access its terminal. Open a new terminal and run:

```bash
docker exec -it <container_id> /bin/bash
```
Replace `<container_id>` with the actual container ID or name.

### Step 7: Download the LLM Models
Inside the container terminal, you can download the desired LLM models using the following command:

```bash
ollama pull <model_name>
```
Replace `<model_name>` with the name of the model you wish to download.

## Running the Models

### Step 1: Run the Llama3 Model
To run the Llama3 model, use the following command inside the container terminal:

```bash
ollama run llama3
```

### Step 2: Run the Mistral Model
To run the Mistral model, use the following command inside the container terminal:

```bash
ollama run mistral
```

### Step 3: Making API Calls
You can also make API calls to the models using the `curl` command as shown below:

#### Example for Llama3:
```bash
curl http://localhost:11434/api/chat -d '{
  "model": "llama3",
  "messages": [
    { "role": "user", "content": "why is the sky blue?" }
  ],
  "stream": false
}'
```

#### Example for Mistral:
```bash
curl http://localhost:11434/api/chat -d '{
  "model": "mistral",
  "messages": [
    { "role": "user", "content": "What is NBA?" }
  ],
  "stream": false
}'
```

## Example Outputs

### Llama3
**Prompt:** "What is NBA?"  
**Response:**
```
The NBA!

The National Basketball Association (NBA) is a professional basketball league in North America, comprising 30 teams from the United States and Canada. It is one of the four major professional sports leagues in North 
America, along with the NFL, MLB, and NHL.

Here's a brief overview:

**History:** The NBA was founded on June 6, 1946, as the Basketball Association of America (BAA). It merged with the National Basketball League (NBL) in 1949 to form the modern NBA.

**Structure:** The league is divided into two conferences: the Western Conference and the Eastern Conference. Each conference has three divisions, with five teams in each division. Teams play a regular season schedule 
of 82 games, followed by playoffs to determine the champion.

**Gameplay:** A standard NBA game consists of four quarters, each lasting 12 minutes in professional games and 8-10 minutes in college or high school games. The objective is to score more points than the opposing team 
by shooting the ball into the opponent's basket.

**Notable teams:**

1. Los Angeles Lakers
2. Boston Celtics (most successful franchise with 17 championships)
3. Golden State Warriors (recently dominant team with three titles in five years)
4. Chicago Bulls (famous for their 1990s dynasty led by Michael Jordan)

**Famous players:** Some of the most iconic NBA players include:

1. Kareem Abdul-Jabbar
2. Magic Johnson
3. Larry Bird
4. Michael Jordan
5. Kobe Bryant
6. LeBron James

The NBA has become a global phenomenon, with games and highlights broadcast worldwide. Its popularity stems from its fast-paced, high-flying action, as well as the personalities of its players.

That's a brief introduction to the NBA!
```

### Mistral
**Prompt:** "What is NBA?"  
**Response:**
```
The NBA, or National Basketball Association, is a professional basketball league in North America. It was founded in 1946 as the Basketball Association of America (BAA) and changed its name to the National Basketball 
League (NBL) for one season before becoming the National Basketball Association in 1949. The NBA consists of 30 teams, with 29 in the United States and 1 in Canada. It is the premier men's professional basketball 
league in the world. Teams play an 82-game regular season from October to April, followed by a postseason that culminates with the NBA Finals, where the champions of the Eastern Conference and Western Conference 
compete for the championship title. Some of the most famous NBA players include Michael Jordan, LeBron James, Kareem Abdul-Jabbar, Magic Johnson, Wilt Chamberlain, and many others. The NBA has a global fan base and is 
known for its high level of athleticism, fast pace, and entertainment value.
```

## Comparison
Pass the same prompts to both models to compare their performance and outputs.
