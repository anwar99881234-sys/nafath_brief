Version: NAFATH-V3

Track: Software

## Overview
A government AI assistant must provide citizens with accurate and secure answers about public services. Software versioning helps developers update the assistant's API without unexpectedly breaking the mobile app or other connected systems. Retrieval-Augmented Generation (RAG) can ground answers in trusted service information, while mobile security controls protect communications with the assistant. Reliable networking supports access as connected devices grow, and cybersecurity measures help defend against prompt injection and other attacks. Data protection practices are essential when storing chat logs, especially when conversations may contain personal information. These fields work together: software defines stable interfaces, AI generates useful responses, mobile and networking deliver the service, cybersecurity reduces threats, and data practices protect citizens. This brief examines the six areas and focuses on Semantic Versioning for the Software track.

## Software
Semantic Versioning uses three numbers: MAJOR.MINOR.PATCH. The MAJOR version must increase when a public API change is incompatible with existing clients. MINOR increases when new functionality is added in a backward-compatible way. PATCH increases for backward-compatible bug fixes. For a government AI assistant, breaking an API response format may require a MAJOR release, while adding an optional field may qualify as MINOR. Teams should document changes and test client compatibility.
Resource: Semantic Versioning 2.0.0 - https://semver.org/

## AI
Retrieval-Augmented Generation (RAG) combines a language model with a retrieval system that finds relevant information from an external knowledge source. The assistant can use retrieved government service documents to ground its response instead of relying only on information learned during training. RAG can reduce unsupported answers, but it does not eliminate errors: retrieved documents may be outdated or irrelevant, and the model may still misinterpret them. Sources should be reviewed and kept current.
Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401

## Mobile
iOS App Transport Security (ATS) requires secure connections that meet Apple's transport security requirements, including HTTPS with appropriate TLS settings. If an app tries to connect to a plain HTTP endpoint, ATS normally blocks the connection. This protects citizens' communications from risks associated with unencrypted transport. Developers should configure servers to support HTTPS rather than broadly disabling ATS, because exceptions can weaken the app's security.
Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking
IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses, providing a much larger address space. IPv6 was designed to support the continued growth of internet-connected devices. For a government AI service, reliable networking helps the mobile app communicate with backend APIs and retrieve information. IPv6 adoption does not automatically make a network more secure; correct configuration, access controls, and monitoring remain necessary.
Resource: RFC 8200 - Internet Protocol, Version 6 (IPv6) Specification - https://datatracker.ietf.org/doc/html/rfc8200

## Cybersecurity

Prompt injection occurs when malicious instructions are supplied through user input or external content in an attempt to influence an AI system's behavior. Direct injection may appear in a user's prompt, while indirect injection may be hidden in retrieved documents or other content. A government assistant should treat retrieved text as untrusted, restrict tools to necessary permissions, validate actions, and avoid exposing sensitive data. No single defense guarantees complete protection.
Resource: OWASP Prompt Injection - https://owasp.org/www-community/attacks/PromptInjection

## Data

Anonymisation aims to prevent individuals from being identified from a dataset, whereas pseudonymisation replaces direct identifiers with substitutes. Pseudonymised information may still identify someone if additional information is available, so it should not automatically be treated as anonymous. A government AI assistant should minimise the personal data it collects, restrict access to chat logs, define retention periods, and assess re-identification risks before using data for analysis or model improvement.
Resource: ICO - Anonymisation - https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-sharing/anonymisation/

## Misconception in My Track
A common misconception is that increasing the MAJOR version number is necessary for every software update. In Semantic Versioning, backward-compatible new functionality normally increases MINOR, and backward-compatible bug fixes increase PATCH. MAJOR is required when a change breaks compatibility with the public API. Choosing the correct version helps teams communicate risk and avoid unexpected failures in dependent applications.
Resource: Semantic Versioning 2.0.0 - https://semver.org/

## Open Question
 How can a government team introduce breaking API changes to its AI assistant while maintaining reliable service for citizens using older versions of the mobile application?
