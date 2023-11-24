# nachotron-voice

Project completed in December 2022, training a Text-to-Speech model to clone the voice of Nach using a GAN. Examples:

* [Poem generated using ChatGPT and read by Nachotron :point_left:](https://github.com/pablomm/nachotron-voice/raw/main/docs/nachotron_chatgpt_poem.mp3)
* [*Esclavos del destino* sung by Nachotron :point_left:](https://github.com/pablomm/nachotron-voice/raw/main/docs/nachotron_esclavos_del_destino.mp3)

For the project, we generated a dataset of Nach's voice, transcribing their discography with Whisper, and using Demucs to separate the voice from the music. Then we trained a TTS model using a CoquiTTS model as the base, and had fun generating new songs with the model. A presentation for the course 'Deep Learning for Audio Signal Processing' that describes the project can be found here in [PDF](docs/presentation_DLASP.pdf) or [PowerPoint](docs/presentation_DLASP.pptx) format.

## Code

All the project work was done using Colab, with the following notebooks:

1. [Data Collection](notebooks/0_data_collection.ipynb). Process original discography in zip and store as separate songs.
2. [Music Source Separation](notebooks/1_music_source_separation.ipynb). Separate voice from music using Demucs for all songs.
3. [Speech Transcription](notebooks/2_speech_transcription.ipynb). Transcribe voice from all songs using Whisper.
4. [Noise Reduction](notebooks/3_noise_reduction.ipynb). Reduce noise from all voice tracks.
5. [Dataset Preparation](notebooks/4_dataset_preparation.ipynb). Cut voice into segments detected as separate sentences by Whisper.
6. [Speaker Identification](notebooks/5_speaker_identification.ipynb). Perform speaker identification to detect Nach's voice, and filter out other voices and cuts without voice.
7. [Train GAN](notebooks/6_train_tts.ipynb). Train a TTS model using CoquiTTS as the base.
8. [Align Voice and Music](notebooks/7_aligning.ipynb). Experiment to automatically align voice generated with our model and a music track.
9. [Other Training](notebooks/8.1_frankestein_retrain_tts.ipynb). Retrain the model with a different dataset, and with different parameters.
10. [Demo](notebooks/9_directo_exposicion.ipynb). Demo of the model, loads a model checkpoint and generate a voice track with a text.

The data used and the dataset is not released due to potential copyright issues. However, the scripts can be used to generate a similar dataset with any discography and replicate the voice cloning (possibly with a more recent and better model).

There are many aspects of this project that could be improved, but it was created in just a weekend purely for fun. We hope you enjoy the results!

<p align="center">
 <img src="./docs/pablo_rap_disc.png" alt="Pablo cover" width="400" height="400">
</p>

## Acknowledgments

We thank Nach for many years of great music, and the resources and libraries used for this project: [Colab](https://colab.research.google.com/), [CoquiTTS](https://github.com/coqui-ai/TTS), [Demucs](https://github.com/facebookresearch/demucs), [deep-speaker](https://github.com/philipperemy/deep-speaker.git) and [Whisper](https://github.com/openai/whisper).
