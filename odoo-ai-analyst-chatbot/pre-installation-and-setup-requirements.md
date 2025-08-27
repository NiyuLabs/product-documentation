---
description: >-
  Before you embark on the journey of integrating the Odoo AI Analyst Chatbot
  into your system, it's crucial to understand the foundational requirements and
  prepare your environment.
---

# Pre-Installation & Setup Requirements

#### Target Audience & Skill Level

This guide assumes you are an **Odoo Administrator**, an **IT Manager**, or a **Power User** with administrative access to your Odoo instance. A basic understanding of Odoo module installation, configuration, and user management is beneficial. While no coding is required, familiarity with managing API keys and external service configurations is helpful.

#### System Requirements

To ensure seamless operation, your Odoo environment should meet the following minimum requirements:

1. **Odoo Version:**
   * The Niyulabs AI Analyst Chatbot is typically developed for specific Odoo versions. Always check the Odoo App Store listing for the exact compatible versions (e.g., Odoo 15, Odoo 16, Odoo 17).
   * Ensure your Odoo instance is running a stable and supported version.
2. **Hosting Environment:**
   * **Odoo.sh / Odoo Enterprise Cloud:** Generally compatible, but ensure you have the necessary permissions to install custom modules and configure system parameters.
   * **Self-Hosted Odoo:** Fully compatible. Ensure your server has sufficient resources (RAM, CPU) to handle additional AI processing tasks, though most heavy lifting is offloaded to the external LLM provider.
3. **Internet Connectivity:**
   * Your Odoo server must have stable and unrestricted outbound internet access to communicate with the external Large Language Model (LLM) service provider (e.g., OpenAI). Ensure no firewalls or proxies are blocking access to these services.
4. **Python Dependencies:**
   * While the module primarily leverages Odoo's existing Python environment, it may introduce specific Python library dependencies. Odoo's standard installation process usually handles these, but in custom environments, you might need to ensure they are present (e.g., openai Python library, if not already included by Odoo).

#### External Service Dependencies: Large Language Models (LLMs)

The core intelligence of the Niyulabs AI Analyst Chatbot relies on connecting to powerful external Large Language Models (LLMs). Currently, the most common and robust integration is with **OpenAI's GPT series**.

1. **OpenAI Account & API Key:**
   * You will need an active account with OpenAI (platform.openai.com).
   * **Crucially, you must generate an API Key.** This key is a unique identifier that authenticates your Odoo instance with OpenAI's services and enables it to make requests.
   * **Billing:** OpenAI services are typically pay-as-you-go based on usage (token consumption). Ensure your OpenAI account has a valid payment method and sufficient credits.
   * **Model Choice:** Be prepared to select a suitable OpenAI model (e.g., gpt-3.5-turbo for cost-efficiency and speed, or gpt-4 for enhanced accuracy and complex reasoning, albeit at a higher cost).
2. **Other LLM Providers (Potential):**
   * While OpenAI is the primary integration, Niyulabs may extend support for other LLM providers in the future (e.g., Anthropic's Claude, Google's Gemini). Always consult the module's documentation or the Odoo App Store listing for the latest supported providers. If using an alternative, you'll need an API key for that specific service.

#### Security Considerations

Handling API keys for external services requires careful attention to security:

* **Confidentiality:** Your OpenAI API key is a sensitive credential. Treat it like a password. Do not hardcode it into public files or share it unnecessarily. The Niyulabs module will guide you to store it securely within Odoo's system parameters.
* **Access Control:** Only Odoo administrators should have access to configure and view the API key within Odoo's settings.
* **Data Privacy:** Understand that while your Odoo data is analyzed by the chatbot, only relevant snippets necessary to answer a query are typically sent to the external LLM. Niyulabs will have implemented measures to ensure data privacy and compliance. Always review their specific privacy policy and data handling practices.
* **Usage Monitoring:** Keep an eye on your OpenAI usage dashboard to monitor costs and detect any unusual activity.

#### Licensing and Acquisition

* The Odoo AI Analyst Chatbot by Niyulabs is a **commercial module** available for purchase on the [Odoo App Store](https://www.google.com/url?sa=E\&q=https%3A%2F%2Fapps.odoo.com%2F).
* Before installation, ensure you have acquired the module, as you will need the module's .zip or .tar.gz file for manual installation, or have it available for direct installation through Odoo.sh or your Odoo Enterprise subscription.

By ensuring all these prerequisites are met, you'll be well-prepared for a smooth and successful installation of the Odoo AI Analyst Chatbot, paving the way for intelligent data analysis.
