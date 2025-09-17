# lab02-debugging

Worked with Jackie & Logan.

[Shader is here!](https://www.shadertoy.com/view/wclBWf)

Bug 1: ln 97, vec uv2 = 2.0 * uv - vec2(1.0); => vec2
- Now we can see something compile!
Bug 2: ln 100, raycast(uv, dir, eye, ref); => uv2
- Instead of uv we should be using uv2 (figured this out since we weren't using uv2 anywhere and tried plugging in).
Bug 3: ln 11, x/x => x/y
- In raycast, we noticed that `H *= len * iResolution.x / iResolution.x;`. x/x? Let's try x/y!
Bug 4: ln 18, increase marching 64 => 128
- Noticed a 'black hole effect' around the spheres, let's try increasing the number in the for loop!
Bug 5: ln 75, reflection should be dir not eye
- `reflect` is incident vector and normal vector. The incident vector should not be `eye`, it should be `dir`!

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
