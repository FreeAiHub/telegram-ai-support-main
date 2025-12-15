```markdown
# Data Model
## ER Diagram

**Users**
- user_id (PK)
- telegram_id
- language
- created_at

**Conversations**
- convo_id (PK)
- user_id (FK)
- model
- system_prompt
- created_at
- updated_at

**Messages**
- message_id (PK)
- convo_id (FK)
- role (user/assistant/tool)
- content
- timestamp

**Plugins**
- plugin_id (PK)
- name
- enabled
- config

**API Keys**
- key_id (PK)
- service (OpenRouter/GPT4/Claude)
- key
- usage_limit
- last_used
```