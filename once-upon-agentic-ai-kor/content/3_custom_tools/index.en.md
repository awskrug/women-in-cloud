---
title: "🔨 Chapter 3: The Art of Magical Forging - Creating Custom Tools"
weight: 30
---

![Header Image](/static/images/header_3.png)

_"Every great adventurer forges their own weapons..."_

Welcome to the mystical forge, brave artisan! In this chapter, you'll learn the ancient art of creating your own magical tools. While the built-in tools we have seen previously are powerful, true masters forge their own enchantments for specific quests, this is what we call: **Custom tools**.

## 🎯 Quest Objective

Master the art of custom tool creation by forging the legendary **Dice of Destiny** - an essential tool for any self-respecting Dungeon Master. You'll transform a simple dice roll function in `3_custom_tools/agent_with_dice_roll_tool.py` into a magical tool that your agent can invoke.

## 🔮 The Philosophy of Custom Tools

In Strands, a custom tool is nothing more than a Python function blessed with special enchantments:

- **🎭 The `@tool` Decorator**: The magical rune that transforms an ordinary function into an agent tool
- **📜 The Sacred Docstring**: The description that guides the agent on when and how to use the tool

## 📜 The Sacred Steps

### Step 1: Import the Sacred Tool Magic 📚
**TODO**: Import `tool` from strands to use the `@tool` decorator

Before you can forge any custom tools, you must first import the sacred `@tool` decorator from the Strands library. Look at this example in the [documentation](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/tools_overview/#building-loading-tools) to help you on this quest.

### Step 2: Invoke the Transformation Rune 🪄
**TODO**: Add the decorator to transform your function into a tool

The `@tool` decorator is the incantation that transforms an ordinary Python function into a tool that your agent can automatically discover and use. Link to the [documentation](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/tools_overview/#building-loading-tools).


### Step 3: Write the Documentation Grimoire 📚
**TODO**: Modify the docstring with information about arguments and return value

The docstring isn't just simple documentation - it's the instruction manual that your agent uses to understand the tool.

Here are the [tool design best practices documentation](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/tools_overview/#tool-design-best-practices).

**Tips:** LLMs are generally really good at creating docstrings for agents. Give them the function you want to transform as a tool and an example of tool design best practices and see what it generates.

### Step 4: Equip Your Agent with the Tool ⚔️
**TODO**: Add the tool to the agent

Once your tool is forged, you must equip your agent with it

**Why this matters:**
- The agent can only use tools that are explicitly provided in the `tools=[]` list
- Without this step, your perfectly crafted tool remains unused
- The agent automatically discovers and learns how to use all provided tools

## 🎲 The Challenge: Lady Luck and Ability Scores

Your agent **Lady Luck** will be challenged with a complex D&D character creation quest:

**The Quest**: "Help me create a new D&D character! Roll the strength, wisdom, charisma and intelligence abilities scores using 4d6 drop lowest method."

**What your agent must accomplish:**
1. **Understand** the traditional 4d6 drop lowest method
2. **Use** the `roll_dice` tool repeatedly and intelligently
3. **Calculate** final scores for each ability
4. **Present** results with theatrical flair

Link to the [documentation](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/tools_overview/#building-loading-tools)

## 🔧 Testing Your Creation

Once both TODOs are completed, run your script:

```bash
python agent_with_dice_roll_tool.py
```

Watch Lady Luck in action:
1. **Analyze** the character creation request
2. **Plan** necessary rolls (4 abilities × 4d6 each)
3. **Execute** dice rolls with your custom tool
4. **Calculate** final scores (keep the best 3 dice)
5. **Present** results with theatrical drama

## 🎉 Quest Complete!

Congratulations, Master Forger! You've mastered the ancient art of custom tool creation. Your agent can now use unique capabilities that you've forged specifically for your adventures.

**What you've mastered:**
- ✅ Transforming Python functions into agent tools
- ✅ Writing effective docstrings to guide agents
- ✅ Creating specialized tools for specific domains
- ✅ Integrating custom tools into complex workflows

**Loot Acquired:**
- 🎲 The legendary Dice of Destiny
- 🔨 Custom tool forging skills
- 🎭 An agent with theatrical personality
- 📊 D&D character creation capabilities

**Next Adventure**: Head to Chapter 4 where you'll discover the planar portals of the Model Context Protocol (MCP) and learn to connect your agents to distant realms!

---

_"A tool forged with care is worth a thousand artifacts found by chance!"_ 🔨✨