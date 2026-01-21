# Prompting Techniques - Examples

A collection of practical prompting examples demonstrating various techniques for effective AI interactions.

---

## 1. Persona-Output-Audience (POA) Prompting

> **Technique:** Combines persona definition, expected output format, and target audience to guide the response.

### Example: Generate Slide Deck from NotebookLLM

```
Create a detailed Slide deck which has brief overview and explanation
of all the prompting techniques explained in the video

[PERSONA] You are a Professional AI Engineer
[OUTPUT] To contain at least 20 slides or pages
[AUDIENCE] Working Software engineers
```

---

## 2. Zero-Shot Prompting

> **Technique:** Direct instruction without examples or step-by-step guidance. Simple and straightforward requests.

### Example: Framework Architecture Overview

```
Explore the project and create architecture of Automation framework on a high level
```

---

## 3. Chain of Thought (COT) Prompting

> **Technique:** Guides the model through a structured thinking process with sequential steps, questions, and iterative refinement.

### Example: Architecture Diagram Generation

```
[TASK] Generate Architecture diagram of this automation framework inside week8 folder

[CONTEXT] You are a test architect and trying to understand the framework

[RULES]
- Do not reveal chain of thoughts

[PROCESS]
1. Ask 3 important questions in regards to create the architecture diagram
2. Wait for my answer before going to the next question
3. Based on my answers generate the architecture diagram according to
   the best industry standards and best practices

[PERSONA] Act as a senior test architect and review the architecture diagram
and make changes if it's not up to the industry standards and doesn't follow best practices
```

---

## 4. Structured Prompting (ICETOP Framework)

> **Technique:** Uses multiple structured elements - **I**nstructions, **C**ontext, **E**xample, **T**one, **O**utput, **P**ersona - for comprehensive guidance.

### Example: Code Review for Junior Developer

**Example:**

```javascript
function isPangram(string) {
  //...
  return new Set(string.toLowerCase().replace(/[^a-z]/g, "")).size === 26;
}
```

| Element          | Description                                                                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Instructions** | Validate the above Given Code and review it. [Include] the best of the best practices and algorithm. [ELI5] with the comments. [TEMPERATURE] 1.3 |
| **Context**      | I am a Junior developer                                                                                                                          |
| **Example**      | Use Data Structures & Algorithm                                                                                                                  |
| **Tone**         | [STRICTLY] Professional tone in review comments                                                                                                  |
| **Output**       | Generate the code in the same given code language                                                                                                |
| **Persona**      | Act as a Solutions Architect to review the code and give the review comments                                                                     |

### Iterative Refinement

> Can we ask to improve the test cases based on the reviewer comments?

---

## 5. Instruction-Based Prompting with Constraints

> **Technique:** Provides detailed step-by-step instructions with explicit constraints and mandatory requirements.

### Example: Selenium Test Script Generation

**Instructions:**

- Generate a Selenium Java-based test script
- Verify the login on Salesforce
- Include setup and teardown methods using TestNG
- Use explicit waits instead of `Thread.sleep()`
- Validate both successful and unsuccessful login attempts
- `[MANDATORY]` Only TestNG
- `[MANDATORY]` Use only `@BeforeMethod` and `@AfterMethod` in TestNG Annotations

| Element     | Description                                                                              |
| ----------- | ---------------------------------------------------------------------------------------- |
| **Context** | Act like an Automation Assistant with Salesforce knowledge                               |
| **Tone**    | [STRICTLY] Professional tone in review comments and summary                              |
| **Output**  | Only code without any markdown or extra text                                             |
| **Persona** | Act as a Test Automation Architect to review the test cases and give the review comments |

---

## Quick Reference: Prompting Techniques Summary

| Technique             | When to Use                                | Key Elements                                          |
| --------------------- | ------------------------------------------ | ----------------------------------------------------- |
| **POA**               | When audience and output format matter     | Persona, Output, Audience                             |
| **Zero-Shot**         | Simple, straightforward tasks              | Direct instruction only                               |
| **Chain of Thought**  | Complex reasoning, multi-step tasks        | Task, Context, Rules, Process                         |
| **ICETOP**            | Comprehensive code/content generation      | Instructions, Context, Example, Tone, Output, Persona |
| **Instruction-Based** | Technical tasks with specific requirements | Detailed steps, Constraints, Mandatory rules          |
