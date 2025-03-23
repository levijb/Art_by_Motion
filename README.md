# Art_by_Motion

# Motavation
## I recently went to a visual muesum that had 5 interactive art exhibited. One was controlling moving balls on the screen by moving your arms and another 
## was supposed to crate a poem stanza based on a body-movement controlled postive-negative axis and a litaral-absract axis. Only 2 out of 5 exhibits worked as intended, and all were very rudementary. \
## I haven't been following this space closely, but I'm  confident I can build something better with just my laptop camera. Eventaully I'd like to incorporate EMG hand signals into art creation.

## Project Outline
Startup

    Launch main.py.
    Program checks GPU availability (e.g., torch.cuda.is_available() or relevant library check).
    Program initiates webcam feed (OpenCV).

Calibration

    Display an overlay: “Position your face and torso within the frame.”
    Wait until face detection is stable for ~2 seconds.

Real-Time Loop

    Capture a frame from OpenCV.
    Convert to RGB, pass to MediaPipe (or chosen library).
    Extract keypoints for arms, hands, face.
    If in single-motion mode:
        Classify gesture in real time. Print recognized gesture if confidence is high.
        Show top 4 predictions. Offer override with head nod.
    If in multi-motion mode:
        Aggregate recognized gestures into a list until user confirms the chain with a nod or a separate gesture.
    Check if the user “tongue out” gesture is detected. If so, toggle single ↔ multi mode.
    Display outputs over the video feed.
    Delay or proceed to the next frame in real time (aim for 15–30 fps or higher).

Shut Down

    On user’s command (e.g., press ‘q’), release the webcam and close the UI.
