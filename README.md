# AI-Based Real-Time Conventional Deadlift Posture Correction System Using MediaPipe

## Overview
This project presents an AI-based real-time posture correction system for conventional deadlift exercises, designed to prevent injuries and enhance performance in strength training. Utilizing **MediaPipe** and **OpenCV**, the system tracks body keypoints to analyze joint angles (shoulders, hips, knees, ankles) and provides multi-modal feedback (visual markers, text, and audio) during three deadlift stages: **Set-Up**, **Lifting**, and **Lock-Out**. The system also counts repetitions and categorizes them as correct/incorrect based on form.

## Key Features
- **Real-time Pose Estimation**: Tracks 33 body keypoints using MediaPipe’s BlazePose model.

![Figure1](https://github.com/user-attachments/assets/14b1f0a4-f3f6-4219-ba7b-bfd3413ef5bc)

*MediaPipe’s 33 keypoints.*

- **Joint Angle Analysis**: Calculates angles for shoulders, hips, knees, and ankles to evaluate form.
- **Stage-Specific Feedback**: Provides corrective instructions for each deadlift stage (Set-Up, Lifting, Lock-Out) e.g., "Lift hips higher" during Set-Up
- **Multi-Modal Feedback**:
  - **Visual**: Colored markers (red/green) highlight incorrect/correct joints.
  - **Text**: On-screen messages guide proper form.
  - **Audio**: Text-to-speech (pyttsx3) delivers verbal corrections.
- **Repetition Tracking**: Counts and categorizes repetitions as correct or incorrect based on comprehensive joint criteria.
- **Neutral Spine Guideline**:  Visual indicator to help maintain proper back position throughout the exercise.


![Figure2](https://github.com/user-attachments/assets/6e1ebb80-c343-43a2-b4b4-d71d75e1e76d)

  The pipeline processes input video frames through MediaPipe Pose Estimation to extract 33 keypoints,
  calculates joint angles (shoulders, hips, knees, ankles), and evaluates form against stage-specific thresholds (Set-Up, Lifting, Lock-Out). 
  Feedback is generated via colored markers, text alerts, and text-to-speech (TTS) audio cues. Repetitions are logged as correct/incorrect based on joint alignment criteria.

  ## Technical Details
- **Frameworks**: MediaPipe (BlazePose), OpenCV 4.10.0, pyttsx3 (TTS).
- **Angle Calculation**: Uses geometric analysis of 3 keypoints per joint.

  ![Figure3](https://github.com/user-attachments/assets/63ba7c86-b73a-4577-a714-80dec89782ed)

- **Thresholds**: Criteria derived from professional deadlift videos, sports research, and trainer validation.
- **Performance**: Runs at **24–30 FPS** on a 13th Gen Intel i7-1355U CPU.

## Prposed System
The system successfully:
- Maintained tracking accuracy in varied environments (lighting conditions, complex backgrounds)
- Detected specific joint errors across all stages of the deadlift
- Provided appropriate stage-specific feedback
- Counted repetitions accurately, categorizing them as correct or incorrect
- Multi-modal feedback, combining visual elements such as colored markers on error joints, text,
  and audio (text-to-speech) instructional feedback to provide users with real-time.

  ![Figure4(Bottom Left)](https://github.com/user-attachments/assets/4d312e04-770f-4681-b8d2-c4f8c2516a53)
*Example of system*

  ## Future Work
1. **Occlusion Handling**: Predictive modeling for obscured keypoints.  
2. **Camera Alignment Tolerance**: Rotation matrices to compensate for misalignment.  
3. **Personalization**: Dynamic thresholds for body types/weight plates.  
4. **Feedback Optimization**: Prioritized audio delivery for simultaneous errors.

*Developed as part of agile research at the National Institute of Development Administration (NIDA), Thailand.*
