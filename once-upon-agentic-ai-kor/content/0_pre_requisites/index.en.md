---
title: "🐉 Chapter 0: An Unexpected Adventure"
weight: 1
---

![Header Image](/static/images/header_0.jpeg)

## What is Strands?

[Strands](https://strandsagents.com/latest/) is an Open Source Python SDK designed to simplify the creation of AI agents and multi-agent systems. Built with developer experience in mind, Strands provides an intuitive framework for building sophisticated AI applications that can interact with various tools, APIs, and services.

### What Makes Strands Special?

- **Agent-First Design**: Create intelligent agents that can reason, plan, and execute complex tasks
- **Tool Integration**: Seamlessly connect your agents to external APIs, databases, and services
- **Multi-Agent Orchestration**: Build systems where multiple agents collaborate to solve complex problems
- **Model Flexibility**: Support for various LLM providers including Amazon Bedrock, OpenAI, and more
- **Production Ready**: Built-in error handling, logging, and monitoring capabilities

### What You'll Learn

In this workshop, you'll discover how to harness the power of Strands to build everything from simple chatbots to complex multi-agent systems. We'll start with the basics and gradually work our way up to advanced patterns and integrations.

Ready to begin your journey? Let's set up your development environment!

## Setting Up Your Sanctum (Installation)

**Step 1: Create Your Magical Environment**

```bash
# Clone the workshop repository
git clone https://github.com/aws-samples/sample-once-upon-agentic-ai.git
cd sample-once-upon-agentic-ai
```

**Step 2: Install the Required Enchantments**

[Install uv if you don't have it](https://docs.astral.sh/uv/getting-started/installation/#standalone-installer)

```bash
# Install all workshop dependencies and sync the environment
uv sync
```

Your venv should activate automatically but in case it doesn't, run the following command:

```bash
source .venv/bin/activate  # On macOS/Linux
# or
.venv\Scripts\activate     # On Windows
```

**Step 3: Configure Your Model Provider (optional)** 

By default, Strands will use Claude 4.0 sonnet. If you want to change the [model](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/model-providers/amazon-bedrock/), create a `.env` file at the root of your project and set a MODEL_ID variable to your prefered model.

```bash
MODEL_ID=us.anthropic.claude-sonnet-4-20250514-v1:0
```

Ensure you have proper credentials configured for your chosen provider. Check the [Strands documentation](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/model-providers/amazon-bedrock/) for setup instructions.

## AWS 
If you are running this workshop in an AWS event, an AWS account will be provisioned for you.

To get started, go to AWS Console. Go to Amazon Bedrock console and on left menu, click on **Model access**:

![Header Image](/static/images/modelAccess.png)

On the Model access screen, on top right, click on the button **"Enable specific models"**:

![Header Image](/static/images/enableSpecificModel.png)


On model access screen, select **only** the following models and click on **"Next"** button:

**Anthropic**
* Claude 3.5 Haiku
* Claude 3.5 Sonnet
* Claude 3.7 Sonnet
* Claude 4.0 Sonnet
* Nova 1.0
* _...and any other models you would like to try_

A "Review and submit" screen will appear, review selected models, review Terms, and click on Submit:

![Header Image](/static/images/modelSubmit.png)