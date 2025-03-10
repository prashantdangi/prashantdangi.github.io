---
title: "LLM OWASP TOP 10 vulnerabilities"
categories: AI LLM
---


### LLM1:2025 Prompt Injection/Jailbreaking

Prompt injection vulnerability alters the Large-Language-Models(LLMs) behavious or output in an unintended way when user prompts something unusual 

Prompt injection does not need text to be human visible/readable as long as the content is parsed by the model.

For Example: Parsing white text on white papers(cannot be parsed by humans but will pe parsed by LLM models)

Retrieval-Augmented-Generation(RAG) and fine tunning aim to make LLM outputs more relevent and accurate. 

Jailbreaking is a form of prompt injection where the attacker provides inputs that cause the model to disregard its safety protocols entirely.

### LLM2:2025 Sensitive Information Disclosure

LLMs when embedded in application exposes risk to expose Sensitive Data, proprietory algorithms, or confidential details through their output.

Revealing training data can expose models to inversion attacks, where attacks extract sensitive information or reconstruct outputs

The "proof pudding attack" (CVE-2019-20634)

### LLM3:2025 Supply Chain

LLMs are susceptible to vulnerabilities of third-party pre trained models and data.

Open-access LLMs and fine tunning methods like "LoRA"(Low-Rank Adaptation) and "PEFT"(Parameter-efficient Fine-tunning) especially on platforms like Hugging Face introduce new Supply-Chain Attacks.

### LLM4:2025 Data and Model Poisoning

Data and Model Poisoning is somewhat same as LLM3:2025 Supply Chain Vulnerabilities discussed above. 

Data and model poisoning occurs when pre-trained, fine-tunning and embedded data is manipulated to introduce vulnerabilities, backdoors, or biases

### LLM5:2025 Improper Output Handling

Improper Output Handling refers specifically to insufficient validation, sanitization, and handling
of the outputs generated by large language models before they are passed downstream to other
components and systems. Since LLM-generated content can be controlled by prompt input, this
behavior is similar to providing users indirect access to additional functionality.

### LLM6:2025 Excessive Agency

LLM-based system is often granted a degree of agency by its developer - the ability to call functions or interface with other systems via extensions (sometimes referred to as tools, skills or
plugins by different vendors) to undertake actions in response to a prompt. The decision over which extension to invoke may also be delegated to an LLM 'agent' to dynamically determine based
on input prompt or LLM output. Agent-based systems will typically make repeated calls to an LLM using output from previous invocations to ground and direct subsequent invocations.

Excessive Agency is the vulnerability that enables damaging actions to be performed in response to unexpected, ambiguous or manipulated outputs from an LLM, regardless of what is causing the
LLM to malfunction. Common triggers include:

• hallucination/confabulation caused by poorly-engineered benign prompts, or just a poorly-performing model;

• direct/indirect prompt injection from a malicious user, an earlier invocation of a malicious/compromised extension, or (in multi-agent/collaborative systems) a malicious/compromised peer agent.

The root cause of Excessive Agency is typically one or more of:\
• excessive functionality;\
• excessive permissions;\
• excessive autonomy.

Excessive Agency can lead to a broad range of impacts across the confidentiality, integrity and availability spectrum, and is dependent on which systems an LLM-based app is able to interact
with.

Note: Excessive Agency differs from Insecure Output Handling which is concerned with insufficient scrutiny of LLM outputs.

### LLM7:2025 System Prompt Leakage

The system prompt leakage vulnerability in LLMs refers to the risk that the system prompts or instructions used to steer the behavior of the model can also contain sensitive information that was not intended to be discovered.

### LLM8:2025 Vector and Embedding Weakness

In System utilizing Retrieval Augmented Model(RAG) with Large Language Models(LLMs) are more prone to these types of attacks.

Weakness in how vectors and embeddings are generated, stored, or retrieved can be exploited by malicious actions(intentional or unintentional) to inject harful content, manipulate model outputs and access sensitive information.

### LLM9:2025 Misinformation 

Large Language Models(LLMs) produces false or misleading information that appears credible.

The major cause of misinformation is LLMs Hallucination. Hallucination occur when LLMs try to fill empty gaps in between unknown user input without truly understanding the content. And this is the major source of Misinformation.

Retrieval-Augmented-Generation(RAG) can be used to improve the reliability of the model.

### LLM10:2025 Unbound Consumption

Unbounded Consumption refers to the process where a Large Language Model (LLM) generates  outputs based on input queries or prompts. Inference is a critical function of LLMs, involving the application of learned patterns and knowledge to produce relevant responses or predictions.