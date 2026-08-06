Here’s a clear separation of functional and non-functional requirements for AI security tools based on the course content:

Functional Requirements:

    Automate compliance gap analysis by scraping and analyzing policy texts.
    Detect risk gaps by cross-referencing policy claims with operational realities.
    Map security outputs to compliance frameworks like CCPA, NIST CSF, SOC 2, GDPR.
    Automate evidence collection for audits.
    Generate professional audit reports quickly.
    Integrate with existing GRC workflows and tools.


Non-Functional Requirements:

    Access Control: Restrict access using API key authentication to protect sensitive data.
    Input Validation: Validate inputs (e.g., URLs, company names) to prevent malicious data.
    Rate Limiting and Budget Controls: Limit request rates and daily usage to avoid abuse and control costs.
    Secrets Management: Securely store API keys and credentials using environment variables or secret managers.
    Audit Logging: Maintain detailed logs of all actions for traceability and compliance.
    Security-by-Design: Implement guardrails like input validation, privilege management, and access controls to build sustainable AI automations.
    Performance and Reliability: Ensure the system processes data efficiently and remains available.


This distinction helps ensure the AI security tools not only perform the required tasks but also operate securely and reliably in production environments.
