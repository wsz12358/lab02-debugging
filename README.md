# lab02-debugging

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)

- Team members: Shize Wei
- link: https://www.shadertoy.com/view/wclfDf
- bug1 is compilation error. I find it because there are errors in the shadertoy, so it is not hard to find them. I changed line 100 'vec' to 'vec2' to solve it.
- bug2 is what makes the camera seems dislocated. When I was going through all of the codes I find the uv2 unused in mainImage function, so I find the problem. I changed line 104 'uv' to 'uv2' to solve it.
- bug3 is the resolution proportion error. It is because of the sphere function is not problematic but what it looks like is an ellipse. It is probably a bug that causes the view stretch. I changed line 12 the second iResolution.x to iResolution.y.
- bug4 is caused by reflect function in line 78. I find it because the texture of all the objects are problematic: it is not a glassial texture, which means the second raycast is problematic because is can't correctly find the reflection. I changed line 78 to 'reflect(dir, nor)' to get the correct out raycast.
- bug5 is the black and white grids on the ground, the number mismatches what is in the video. I come to the answer when I realizes it is because those are too far from the screen got cliped by march algorithm, because the distance reaches the maximum that march algorithm can go. I simply changed the number of loop from 64 to 256.
