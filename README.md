# Fuzzy Matching Transaction Descriptors to Merchants
Submitted by: Rishabh (Rish) Kaushick <br>
Program: Master of Science in Information Systems <br>
Course: CSYE 7230 - Software Engineering & Generative Artificial Intelligence <br>
Term: Spring 2025 <br>
Supervised by: Prof. Junwei Huang

# Problem Statement
Large finanacial organizations have difficulty matching merchant descriptors to individual merchants. 

Take the following examples:

| Messy Merchant Descriptor    | Messy Merchant Name      | Match?      |
|------------------------------|--------------------------|-------------|
| AMZN Mktp CA*UC33G8423       | Amazon Marketplace       | ✅ MATCH    | 
| NETFLX#999-USA               | NetFlex Gym USA          | 🚫 MISMATCH | 

## Current Process

```mermaid
flowchart LR
  A[/Messy Merchant Descriptor/] e1@==> B@{ shape: processes, label: "Very Large Rule Based Algorithm" }
  B e2@==> C[/Messy Merchant Name/]
  e1@{ animate: true }
  e2@{ animate: true}
```

Sometimes the very large rule based algorithm could correctly guess the merchant name from the merchant descriptor - like the Amazon example above. However, sometimes it could make mistakes such as the second example.

Therefore given a pair of merchant descriptor and merchant name, can we classify whether the current process correctly identified the merchant? (MATCH condition) Or is it possible that it guessed the merchant wrongly? (MISMATCH)

Apart from traditional machine learning approaches, this project seeks to explore whether LLMs, with their emergent abilities, can solve this classification probelm better.

# How to Run The Project
## Setup OpenAI API Key & Google Gemini API Key
First let's setup the API key in our environment variable from the terminal.

### MacOS Setup
1. Run the following (after changing YourAPIKeyHere):
    ```bash
    echo "export OPENAI_API_KEY='YourAPIKeyHere'" >> ~/.zshrc
    echo "export GEMINI_API_KEY='YourAPIKeyHere'" >> ~/.zshrc
    ```
2. Update the shell
    ```bash
    source ~/.zshrc
    ```
3. To confirm the API Key has been setup correctly, we can check it on the terminal as follows:
    ```bash
    echo $OPENAI_API_KEY
    echo $GEMINI_API_KEY
    ```

