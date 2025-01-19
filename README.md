# Support Ticket Classification System

<img width="1409" alt="Screenshot 2024-08-11 at 4 34 42 PM" src="Screenshot 2024-08-18 at 3.55.16 PM.png">


## Description
This project is a machine learning-based support ticket classification system designed to categorize customer queries into predefined categories, including:
- **Login Issues**
- **App Functionality**
- **Billing**
- **Account Management**
- **Performance Issues**

The system leverages:
1. **Sentence Transformers** for embedding-based retrieval.
2. **Llama 3.1 model** for generative classification.

It features a user-friendly Gradio interface for inputting support tickets and ensures irrelevant or out-of-scope queries are handled gracefully with a custom fallback message. This prevents model hallucinations and provides accurate responses.

## Features
- Embedding-based retrieval using Sentence Transformers.
- Generative classification with the Llama 3.1 model.
- Handles out-of-scope queries with a fallback message.
- Intuitive Gradio-based user interface with custom styling.

## Installation
### Prerequisites
- Python 3.9 or later
- Required Python libraries:
  - gradio
  - torch
  - nltk
  - sentence-transformers
  - ollama

### Setup
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```
2. Create a virtual environment:
   ```bash
   python -m venv myenv
   source myenv/bin/activate # For Linux/MacOS
   myenv\Scripts\activate   # For Windows
   ```
3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Ensure you have the necessary model files and libraries installed.

## Usage
1. Launch the Gradio interface by running:
   ```bash
   python main.py
   ```
2. Open the Gradio interface in your web browser (a link will be provided in the terminal).
3. Enter a support ticket in the text box.
4. View the classification result provided by the system.

## Components
### 1. Knowledge Base
The system uses a predefined knowledge base of categories with descriptions:
- **Login Issues**: Problems like incorrect passwords or account lockouts.
- **App Functionality**: Issues like app crashes or device incompatibility.
- **Billing**: Errors such as duplicate transactions or discrepancies.
- **Account Management**: Tasks like updating profiles or linking social media.
- **Performance Issues**: Issues related to network connectivity or device specifications.
- **Fallback Message**: "It looks like I don’t have the relevant information you’re looking for. For further assistance, please contact our support team directly at techsupport@company.com."

### 2. Classification Function
The `classify_ticket` function:
- Retrieves relevant information using Sentence Transformers.
- Evaluates query similarity against the knowledge base.
- Uses the Llama 3.1 model for classification when similarity is above the threshold.

### 3. Gradio Interface
The interface includes:
- A text box for ticket input.
- Customized styles for a user-friendly experience.
- Clear output display of the classification result.

## Customization
### Gradio Styling
The interface's appearance can be customized using the embedded CSS in the `iface` definition. Modify styles like background, fonts, and buttons to suit your branding.

## Example
1. Input a support ticket: "My app keeps crashing whenever I try to open it."
2. The system retrieves relevant information and classifies it as **App Functionality**.
3. If the input is out of scope, the system provides the fallback message.

## Limitations
- The system relies on the quality and comprehensiveness of the predefined knowledge base.
- Performance depends on the underlying Sentence Transformers and Llama 3.1 model.
- Requires internet access for model execution.

## Author
**Riya Chougule**

## Date
01/18/2025

## License
This project is licensed under the MIT License. See `LICENSE` for details.

## Acknowledgments
- [Sentence Transformers](https://www.sbert.net/)
- [Gradio](https://gradio.app/)
- [Llama Models](https://ollama.ai/)
- Background image source: [GetZephyr](https://www.getzephyr.com)

