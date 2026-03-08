An automated NLP pipeline built in Google Colab that extracts transcripts from YouTube videos and generates concise, high-quality summaries using Hugging Face Transformers.
Project Overview
This project addresses the challenge of consuming long-form video content quickly. By leveraging the BART (Bidirectional and Auto-Regressive Transformers) model, the application converts spoken video content into a readable summary, saving time and highlighting key takeaways.
Tech Stack
Environment: Google Colab
Language: Python
NLP Framework: Hugging Face transformers
Data Source: youtube_transcript_api

How It Works
1. Data Extraction
The project uses the youtube_transcript_api to fetch raw captions from a provided YouTube URL. It extracts the unique video_id to target the correct content.

2. Text Processing & Chunking
Since Transformer models have a maximum token limit, the script:
Cleans and joins individual transcript fragments into a single text body.
Chunks the text into segments of 1,000 characters to ensure the model processes the entire video without crashing or losing data.

3. Summarization Pipeline
Each text chunk is passed through a summarization pipeline. The BART-Large-CNN model, specifically fine-tuned on the Samsum dataset, is used to generate natural-sounding summaries for each segment.

4. Results
The final output is a concatenated string of summarized text, significantly reducing the original word count while retaining the core message.

You will need to install the following libraries:
Bash
pip install transformers youtube_transcript_api

Usage

Open the notebook in Google Colab.
Provide a YouTube URL.
Run the cells to extract the transcript and generate your summary.

Key Features
Chunked Logic: Handles long videos by breaking text into manageable parts.

In-Notebook Preview: Uses IPython.display to show the video alongside the processing code.

Optimized Model: Uses a model fine-tuned for dialogue, which is ideal for the conversational nature of YouTube videos.
