# AttentiveAI
Provided by <b>AlpacAI</b>

<p align=center>
<img src="https://github.com/zennur/ConversationalAI_SDV/assets/7806017/abd3d0f3-c75c-47e3-ab3c-1b06aa6f8a7d" width="50%"/>
</p>

## Table of Content

- [AttentiveAI](#attentiveai)
  - [Table of Content](#table-of-content)
  - [Problem Statement](#problem-statement)
  - [Vision](#vision)
  - [Future Directions](#future-directions)
  - [Conceptual System Architecture](#conceptual-system-architecture)
  - [Prerequistes](#prerequistes)
  - [Installation](#installation)
  - [Usage](#usage)
  - [License](#license)

## Problem Statement

AttentiveAI represents a cutting-edge integration of AI technologies with automotive safety systems, designed to redefine the driving experience. At its core, AttentiveAI leverages advanced machine learning algorithms, natural language processing, and computer vision to monitor driver attentiveness and provide interactive assistance. By ensuring that drivers remain focused and alert, AttentiveAI aims to significantly reduce the risk of accidents caused by distractions.

## Vision

AttentiveAI aims to gamify driver experience and ensure road safety by embedding intelligence and attentiveness into every journey. By combining AI's predictive capabilities with real-time monitoring and intervention, AttentiveAI not only makes driving safer but also more enjoyable and engaging. It represents a significant step forward in our journey towards fully autonomous vehicles, offering a glimpse into the future of intelligent transportation systems.

## Future Directions
The project envisions expanding its capabilities to include predictive accident avoidance, integration with smart city infrastructure for optimized routing, and enhanced personalization features that adapt to each driver's unique preferences and driving patterns. AttentiveAI is not just a project; it's a commitment to safer, smarter, and more connected driving experiences.

## Conceptual System Architecture

<p align=center>
<img src="doc/architecture.png" width="90%"/>
</p>



## Prerequistes
* Linux Ubuntu 22.04
* `python` > 3.10+
* `gcloud` (See [gcloud installation](https://cloud.google.com/sdk/docs/install?hl=de#deb).)
* `portaudio`  
  ```commandline
  sudo apt install portaudio19-dev python3-all-dev
  ```
## Installation

```shell
# Clone the repository
git clone https://github.com/Bosch-ConnectedExperience-2024/AttentiveAI.git

cd AttentiveAI

# Setup the python virtual environment
python -m venv .venv

# Activate the virtual environment
source .venv/bin/activate

# Install the requirements
(.venv) pip install -r requirements.txt

# Install python package
(.venv) pip install .
```

## Usage

## License

AlpacAI
