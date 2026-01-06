ComfyUI_DiffRhythm2 is a ComfyUI extension node based on the Xiaomi DiffRhythm2 model, capable of generating high-quality musical works via Text Prompts / Reference Songs + Lyrics.

https://github.com/user-attachments/assets/9d67a3df-893c-4ede-9364-10f8b7ca4431

🚀 Installation
Windows System Configuration:

Download and install the latest version of [espeak-ng](https://github.com/espeak-ng/espeak-ng/releases/tag/1.52.0)

Add a system environment variable named PHONEMIZER_ESPEAK_LIBRARY. The value should be the path to the `libespeak-ng.dll` file within your installed espeak-ng folder. Example: `C:\Program Files\eSpeak NG\libespeak-ng.dll`.

Linux System:

You need to install the espeak-ng` package. Run the following command to install:

`apt-get -qq -y install espeak-ng`

Go to the ComfyUI custom_nodes directory:

```Bash
cd ComfyUI/custom_nodes
```
Clone this repository:

```Bash
git clone https://github.com/billwuhao/ComfyUI_DiffRhythm2.git
```
Install dependencies:

```Bash
cd ComfyUI_DiffRhythm2
pip install -r requirements.txt
```
Restart ComfyUI.

📋 Usage Instructions
Node Input Parameters
Required Parameters
Music Style Prompts: Describe the desired music style, e.g., "Vocal, Indie, Pop, Synthesizer, Piano, Electric Guitar, Rock, Happy, Romantic".

Lyrics: Input the lyrics text. Supports structure tags (see explanation below).

Max Song Length: Set the maximum length of the generated song (in seconds). Range: 10-500 seconds. Usually generates songs around 2~3 minutes.

Optional Parameters
Reference Audio: Upload a reference audio file to generate music with a similar style.

Steps: Diffusion model sampling steps. Default is 20, range is 10-100.

cfg (cfg): Classifier Free Guidance strength. Default is 2.0, range is 1.0-10.0.

seed (seed): Random seed for reproducing results.

Unload Model: Whether to unload the model after generation to free up memory.

🏗️ Lyrics Structure Tags
You can use the following structure tags to organize the lyrics:
```
[start] - Start marker
[end] - End marker
[intro] - Intro
[verse] - Verse
[chorus] - Chorus
[outro] - Outro
[inst] - Instrumental
[solo] - Solo
[bridge] - Bridge
[hook] - Hook
[break] - Break
[stop] - Stop
[space] - Space/Pause
```
Lyrics Example
```
[start]
[intro]
[verse]
In this beautiful night
Starlight fills the sky
[chorus]
Let us sing together
Sing out the dreams in our hearts
[verse]
The breeze gently brushes the face
Bringing the fragrance of flowers
[chorus]
Let us sing together
Sing out the dreams in our hearts
[outro]
[end]
```
Model Download
Models will be downloaded automatically upon first use.

You can also manually download them into the `ComfyUI\models\TTS\DiffRhythm` folder.

The directory structure should be as follows:

```
.
├─DiffRhythm2
│      config.json
│      decoder.bin
│      decoder.json
│      model.safetensors
│
├─MuQ-large-msd-iter
│      config.json
│      model.safetensors
│
├─MuQ-MuLan-large
│      config.json
│      pytorch_model.bin
│
└─xlm-roberta-base
        config.json
        model.safetensors
        sentencepiece.bpe.model
        tokenizer.json
        tokenizer_config.json
```
Manual download links:

- https://huggingface.co/ASLP-lab/DiffRhythm2/tree/main
- https://huggingface.co/OpenMuQ/MuQ-MuLan-large/tree/main
- https://huggingface.co/OpenMuQ/MuQ-large-msd-iter/tree/main
- https://huggingface.co/FacebookAI/xlm-roberta-base/tree/main

🙏 Acknowledgments
[xiaomi-research/diffrhythm2](https://github.com/xiaomi-research/diffrhythm2)



