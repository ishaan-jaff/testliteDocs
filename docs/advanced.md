# Advanced

## Use liteLLM to send Output Data to Posthog, Sentry etc

## Current Integrations
liteLLM simplifies sending your LLM output / exceptions to the following providers, See Adding an integration for adding support for one of your integrations
- Posthog
- Sentry
- Slack Alerts

### Quick Start
```python

from litellm import completion_client, embedding
import os

os.environ['SENTRY_API_URL'] = ""
os.environ['POSTHOG_API_KEY], os.environ['POSTHOG_API_URL] = "api-key", "api-url"
completion = completion_client(success_callback=["posthog"], failure_callback=["sentry", "posthog"])

```

