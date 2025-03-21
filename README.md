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

#### File: 
`max_files` can be modified to adjust # files processed during model testing
File paths are meant for Google Colab setup; should be modified if needed

#### Dataset:
Modify the link parameter in the `load_dataset()` method call

### Citation
If you use this program in your research please cite:

```
@ARTICLE{2025arXiv250309905A,
       author = {{Andreyev}, Allison},
        title = "{Quantization for OpenAI's Whisper Models: A Comparative Analysis}",
      journal = {arXiv e-prints},
     keywords = {Computer Science - Sound, Computer Science - Computation and Language, Computer Science - Machine Learning, Electrical Engineering and Systems Science - Audio and Speech Processing, 68T50, 68T10, I.2.7, I.5.4, H.5.1},
         year = 2025,
        month = mar,
          eid = {arXiv:2503.09905},
        pages = {arXiv:2503.09905},
          doi = {10.48550/arXiv.2503.09905},
archivePrefix = {arXiv},
       eprint = {2503.09905},
 primaryClass = {cs.SD},
       adsurl = {https://ui.adsabs.harvard.edu/abs/2025arXiv250309905A},
      adsnote = {Provided by the SAO/NASA Astrophysics Data System}
}
```
