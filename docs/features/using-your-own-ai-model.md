# Using your own AI model (BYOK)

openkoutsi's [AI features](../data-and-ai.md) — activity analysis, daily training
status, and AI plan/workout generation — run against any **OpenAI-compatible**
chat API. Instead of relying on whatever your instance's administrator has set
up, you can point openkoutsi at **your own** endpoint: a local model on your
machine, or a hosted provider you have an account with. This is often called
**BYOK — "bring your own key"**.

!!! info "When would I use this?"
    - You run a **local model** (Ollama, LM Studio, llama.cpp…) and want the AI
      features to use it, so nothing leaves your computer.
    - You have your **own account** with a hosted provider and want to use your
      own API key rather than the instance's.
    - Your instance requires you to bring your own model to use the AI features.

## Setting it up

Open **Settings → AI / LLM**. You'll see a card with three fields:

| Field | What to enter |
|---|---|
| **Base URL** | The endpoint of your OpenAI-compatible server, e.g. `http://localhost:11434/v1` for a local Ollama, or `https://api.openai.com/v1` for a hosted provider. |
| **Model** | The model name to request, e.g. `llama3.2` or `gpt-4o-mini`. |
| **API key** | Optional. Leave blank for a keyless local server; paste your provider key for a hosted service. |

Click **Test connection** to send a tiny "hello" message and confirm the model
replies, then **Save**. The banner at the top of the card shows whether you're
**using your own LLM server** or **this instance's LLM**.

!!! tip "The Test button works before you save"
    *Test connection* uses whatever is currently in the form, so you can verify a
    URL, model, and key before committing them.

=== "Local model (Ollama)"

    1. Install [Ollama](https://ollama.com/) and pull a model, e.g.
       `ollama pull llama3.2`.
    2. In **Settings → AI / LLM** set:
        - **Base URL**: `http://localhost:11434/v1`
        - **Model**: `llama3.2`
        - **API key**: leave blank
    3. **Test connection**, then **Save**.

    Requests to a local model never leave your machine.

=== "Hosted provider"

    1. Get an API key and the OpenAI-compatible base URL from your provider.
    2. In **Settings → AI / LLM** set:
        - **Base URL**: the provider's `/v1` endpoint, e.g. `https://api.openai.com/v1`
        - **Model**: a model the provider offers, e.g. `gpt-4o-mini`
        - **API key**: your provider key
    3. **Test connection**, then **Save**.

    Requests go to that provider under **their** privacy and data-retention
    terms — see [Your data & AI](../data-and-ai.md).

## Once your own server is set

As soon as you save your own **Base URL**, openkoutsi uses **only** your
configuration for every AI feature. Your instance's model and key are ignored
entirely — so the instance's API key is never sent to your server, and your key
is never mixed with the instance's endpoint.

To go back to the instance's LLM, use **Clear** on the card. Future AI actions
then use whatever your administrator has configured (if anything).

## How your API key is stored

Your API key is **encrypted at rest** on the server (AES-256/Fernet, with a key
derived from your user ID) and is **never returned to your browser** after you
save it. When an AI feature runs, the server decrypts it in memory only to make
the request on your behalf — all AI calls are proxied through the backend, so
your key and request data never leave your self-hosted instance except to reach
the endpoint you chose.

!!! note "Leaving the key blank keeps the current one"
    If you already saved a key, leaving the **API key** field blank on your next
    save keeps it unchanged. Use **Clear** to remove it (for example when
    switching to a keyless local model).

## Allowed servers

Some instances restrict BYOK to a **vetted list of providers**. When that's the
case, the **Base URL** field becomes a dropdown of the allowed servers instead
of free text, and saving a URL outside the list is rejected. If the provider you
want isn't listed, ask your administrator.

## Troubleshooting

!!! warning "Connection failed"
    - **Connection refused / timed out** — the base URL isn't reachable from the
      server. For a local model, make sure it's running and reachable from where
      openkoutsi runs (a server in a container may not reach your laptop's
      `localhost`).
    - **Authentication failed** — check your API key, or clear it for a keyless
      local server.
    - **Not in the allowed list** — your instance restricts BYOK URLs; pick one
      from the dropdown or ask your administrator.
    - **The reply wasn't in the expected format** — the endpoint isn't
      OpenAI-compatible, or the model name is wrong.

For what each AI feature sends to the model and where it goes, see
[Your data & AI](../data-and-ai.md).
