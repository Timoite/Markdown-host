
2025-11-20 11:51

Status: WIP

Tags: [[IIB]]


# Slide Outline for IIB project

## Slide 1: Project Title and Self Introduction


## Slide 2: Motivation & Industrial context

Hook the audience by saying:
1. Facial animation is a booming field in gaming and film, e.g. Unreal Metahuman and Flawless AI (show some picture)
2. While looking photorealistic, the intra-oral cavity (especially tongue) is often neglectedor requires manual artist labor
3. Goal: Automate this "inner-mouth" animation process to match the quality of "outer face" for better speech intelligibility

## Slide 3: The Current State

1. Blendshapes (linear combination of expression extremes) are standard to drive a face model right now, and we have dataset (BEAT) and face model (ICT-FaceKit) for this that fits a common standard called "ARKit". It's nice that we already have a standardised pipeline in this field
2. However, they lack explicit tongue information. When the mouth opens, we can see the tongue is actually moving with the jaw and never actually looks like it help producing any speech. (Picture of  vs an real face speaking, I hope I can find a )
3. Impact: loss of semantic information. (Showing a visual speech recognition result compared to actual speech)
	1. Theoretically hard to distinguish specific phonemes without tongue cues (e.g. /t/ vs /k/)

## Slide 4: Baseline Visual Speech Recognition

1. Using the BEAT dataset as a baseline
2. Present initial Word Error Rate (WER) results on the face-only animation
3. Constraint: Manage to say some difficulties working with this dataset (lack of inner mouth information, the quality of the data, etc)

## Slide 5: Approaches to Tongue Animation

1. Discuss our approach to the tongue animation
2. A detailed pipeline graph would be nice here (Charles)

## Slide 6: More Details on Tongue Animation...

1. Work on Armature, LBS, etc.
2. Way to evaluate it in early phase:
	1. Cross-section view on matplotlib animation and compare it with MRI data
3. Showing the tongue mesh with "Bones" highlighted, with deforming animation

## Slide 7: The Challenges During the Project

1. The acoustic model outputs normalized data, but the mesh requires specific geometric coordinates
2. Direct mapping fails because of scale and non-linearities

## Slide 8: Our Method: Optimizing Linguistically Meaningful Points

1. Instead of direct mapping, we use Optimization
2. Optimizaing the tongue position based on linguistically meaningful landmarks
3. Fitting the armature to predicted point of the inversion model

Speech Audio -> (denoising?) -> Inversion Model -> Keypoints -> Optimization Step -> Mesh Deformation

## Slide 9: Visual Validation of the Preliminary Results

1. Show a gif of the best rendered result of both tongue matches MRI data
2. Validation
3. with full face model (against a reference video would be nice)
4. Demonstrate how the integration/camera/lighting code works

## Slide 10: Evaluation Using VSR model

1. Run Visual Speech Recognition again on the combined model, we would expect a lower WER
2. If not, explain some reasoning (I hope I don't need to)
3. Metric: Can do some metric for special articulation like /t/ and /k/ for the optimised data? (Technically we need TextGrid to be available and we do hot optimization on the data, not by training a model additionally, so this worths a discussion)

## Slide 11: Next Step

1. SMIRK?





# Reference
