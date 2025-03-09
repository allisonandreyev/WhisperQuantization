# Whisper Quantization Experiment

This repository provides a simple Python script to download and process the **LibriSpeech ASR** dataset for automatic speech recognition (ASR) tasks. The script uses **Hugging Face's `datasets` library**.

## **Features**
- Downloads Whisper CPP base & quantization requirements
- Quantizes Whisper model (default INT6, compatible with INT4, INT5, INT8)
- Runs WER evaluation experiment using https://github.com/ins8ai/wer
  
## **Requirements**
- Python 3

## Customization

#### Quantization method:<br>
`!./build/bin/quantize models/ggml-base.en.bin models/ggml-base.en-q6_0.bin q6_0`<br>
`!./build/bin/whisper-cli -m models/ggml-base.en-q6_0.bin ./samples/gb0.wav `<br>

The "q6_0" string in the code should be modified to "q5_0" for INT5 quantization, "q4_0" for INT4 quantization and etc.

#### File 
`max_files` can be modified to adjust # files processed during model testing
File paths are meant for Google Colab setup; should be modified if needed

#### Dataset
Modify the link parameter in the `load_dataset()` method call

### arXiv Publication

Link: 

> Automated speech recognition (ASR) models have gained prominence for applications such as captioning, speech translation, and live transcription. Whisper includes three model variants: one optimized for live speech streaming and another for offline transcription. However, these models are not always accurate when transcribing speech, and some transcriptions include fabricated or hallucinated content. Furthermore, larger model variants exhibit increased latency and pose challenges for deployment on resource-constrained devices. In this study, the similarities between the 3 Open AI Whisper Models are reviewed, used for speech transcription. Through a qualitative analysis, we examine the similarities, differences, and unique capabilities of the three models. This study evaluates the impact of quantization on Whisper's latency and its feasibility for deployment on smaller devices. Using the open source LibriSpeech dataset, this study evaluates the word error rate (WER) on all 3 models along with its total time transcribing. The results indicate quantization effectively reduces latency while maintaining transcription accuracy. Upon the 4 different quantization methods tested, we additionally discover that accuracy transcribing the complex corpus is unaffected by model size. These findings provide insights into the optimal use cases of different Whisper models.

By: Allison Andreyev
