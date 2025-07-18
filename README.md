# ⛪️ n8n Sermon Automation Workflow
This repository documents the development of a sermon automation workflow that will be used to generate and post social media content when a sermon is uploaded to YouTube.

## Audio Transcriber Workflow
This n8n workflow watches for an audio file to be created in the audio_files folder in Google Drive. It then downloads that file and writes it to the disk. FFmpeg is used to split the audio into 900 second chunks where they can be read and transcribed through OpenAI. The separate transcripts are then combined into one transcript which is converted into a text file and uploaded to the transcripts folder in Google Drive. The files written to the disk are deleted to save space. A summary of the final transcript is created, and a WordPress post is created containing both the summary and transcript. The name of the original audio file is used as the name of the transcript uploaded to Google Drive as well as the title of the WordPress post.
