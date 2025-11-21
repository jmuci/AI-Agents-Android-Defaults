# AI-Agents-Android-Defaults
AI Context and Rules for AI agents to drop into your Android Project. 
Most of the content is general modern Android best practices and clean code principles; however, some sections are more opinionated (e.g., database choice, using Ktor client, etc), and you will need to adapt them for your project's specific needs.
Drop the AI_CONTEXT and AI AGENTS at the root of your repo, as well as the prompts directory. 

AI agent "rules files" and "prompts" work together to guide an AI's behavior. Prompts are specific instructions given for a single task, while rules files are configuration files that define ongoing instructions, such as coding standards or project-specific knowledge. These files provide the AI with context and guidelines to ensure consistent, high-quality, and project-aligned outputs. 

## Prompts
Purpose: To provide specific, one-off instructions for a particular task.
Content: Includes clear, concise language, a defined persona (e.g., "You are a helpful customer support agent..."), specific goals, and desired outputs or examples.
Examples: A prompt asking the AI to "write a Python function to sort a list of numbers" or "generate a list of project ideas for a mobile app". 
## Rules files (AGENTS)
Purpose: To define consistent, long-term guidelines for the AI across multiple tasks. They are often used to automate recurring instructions or establish project-specific standards.
Content: Can include coding standards, error handling guidelines, project-specific knowledge, and other rules that apply to a specific context or project.
