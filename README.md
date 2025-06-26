# OpenAI-Agents-SDK-40-Essential-Documentation-Based-Q-A 
Prepared by: Ameer Hamza
Roll No: 404642
Class: Saturday Evening
Email: ameerhamza94572@gmail.com

 Introduction
This document contains my research-based answers to important foundational and intermediate-level questions related to the OpenAI Agents SDK. The goal of this self-assigned exercise was to explore the official documentation thoroughly and solidify my understanding of the key components, behaviors, and tools provided by the SDK.

Each answer is based directly on concepts found in the official documentation and real use cases, not from ChatGPT. The intention is to develop hands-on understanding that will help in future implementation of agentic workflows and collaborative tool-based AI systems.

 Questions & Answers
What’s the main advantage of custom tool behavior functions?
They provide fine-grained control over how and when tools are invoked during an agent run, enabling advanced behaviors like filtering tools dynamically, modifying tool inputs, or customizing final output handling.

Which method is used to execute an agent asynchronously?
await runner.run() — This allows asynchronous execution of the agent's logic.

What’s the purpose of RunContextWrapper?
It wraps the run context to allow dynamic access and mutation of internal agent state during tool calls or run processes.

What does Runner.run_sync() do?
Executes the agent in a synchronous (blocking) manner, ideal when you are not in an async environment.

What does extra="forbid" do in a Pydantic model config?
It prevents any extra fields that are not defined in the model schema, enforcing strict validation.

What's the main advantage of strict schemas over non-strict?
They prevent schema drift and unintended input/output, making the agent’s behavior more predictable and secure.

What happens when you combine StopAtTools with multiple tool names?
The agent run will stop once any of the specified tools are invoked, allowing for multi-stop control flow.

What is the purpose of context in the OpenAI Agents SDK?
It stores shared memory or state between tools, messages, and agent runs — useful for passing data between calls.

What's the key consideration when choosing between different tool_use_behavior modes?
Performance, control flow, and complexity. Some modes give faster responses (stop_on_first_tool), while others offer more flexibility (custom behavior functions).

What information does handoff_description provide?
It gives a short description of what the tool does or expects, often shown in the UI when the agent hands off to a tool.

What does ToolsToFinalOutputResult.is_final_output indicate?
If True, it tells the agent to stop further tool use and return the current result as the final answer.

What’s the difference between hosted tools and function tools in terms of tool_use_behavior?

Function tools are locally defined Python functions.

Hosted tools are external services.
Tool behavior needs to consider availability, latency, and serialization.

How do you convert an agent into a tool for other agents?
Wrap the agent using as_tool() and define its name, description, and input_schema.

What method returns all tools available to an agent?
agent.tools returns the list of tool instances registered with the agent.

What is the first parameter of every function tool?
context — which is an instance of ToolCallContext.

What is the purpose of the get_system_prompt() method?
It returns the system-level instruction string that guides the behavior of the underlying LLM.

What’s the difference between InputGuardrail and OutputGuardrail?

InputGuardrail: Validates/filters inputs before tools run.

OutputGuardrail: Validates/transforms outputs before they’re sent back to the user.

What is the primary purpose of the instructions parameter in an Agent?
To guide the agent’s overall behavior by setting a system prompt for the LLM.

What does the reset_tool_choice parameter control?
If True, the agent can reconsider all tools after a tool run instead of being locked to the same one.

What happens if a function tool raises an exception?
The error is captured in the run logs. The agent can optionally retry or output a fallback response.

What does the clone() method do?
It creates a deep copy of the agent or runner, allowing safe reuse with altered state.

What is ToolsToFinalOutputFunction in the OpenAI Agents SDK?
It’s a special function that transforms tool outputs into the final response of the agent.

What is the return type of Runner.run()?
AgentRunResult, which includes the final message, steps, and execution metadata.

What happens if a custom tool behavior function returns is_final_output=False?
The agent will continue reasoning and possibly call more tools — it doesn’t treat the output as final.

When would you use StopAtTools instead of stop_on_first_tool?
When you want to stop at specific tools rather than the first one used — more targeted stopping logic.

What is the default value for tool_use_behavior in an Agent?
auto, which lets the SDK manage tool selection and stopping automatically.

What’s the key difference between run_llm_again and stop_on_first_tool in terms of performance?
stop_on_first_tool is faster but less flexible. run_llm_again gives the LLM another chance to reason, which may improve accuracy.

Which Pydantic v2 decorator is used for field validation?
@field_validator is used to validate specific fields.

What is the purpose of model_settings in an Agent?
To configure the LLM model’s temperature, context size, and other generation parameters.

How do you enable non-strict mode for flexible schemas?
Use model_config = ConfigDict(extra="allow") in Pydantic v2.

What does the handoff_description parameter do?
It provides a short summary of what the tool does, helping the agent decide how and when to use it.

How do you implement schema evolution while maintaining backward compatibility?
By using optional fields and setting defaults for new fields in the updated schema.

Can dynamic instructions be async functions?
Yes, they can be defined using async def, especially if they depend on external data or context.

What happens when tool_use_behavior is set to 'stop_on_first_tool'?
The agent will halt LLM reasoning immediately after the first tool call is made.

What’s the difference between mutable and immutable context patterns?

Mutable: You can update values during runtime (e.g., context["stage"] = "complete").

Immutable: The context is fixed and must be cloned to modify.

What causes the error 'additionalProperties should not be set for object types'?
It means the schema was declared with extra="forbid" but received unexpected fields.

When should you use non-strict schemas over strict schemas?
When dealing with dynamic, evolving, or user-generated input where flexibility is needed.

In a custom tool behavior function, what parameters does it receive?
It typically receives: tools, step, context, and tool_call_args.

What does Runner.run_streamed() return?
It returns an async generator that yields streamed LLM or tool outputs in real time.

How do you create dynamic instructions that change based on context?
Pass a function or async function to the instructions parameter that reads from context.

