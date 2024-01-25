Abstract:

</br>

This work presents the development of a system focused on drowsiness detection in drivers based on certain biological features, whose purpose is to alert drivers to avoid road-side accidents.
</br>
Introduction:
Drowsiness, characterized as the condition of feeling sleepy and in need of rest, can lead to various symptoms that significantly affect task performance. These may include slowed response times, occasional lapses in awareness, and brief episodes of microsleeps (blinks lasting over 500 ms), among other manifestations. In essence, continuous tiredness can have similar effects to those caused by alcohol [3]. While driving, these symptoms can be life-threatening since they increase the likelihood of drivers missing exit signs, drifting into other lanes, causing an accident.  While alerting drowsy drivers is important, it is equally necessary to minimize the number of false alarms, which could be another fatal distraction.
In the context of this project, our fundamental concept is as follows: The design and development of eye and face recognition to detect features such as eye-blink rate, yawn rate and head-tilt position which are then passed into a multi-layer perceptron classifying whether a driver is awake or drowsy. Another approach of transfer learning is employed by training the pre-trained InceptionV3 model with additional layers for our particular task. The real-time video feed is sent to the pre-trained models to get a prediction score and if the driver has been flagged drowsy consistently for ten seconds, an alarm is rung. The two models are used as comparison for accuracy results along with a comparison of a hybrid approach of combining both the models.

</br>

The figure below shows the proposed model architecture:

</br>

<p align="center">
<img width="452" alt="Screenshot 2024-01-25 at 11 19 47 AM" src="https://github.com/guptaru1/DrowsinessDetection/assets/50961619/584bd69e-60ca-4236-bd0c-9d6ee6fb6161">
</p>

</br>

The figure below shows 6 consecutive real-time frames classification:

</br>


<p align="center">
<img width="576" alt="Screenshot 2024-01-25 at 11 21 04 AM" src="https://github.com/guptaru1/DrowsinessDetection/assets/50961619/56d6a27c-cd1f-47f0-b2e0-9391783f8048">
</p>

</br>

The figure below is a tabular view of sample test cases:

</br>
<p align="center">
<img width="546" alt="Screenshot 2024-01-25 at 11 22 44 AM" src="https://github.com/guptaru1/DrowsinessDetection/assets/50961619/d74c492a-5b12-4c41-87f9-a0724f451cec">
</p>
</br>

Conclusion & Challenges
</br>

This paper aimed to propose a novel solution to detecting drowsiness in a real-time scenario by using either a hybrid combination of pre-trained models or just one of a high accuracy pre-trained model. It can be concluded that the multi-layer perceptron performed exceptionally well in detecting drowsiness in a real-time camera feed.
The multi-layer perceptron had an accuracy of 94%,  however it failed to correctly classify images which had eyes closed with no head tilt. However, when the multi-layer model was used in detecting drowsiness from a real-time feed, it performed better than Inception. Inception indicates a lot of false positives, which in our case is not acceptable as sounding an alarm unnecessarily can be a distracting measure.
It can further be concluded that the models are sensitive to a lot of external factors such as ensuring the driver’s head stays within the frame, there is no hair covering the eyes, which might make it hard to implement in a real-life scenario.
For future work the dataset used to train the models should be expanded to consist of a mixture of videos and images since the end goal of the project was to detect drowsiness in a live stream. Apart from that, another method is to combine a deep learning model with fuzzy logic which helps minimize the number of false positives. Another aspect for future analysis is coming up with a good drowsiness threshold, which currently is set to 10 seconds. This work stands as a good baseline to incorporate the above future works.
