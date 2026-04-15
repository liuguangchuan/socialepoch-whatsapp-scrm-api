---
name: socialepoch-whatsapp-scrm
description: Officially integrated with SocialEpoch global WhatsApp SCRM open API, tailored for enterprise overseas marketing and customer service scenarios. Full coverage of WhatsApp account management, online agent query, customer operation, user profiling, chat record retrieval and Webhook callback. Supports one-on-one & bulk messaging for text, image, audio, video, document, business card, link card and diversion link. Built-in signature adaptation, automatic dependency management and zero-configuration deployment to empower overseas private domain and automated operation.
version: 2.1.3
author: SocialEpoch
metadata:
  emoji: 📱
  type: tool
  platform: darwin
  openclaw:
    requires:
      bins: ["python3"]
      env: ["SOCIALEPOCH_TENANT_ID", "SOCIALEPOCH_API_KEY"]
    primaryEnv: SOCIALEPOCH_API_KEY
    install:
      - id: python-brew
        kind: brew
        formula: python
        bins: ["python3"]
        label: Install Python 3 (brew)
    launcher:
      command: "${PYTHON}"
      args:
        - "scrm_api.py"
      python: true
      auto_bootstrap: true
      auto_install_python: true
---

# SocialEpoch WhatsApp SCRM Intelligent Assistant
Comprehensive management for WhatsApp service accounts. Support one-on-one and bulk delivery of text, images, audio, videos, documents, business cards and link messages, with online agent query and automatic signature. No manual dependency installation or environment configuration required. Clear guidance will be prompted when configuration is missing.

## Core Features
- 📱 Cross-platform compatibility: Native adaptation for Mac
- 📦 Dependency management: Automatic detection and installation of requests
- 🔧 Dual configuration: Environment variables & local config file
- ✅ Strict validation: Format, non-empty and type checking for all parameters
- 📊 Structured output: Standardized JSON response for all results

## Configuration Methods (Choose One)
### Method 1: Environment Variables (Recommended)
```bash
export SOCIALEPOCH_TENANT_ID="Your Tenant ID"
export SOCIALEPOCH_API_KEY="Your API Key"
```

### Method 2: Command Line Configuration
```bash
python3 scrm_api.py set_config Your_Tenant_ID Your_API_Key
```

## Supported Commands
### Query Online Agent Accounts
```bash
python3 scrm_api.py query_online_agents
```

### Send Text Message
```bash
python3 scrm_api.py send_text Sender_Number Recipient_Number "Message Content"
```

### Send Image
```bash
python3 scrm_api.py send_img Sender_Number Recipient_Number "Image URL" "Remark"
```

### Send Audio
```bash
python3 scrm_api.py send_audio Sender_Number Recipient_Number "Audio URL"
```

### Send Document
```bash
python3 scrm_api.py send_file Sender_Number Recipient_Number "File URL" "Remark"
```

### Send Video
```bash
python3 scrm_api.py send_video Sender_Number Recipient_Number "Video URL" "Remark"
```

### Send Business Card
```bash
python3 scrm_api.py send_card Sender_Number Recipient_Number "Card Content"
```

### Send Brand Link Card
```bash
python3 scrm_api.py send_card_link Sender_Number Recipient_Number "Title" "Link URL" "Description" "Cover Image URL"
```

### Send Diversion Link
```bash
python3 scrm_api.py send_flow_link Sender_Number Recipient_Number "Title" "Diversion Number List"
```

### Query Task Status
```bash
python3 scrm_api.py query_task Task_ID
```

## Bulk Messaging
Bulk delivery is available for text, image, video, audio, document and link card messages.
Separate multiple recipient numbers with an **English comma (,)**.

## Operation Rules
1. The assistant only executes operations based on explicit user instructions.
2. Local configuration is stored only for normal tool operation.
3. All actions require clear user authorization and intention confirmation.

## Error Handling
- Missing dependencies → Friendly installation prompt
- Missing configuration → Clear setup guidance
- Invalid parameters → Usage reminder
- Network exception → Adaptive retry mechanism
```