---
workflow: sipmsg-workflow
skill: workflow-orchestrator
description: Analyze log files for SIP signaling activity using the sipmsg template.

default_max_lines: 200

input:
  - path: "*.txt"
    skill: android-log-analysis
    include:
      - ../../log-templates/log/sipmsg.yaml

final_summary_prompt: >
  Based on the SIPMSG matches, summarize the SIP signaling timeline, highlight
  any suspicious or failure-related messages, and suggest next troubleshooting
  steps.
---

# SIPMSG Workflow

This workflow analyzes text log files and extracts SIP signaling lines using the
`sipmsg` template. Use it when you want a quick SIP-focused view of log output,
including a concise summary of signaling behavior and notable anomalies.
