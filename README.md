# Auralis

Private, open-source desktop meeting assistant. Auralis transcribes audio locally, keeps a live transcript, analyzes an optional screenshot, and sends AI requests only to the provider you configure.

## Principles

- No account, sign-in, subscription, usage plan, or hosted Auralis relay.
- Local on-device transcription by default.
- Your API key is stored through the operating system's secure keychain.
- Bring any OpenAI-compatible provider: NVIDIA NIM, OpenAI, OpenRouter, Ollama, LM Studio, vLLM, or LiteLLM.
- Transcripts are saved locally under `Documents/Auralis`.

## Configure a provider

Open the Auralis toolbar, choose **Answers**, then **Add provider**. Choose one of the presets and enter your own key. For NVIDIA NIM, use:

```text
URL:   https://integrate.api.nvidia.com/v1
Model: nvidia/nemotron-3.5-lightning-30b-a3b
```

The provider receives only the text or screenshots required for the AI action you choose. Use Ollama for fully local answers.

## Development

```bash
cd app
npm ci
npm run fetch:asr
npm run dev
```

Useful checks:

```bash
npm run typecheck
npm test
npm run build
```

## Architecture

```text
app/    Electron, React, Vite, TypeScript desktop application
relay/  Legacy upstream service; Auralis does not use it
docs/   Repository documentation assets
```

## License and attribution

This fork retains the upstream Apache-2.0 license. Preserve required copyright and license notices when distributing changes.
