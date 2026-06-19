## README.md

# Educational Video Generator

This project automates the creation of short educational videos based on a user-provided topic. It leverages several AI and multimedia libraries to generate a script, voiceover, visual scenes, and then compile them into a final video.

## Features

-   **Script Generation**: Generates a structured educational script based on a given topic.
-   **Voiceover Creation**: Converts the generated script into an audio file using Google Text-to-Speech (gTTS).
-   **Visual Scene Generation**: Creates three distinct visual scenes using Stable Diffusion, based on cinematic prompts tailored to the video's topic.
-   **Video Compilation**: Combines the generated images and audio into a single MP4 video file using MoviePy.

## How it Works

1.  **Dependencies**: Installs necessary libraries like `diffusers`, `transformers`, `accelerate`, `moviepy`, and `gTTS`.
2.  **Directory Setup**: Creates `scripts`, `audio`, and `images` directories to organize output.
3.  **Topic Input**: Prompts the user to enter a topic for the educational video.
4.  **Scripting**: Generates a mock script (Hook, Explanation, Call to Action) and saves it to `scripts/script.txt`.
5.  **Voice Generation**: Reads the script, removes section headers, and generates an `audio/voice.mp3` file.
6.  **Prompt Generation**: Creates detailed Stable Diffusion prompts for three scenes, incorporating the chosen topic.
7.  **Image Generation**: Uses the `StableDiffusionPipeline` (requires a GPU runtime) to generate images for each scene and saves them to the `images/` directory.
8.  **Video Assembly**: Compiles the generated images and the voiceover audio into a final MP4 video, `final_video.mp4`, with each image clip timed to fit the total audio duration.

## Usage

To use this project:

1.  **Enable GPU Runtime**: In Google Colab, go to `Runtime > Change runtime type` and select `GPU` as the hardware accelerator.
2.  **Run All Cells**: Execute all the cells in the notebook sequentially.
3.  **Provide Topic**: When prompted, enter the topic for your desired educational video (e.g., "Neural Network").

The final video will be saved as `final_video.mp4` in the notebook's root directory.
