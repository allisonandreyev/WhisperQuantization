# Whisper Quantization Experiment

This repository provides a simple Python script to download and process the **LibriSpeech ASR** dataset for automatic speech recognition (ASR) tasks. The script uses **Hugging Face's `datasets` library**.

## **Features**
- Downloads Whisper CPP base & quantization requirements
- Quantizes Whisper model (default INT6, compatible with INT4, INT5, INT8)
- Runs WER evaluation experiment using https://github.com/ins8ai/wer
  
## **Requirements**
- Python 3
- Google Colab Environment

## Customization

#### Quantization method:<br>
`!./build/bin/quantize models/ggml-base.en.bin models/ggml-base.en-q6_0.bin q6_0`<br>
`!./build/bin/whisper-cli -m models/ggml-base.en-q6_0.bin ./samples/gb0.wav `<br>

The `q6_0` string in the command should be modified to `q5_0` for INT5 quantization, `q4_0` for INT4 quantization and etc.

#### File: 
`max_files` can be modified to adjust # files processed during model testing
File paths are meant for Google Colab setup; should be modified if needed

#### Dataset:
Modify the link parameter in the `load_dataset()` method call

### Citation
If you use this program in your research please cite:

```
@article{andreyev2025quantizationopenaiswhispermodels,
      title={Quantization for OpenAI's Whisper Models: A Comparative Analysis}, 
      author={Allison Andreyev},
      year={2025},
      eprint={2503.09905},
      archivePrefix={arXiv},
      primaryClass={cs.SD},
      url={https://arxiv.org/abs/2503.09905}, 
}
```
