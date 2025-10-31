---
title: "Resource cleanup"
weight: 80
---

![Header Image](/static/images/header_8.png)

To avoid incurring future charges, clean up the resources created during this workshop (if running this workshop in your own AWS account).

## Amazon Bedrock cleanup

Since this workshop primarily uses Amazon Bedrock, no specific cleanup is required for the Bedrock service itself. However, be aware of the following:

1. **Bedrock Model Usage**: Charges are based on usage (input/output tokens). No ongoing charges will occur if you stop using the models.

2. **Bedrock Model Access**: The model access you enabled will remain active but doesn't incur charges unless used.

## Local development cleanup

1. **Stop local servers**: 
   - Stop any running MCP servers (Ctrl+C in terminal)
   - Terminate any local development servers

2. **Clean up temporary files**:
   - Remove any temporary log files created during development
   - Clear any cached model responses if applicable

## Next steps

Now that you've cleaned up your resources, you're ready to apply what you've learned in your own projects.

If you have any questions or need further assistance, refer to the [Strands Agents documentation](https://strandsagents.com/latest/documentation/docs/) or reach out to the workshop facilitators.