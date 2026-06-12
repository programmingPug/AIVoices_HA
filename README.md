# AIVoices_HA

Custom [Piper](https://github.com/OHF-Voice/piper1-gpl) text-to-speech voices for [Home Assistant](https://www.home-assistant.io/).

These are medium-quality, single-speaker English (`en-US`) neural voices trained for use with Home Assistant's local TTS engine.

## Voices

| Voice | Files | Language | Sample rate | Quality |
|-------|-------|----------|-------------|---------|
| **cathy** | `en_us-cathy-medium.onnx` + `.onnx.json` | en-US | 22050 Hz | medium |
| **cynda** | `en_us-cynda-medium.onnx` + `.onnx.json` | en-US | 22050 Hz | medium |
| **james** | `en_us-james-medium.onnx` + `.onnx.json` | en-US | 22050 Hz | medium |

Each voice consists of two files that must stay together:

- `*.onnx` — the trained model weights
- `*.onnx.json` — the voice configuration (phoneme map, sample rate, inference settings)

## Installation (Home Assistant)

These voices work with the **Piper** add-on / [wyoming-piper](https://github.com/rhasspy/wyoming-piper).

1. Locate the Piper data directory where custom voices are stored. For the
   official **Piper** add-on this is the share folder, typically:

   ```
   /share/piper/
   ```

2. Copy **both** files for each voice you want into that directory:

   ```
   en_us-cathy-medium.onnx
   en_us-cathy-medium.onnx.json
   ```

3. Restart the Piper add-on. Then in Home Assistant go to
   **Settings → Voice assistants → (your assistant) → Text-to-speech**
   and select the new voice.

> Tip: If a voice does not appear, confirm the `.onnx` and `.onnx.json`
> filenames match exactly and that both files are present.

## Testing a voice locally

With Piper installed you can render a sample to a WAV file:

```bash
echo "Hello from Home Assistant." | \
  piper --model en_us-cathy-medium.onnx --output_file sample.wav
```

## License

The licensing of a trained Piper voice depends on the dataset it was trained
on. Add a `LICENSE` file describing the terms that apply to these models and
their training data before distributing them.
