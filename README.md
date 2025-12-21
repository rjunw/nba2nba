# NBA2NBA

An E2E system for generating next best actions for given NBA scenarios (offense + defense).

## Current TODOs

- ~~Fine-tune RF-DETR for NBA player detection~~
- ~~Implement ByteTrack/DeepSORT for multi-object tracking~~
- ~~Implement OCR for jersey number detection, to map tracking IDs to players, teams, and stats~~
  - Had fun implementing a CNN-Transformer CTC OCR model from scratch, but it's not as accurate as I'd like, so I'm going to use a pre-trained model and fine-tune if necessary
  - We only want to track players, so filter out bboxes corresponding to non-players
  - Keep track of current team and jersey number for each tracklet, when tracks are lost/reappeared, update jersey number
  - If at analysis time, there are ambiguous player IDs, pass in image sequence corresponding to tracklet to LLM to get a best guess
- Implement scene transition detection to separate different plays (and re-run tracking if needed)
- ~~Fine-tune YOLOv11 for keypoint detection -> Homography transform to get top-down court view~~
- Transform sequence of top-down court into vector embeddings for vector retrieval
- Translate time series of vector embeddings into human-readable actions for Gemini to generate next best actions
- Serve models as API endpoints (FastAPI)
- Implement Streamlit UI for interactive UX (including video player (tracking/bounding boxes similar to NBA2K UI (?)), play-by-play, etc.)

## Overview

TODO: Input system flowchart here.

## Demo

Current project status:

<img src="https://imgur.com/rWyuvz3.gif" alt="tracking demo" width="50%" height="50%">

## How to run

TODO: Instructions for build and run here.
