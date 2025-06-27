
# OpenAI-Agents-SDK-40-Essential-Documentation-Based-Q-A

**Prepared by:** Ameer Hamza  
**Roll No:** 404642  
**Class:** Saturday Evening  
**Email:** ameerhamza94572@gmail.com  

---

## ᵍ Introduction

This document contains my research-based answers to important foundational and intermediate-level questions related to the OpenAI Agents SDK. The goal of this self-assigned exercise was to explore the official documentation thoroughly and solidify my understanding of the key components, behaviors, and tools provided by the SDK.
---

## ✅ Questions & Answers

1. **What’s the main advantage of custom tool behavior functions?**  
   They provide fine-grained control over how and when tools are invoked during an agent run.

2. **Which method is used to execute an agent asynchronously?**  
   `await runner.run()`

3. **What’s the purpose of RunContextWrapper?**  
   It wraps the run context to allow dynamic access and mutation of internal agent state.

4. **What does Runner.run_sync() do?**  
   Executes the agent in a synchronous (blocking) manner.

5. **What does extra="forbid" do in a Pydantic model config?**  
   It prevents any extra fields that are not defined in the model schema.

6. **What's the main advantage of strict schemas over non-strict?**  
   They prevent schema drift and enforce predictable input/output.

7. **What happens when you combine StopAtTools with multiple tool names?**  
   The agent run stops once any of the specified tools are invoked.

8. **What is the purpose of context in the OpenAI Agents SDK?**  
   It stores shared memory or state between tools, messages, and agent runs.

9. **What's the key consideration when choosing between different tool_use_behavior modes?**  
   Balance between performance and flexibility.

10. **What information does handoff_description provide?**  
    A short description of what the tool does or expects.

11. **What does ToolsToFinalOutputResult.is_final_output indicate?**  
    Whether the agent should stop and return the result as final output.

12. **What’s the difference between hosted tools and function tools in terms of tool_use_behavior?**  
    Function tools are local functions, hosted tools are external services.

13. **How do you convert an agent into a tool for other agents?**  
    Wrap the agent using `as_tool()`.

14. **What method returns all tools available to an agent?**  
    `agent.tools`

15. **What is the first parameter of every function tool?**  
    `context`

16. **What is the purpose of the get_system_prompt() method?**  
    It returns the system-level instruction string.

17. **What’s the difference between InputGuardrail and OutputGuardrail?**  
    InputGuardrail filters inputs; OutputGuardrail validates outputs.

18. **What is the primary purpose of the instructions parameter in an Agent?**  
    To guide the agent’s overall behavior via system prompt.

19. **What does the reset_tool_choice parameter control?**  
    Allows re-selection of tools after a run step.

20. **What happens if a function tool raises an exception?**  
    It's captured in logs and can be handled or retried.

21. **What does the clone() method do?**  
    Creates a deep copy of the agent or runner.

22. **What is ToolsToFinalOutputFunction in the OpenAI Agents SDK?**  
    A function that converts tool results into final output.

23. **What is the return type of Runner.run()?**  
    `AgentRunResult`

24. **What happens if a custom tool behavior function returns is_final_output=False?**  
    The agent continues reasoning and may call more tools.

25. **When would you use StopAtTools instead of stop_on_first_tool?**  
    When you want to stop on specific tools, not just the first one.

26. **What is the default value for tool_use_behavior in an Agent?**  
    `auto`

27. **What’s the key difference between run_llm_again and stop_on_first_tool in terms of performance?**  
    stop_on_first_tool is faster but less flexible.

28. **Which Pydantic v2 decorator is used for field validation?**  
    `@field_validator`

29. **What is the purpose of model_settings in an Agent?**  
    To configure generation parameters like temperature.

30. **How do you enable non-strict mode for flexible schemas?**  
    Use `extra="allow"` or `ConfigDict(extra="allow")`

31. **What does the handoff_description parameter do?**  
    Describes the tool's purpose during a handoff.

32. **How do you implement schema evolution while maintaining backward compatibility?**  
    Use optional fields and set defaults for new ones.

33. **Can dynamic instructions be async functions?**  
    Yes.

34. **What happens when tool_use_behavior is set to 'stop_on_first_tool'?**  
    The agent stops reasoning right after the first tool call.

35. **What’s the difference between mutable and immutable context patterns?**  
    Mutable allows in-place updates; immutable does not.

36. **What causes the error 'additionalProperties should not be set for object types'?**  
    The schema is strict but received unknown fields.

37. **When should you use non-strict schemas over strict schemas?**  
    When dealing with dynamic or evolving input.

38. **In a custom tool behavior function, what parameters does it receive?**  
    `tools`, `step`, `context`, `tool_call_args`

39. **What does Runner.run_streamed() return?**  
    An async generator yielding real-time outputs.

40. **How do you create dynamic instructions that change based on context?**  
    Use a (async) function as instructions that reads from context.

---

**Prepared with effort and curiosity.**  
– Ameer Hamza (Roll No: 404642)
