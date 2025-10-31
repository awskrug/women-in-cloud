---
title: "🎲 Chapter 6: The Grand Tavern - Bringing Your Game Master to Life"
weight: 60
---

![Header Image](/static/images/header_6.png)

_"Every legendary Game Master needs a proper tavern where adventurers can gather..."_

Welcome to the final chapter of your journey, brave architect! You've forged a powerful AI Game Master with custom tools, mystical connections, and agent-to-agent communication. Now it's time to unveil your creation to the world through our enchanted web interface.

## 🎯 Quest Objective

Test your local Game Master in real life with our basic web interface

## 🌐 The Mystical Portal: SSH Tunneling

Since your Game Master currently dwells in the local realm of your machine, we need to create a magical bridge to make it accessible from the wider internet. Our web interface requires HTTPS connections for security enchantments, so we'll use SSH tunneling to create this secure passage.

### Step 1: Open the Portal 🚪

In your project folder, cast this incantation to create a secure tunnel:

```bash
ssh -R 80:0.0.0.0:8009 nokey@localhost.run
```

This powerful spell will:

- **Create** a secure tunnel from the internet to your local machine
- **Provide** you with a unique HTTPS URL
- **Redirect** all traffic to your Game Master running on port 8009

You should see something like this mystical response:

![Portal Creation](/static/images/nokey.png)

## 🏛️ The Grand Web Interface

Once your portal is established, venture forth to our enchanted web interface where adventurers can interact with your Game Master:

🌟 [Enter the Digital Tavern](https://aws-samples.github.io/sample-once-upon-agentic-ai/)

This mystical interface provides:

- **🎭 Immersive Chat Experience**: A proper setting for D&D adventures
- **🎲 Real-time Interactions**: Instant communication with your Game Master

### Step 2: Connect Your Game Master 🔗

In the web interface:

1. **Locate** the `Server URL` input field
2. **Enter** the HTTPS URL provided by your SSH tunnel
3. **Click** Connect to establish the mystical link

![Connection Interface](/static/images/ui-home.png)

**📊 Performance Monitoring:**
Watch your terminal for debug logs to see how your Game Master handles requests:

```bash
DEBUG | strands.agent | Processing request from web interface
DEBUG | strands.tools | Using dice_roll tool for ability scores
DEBUG | strands.agent | Response generated in 2.3s
```

**🔧 Customization Options:**

- Modify your Game Master's personality through system prompts
- Add new custom tools for unique campaign mechanics
- Integrate additional MCP servers for expanded capabilities

## 🚨 Troubleshooting Portal Issues

**"Connection Refused" Error:**

- Verify your local agent is running on port 8009
- Check that the SSH tunnel is active
- Ensure no firewall is blocking the connection

**"Invalid Server URL" Message:**

- Confirm you're using the HTTPS URL from the tunnel
- Check for typos in the URL entry
- Try refreshing the tunnel connection

**Slow Response Times:**

- Monitor your local machine's resource usage
- Check your internet connection stability
- Consider optimizing your agent's model configuration

## 🎉 Quest Complete - The Legend Begins!

Congratulations, Master Architect! You've successfully created and deployed an almost fully functional AI Game Master accessible through a beautiful web interface. Your digital tavern is now open for business!

**🌟 The Adventure Continues:**
Your journey in AI agent development has just begun. With these foundational skills, you can now create agents for any domain, integrate them with various services, and deploy them to serve real users.

---

_"And so the student becomes the master, and the code becomes legend. May your agents serve you well in all your digital adventures!"_ 🏰✨
