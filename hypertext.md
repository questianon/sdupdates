# SD Hypertextbook

## Preamble
This is a tutorial/commentary to guide a newcomer how to setup and use Stable Diffusion to its fullest. It's a pruned version of the [SD Goldmine](https://rentry.org/sdgoldmine)

## Contact
If you have questions or comments, contact me

Socials: 
Trip: questianon !!YbTGdICxQOw 
Discord: malt#6065
Reddit: u/questianon
Github: https://github.com/questianon
Twitter: https://twitter.com/questianon
Patreon: https://patreon.com/questianon
Ko-fi: https://ko-fi.com/questianon

## How to use this resource
The hypertextbook is ordered from surface-level content to deep level content. If you are a newcomer to Stable Diffusion, it's highly recommended to start from the beginning. If you need a resource that isn't listed here, check out the [Goldmine](https://rentry.org/sdgoldmine)

## Disclaimers/Warnings

1. As of right now, .ckpts, hypernetworks, embeddings, vaes, and scripts downloaded anywhere are not inherently safe. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet.
2. Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps.

## Chapters
- [Chapter 1: Getting Started](#getting-started)
	- [Prerequisites](#prerequisites)
	- [Instructions](#instructions)
	- [Hello Asuka](#hello-asuka)
	- [Updating](#updating)
- [Chapter 2: Troubleshooting](#troubleshooting)
- [Chapter 3: The Webui Pt.1](#webui-pt-1)
	- [Txt2img](#txt2img)
	- [Img2img](#img2img)
	- [Inpainting](#inpainting)
	- [Extra](#extras)
	- [PNG Info](#png-info)
	- [Extensions](#extensions)
- [Chapter 4: Prompting](#prompting)
	- [Txt2img Tips](#txt2img-tips)
		- [Syntax](#syntax)
		- [Txt2img Settings](#txt2img-settings)
	- [Img2img Tips](#img2img-tips)
	- [Inpainting Tips](#inpainting-tips)
- [Chapter 5: The Webui Pt.2](#webui-pt-2)
	- [Models](#models)
	- [Dreambooth](#dreambooth)
	- [Embeddings](#embeddings)
	- [Hypernetworks](#hypernetworks)
	- [VAE](#vae)
	- [Checkpoint Merging](#checkpoint-merging)
- [Chapter 6: Training](#training)
- [Chapter 7: Developments](#developments)
	- [NAI](#nai)
	- [Anything.ckpt](#anythingckpt)
- [Chapter 8: Modifications](#modifications)
- [Chapter 9: Common Questions](#common-questions)
- [Chapter 10: Resources](#resources)

## Getting Started
Stable Diffusion is easy to setup. It takes ~5 minutes to set up if you have all the files.

I highly personally recommend using the [NAI Speedrun](https://rentry.org/nai-speedrun) if this guide doesn't cover something yet, though any from [Goldmine: Getting Started](https://rentry.org/sdgoldmine#getting-started) should work

### Prerequisites (Windows + NVIDIA)
[**Git**](https://git-scm.com/download/win) 
- Activate option `Git from the command line and also from 3rd-party software`
- Activate option `Git from the command line and also from 3rd-party software` if you want to update through Command Prompt (what I do)
- Everything else is fine, change what you want

[**Python 3.10**](https://www.python.org/downloads/windows/) 
- Make sure `Add Python to environment variables`/`add to PATH` is enabled
- Everything else if fine, change what you want

Enough space on your computer (my install without models, which is pretty barebones, takes up 8 GBs)

A model. For this example, let's use NAI.ckpt (go to [Developments](#developments) for more information on what this is): 
Anonfiles: https://anonfiles.com/U5Acl7F0y2/Novel_AI_Hypernetworks_zip
Pixeldrain: https://pixeldrain.com/u/FMJ4TQbM
Torrent (only download `animefull-final-pruned` and `animevae.pt`:
``` python
magnet:?xt=urn:btih:5bde442da86265b670a3e5ea3163afad2c6f8ecc&dn=novelaileak&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2810%2Fannounce&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.openbittorrent.com%3A80%2Fannounce&tr=udp%3A%2F%2Fopentracker.i2p.rocks%3A6969%2Fannounce&tr=https%3A%2F%2Fopentracker.i2p.rocks%3A443%2Fannounce&tr=udp%3A%2F%2Ftracker.torrent.eu.org%3A451%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.pomf.se%3A80%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Fopen.stealth.si%3A80%2Fannounce&tr=udp%3A%2F%2Fopen.demonii.com%3A1337%2Fannounce&tr=udp%3A%2F%2Fmovies.zsw.ca%3A6969%2Fannounce&tr=udp%3A%2F%2Fipv4.tracker.harry.lu%3A80%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexodus.desync.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fbt.oiyo.tk%3A6969%2Fannounce&tr=https%3A%2F%2Ftracker.nanoha.org%3A443%2Fannounce&tr=https%3A%2F%2Ftracker.lilithraws.org%3A443%2Fannounce&tr=https%3A%2F%2Ftr.burnabyhighstar.com%3A443%2Fannounce
```

### Instructions
1. Open Windows Explorer and navigate to where you want AUTOMATIC1111's webui to be installed. The example directory for this tutorial will be `C:\webui` for simplicity. This is a dummy variable and should be changed to whatever your desired directory is
2. Right click anywhere in your desired directory (e.g. `C:\webui`) and select `Git Bash Here`. If this is missing, you didn't activate the option `Windows Explorer integration > Git Bash` when installing. Either change the option somehow or just reinstall Git
3. Type/paste `git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui` and click enter. Wait for the download to finish
4. Navigate to the stable-diffusion-webui-master\ folder where you should see a file named `webui-user.bat`. For this tutorial's example, this folder will be `C:\webui\stable-diffusion-webui-master\`
5. Navigate to `stable-diffusion-webui-master\models\Stable-diffusion` and place `model.ckpt` and `animevae.pt` in here
	- For now, rename them as follows:
		- `model.ckpt` --> `animefinal-full-pruned.ckpt`
		- `animevae.pt` or `model.vae.pt` --> `animefinal-full-pruned.vae.pt`
6. Run `webui-user.bat`

Everything's good to go when `Running on local URL: http://127.0.0.1:7860` is displayed. Open a web browser and type in `http://127.0.0.1:7860` to access your local SD install.

### Hello Asuka

The reason why we use NAI is because of the Asuka Test (similar to the `Hello World` test for programming)

1. Check the top left under the title `Stable Diffusion checkpoint` to see if `animefinal-full-pruned.ckpt` is there. If it's not, click the box and click `animefinal-full-pruned.ckpt`
2. Verify the files loaded correctly via the following messages in the console log:
	- `Loading weights [925997e9] from: [your directory here]\stable-diffusion-webui\models\Stable-diffusion\animefull-final-pruned.ckpt`
	- `Loading VAE weights from: [your directory here]\stable-diffusion-webui\models\Stable-diffusion\animefull-final-pruned.vae.pt`
3. Go to the `Settings` tab at the top
4. `Ctrl + F` and make the following changes:
	- Stop At last layers of CLIP model = 2
	- Eta noise seed delta = 31337
5. Click `Apply settings` at the top of the page and verify that the changes have been saved (it will say `2 settings changed`)
6. Go to the `txt2img` tab at the top
7. (Euler) Use the following in their respective fields:
	- Prompt: `masterpiece, best quality, masterpiece, asuka langley sitting cross legged on a chair`
	- Negative prompt: `lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts,signature, watermark, username, blurry, artist name`
	- Sampling Steps: `28`
	- Sampling Method: `Euler`
	- CFG Scale: `12`
	- Seed: `2870305590`

8. (Euler a, optional) This is if you really want to make sure your setup is correct:
	- Prompt: `masterpiece portrait of smiling Asuka \(evangelion\), evangelion \(Hideaki\), caustics, textile shading, high resolution illustration, blue eyes, contempt, feminine, woman disdain, disgust, no pupils, hair over face,orange hair, long hair, red suit, ilya kuvshinov`
	- Negative prompt: `nsfw, lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, headdress, loli,`
	- Sampling Steps: `28`
	- Sampling Method: `Euler a`
	- CFG Scale: `12`
	- Seed: `2870305590`
9. Click `Generate`

The following Asuka's should be generated within 95%-100% correctness:
- Euler a: https://i.imgur.com/j7DSvIS.png
- Euler: https://i.imgur.com/Bfl5qJB.png

If you have issues with your Asuka test, check out one of the following depending on which Asuka test you're recreating:
	- Asuka Euler: https://imgur.com/a/DCYJCSX
	- Asuka Euler a: https://imgur.com/a/s3llTE5

### Updating
Instructions:
	* If on Windows:
		1. navigate to the webui directory through command prompt or git bash
			a. Git bash: right click > git bash here
			b. Command prompt: click the spot in the "url" between the folder and the down arrow and type "command prompt". 
			c. If you don't know how to do this, open command prompt, type "cd [path to stable-diffusion-webui]" (you can get this by right clicking the folder in the "url" or holding shift + right clicking the stable-diffusion-webui folder)
		2. ```git pull```
		3. ```pip install -r requirements.txt```
	* If on Linux: 
		1. go to the webui directory
		2. ```source ./venv/bin/activate```
			a. if this doesn't work, run ```python -m venv venv``` beforehand
		3. ```git pull```
		4. ```pip install -r requirements.txt```

## Troubleshooting

Adding commands to your `commandline args` means to do the following:
1. Right click `webui-user.bat`
2. Click 'Edit'
3. Add your commands
4.  Save
Look at the first issue + solution for an example

- If you're running out of vram (memory), right click `webui-user.bat`, click 'Edit', and add " --med-vram " or " --low-vram " (remove the quotations) after 'set COMMANDLINE_ARGS=' in webui-user.bat. Choose the former if possible
- If you have a 16xx card, add " --precision full --no-half " (remove the quotations) to your commandline args in webui-user.bat
- If your outputs are randomly black, add " --no-half-vae " (remove the quotations) to your commandline args in webui-user.bat

## Webui Pt 1

** Note: Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps. **

To update your install,

### txt2img
The bread and butter of Stable Diffusion. You type stuff in and the AI generates stuff for you

- Prompt: Pushes the vectors in the positive direction every step  
- Negative prompt: Pushes the vectors in the negative direction every step  
- Sampling steps: Generally, more steps = more accurate. Exception: the "a samplers" (like `Euler a`) completely change after every ~20 steps.  
- Sampling method: Each one generates images differently. Test it out yourself to see which you like. For comparisons, check out the goldmine and search `comparisons`  
- Width and height: Output dimensions. The larger these are, the more vram is required  
- Restore faces: Restores faces using the `face restoration model` in `Settings`. You can also restore faces in the `Extras` tab if you don't want it to auto restore faces after your generation  
- Tiling: Meant for generations with patterns  
- Highres. fix: Only really useful for generations above 512x512. It breaks down the output resolution into 512x512 chunks, runs txt2img on each one, then combines them together through img2img (I believe). Very helpful in dealing with multiple people in the output image. SD v1.4 needs this since it was trained on 512x512. NAI doesn't really need this as it was trained on 768x768
	- Firstpass width/height: Will generate the initial chunks at this resolution. Most commonly left on 0x0  
	- Denoising strength: How much the output image will differ from the chunked input images. Play around with this to see what you like. I usually run ~0.3  
- Batch count: How many images to generate in total  
- Batch size: How many images to generate at a time. Speeds up it/s but uses more vram  
- CFG scale: How closely the AI should follow the prompt. Higher values can deepfry your output while lower values can make the AI ignore your prompt  
- Seed: Randomization, basically a Minecraft seed, -1 is to randomize  
- Extra: No one really uses these
	- Variation seed: Seed of a different picture to be mixed into the generation. Basically combines parts of seeds together 
	- Variation strength: How strong of a variation to produce. 0 = original image, 1 = variation image
	- Resize seed from width/height: Attempts to prdouce a picture similar to what would have been produced with the same seed at the specified resolution
- Script: Custom user scripts
- The paint emoji: Adds a random artist to the prompt from the artists.csv file in `\stable-diffusion-webui`
- The checkmark emoji: Read generation parameters from prompt or last generation if prompt is empty into user interface. Seems to take the last generation and put it's prompt + settings into the current UI
- The floppy disk emoji: Saves the current prompt as a style
- The clipboard emojiL Applies the selected styles to the current prompt
- Style 1 and 2: When you save a style, it saves your current prompt. Using a style just adds that prompt secretly (not sure if it's at the end or the beginning)  
- Send buttons: Sends your output to the desired location so you don't need to find it in your output folder and drag it back in  

### img2img
The peanut butter and jam of Stable Diffusiono

You can edit and generate similar images

- Just resize: Will resize output image to target resolution. You need to make your output width x height match your input's wxh
- Crop and resize: Will resize the output image so the entirety of the target resolution is filled with the image. Will crop parts that stick out
- Resize and fill: Will resize the output image so that the entire image is inside the target resoltuion. Will fill empty space with output image's colors
- Width/Height: The resolution of your output image. Make sure it matches your input unless you deliberately want to not make them match
- Denoising strength: How much of the original image should be respected by the algorithm. 0 = nothing changes while 1 = a completely unrelated image. Unless changed in the settings, values below 1 will take less steps than the `Sampling Steps` slider specifies
- Interrogate CLIP: Will try to generate a CLIP prompt out of your input image. For me, there seems to be a memory leak that breaks my Stable Diffusion after using it, so your mileage may vary.

### Inpainting
The butter knife of Stable Diffusion

You can edit/change parts of the image that you don't like

Note: The inpainting doesn't seemm to work with certain extensions active (I think adblock?). Use private browsing/incognito to circumvent this (unless you set your extensions to run in these windows)

- Where you paint is where the AI will look at to edit your input. We'll call this area the `paint`
- Mask blur: Blurs the area under the `paint`. Useful if you want the general colors of the content but want to change the details
- Draw mask/upload mask: You can draw a mask directly in the UI or upload one that you create from an image editor. An uploaded mask should be black and white, with black representing the original image and white representing the `paint`
- Inpaint masked/not masked: Whether to edit the area under the `paint` or edit everything else but the area under the `paint`
- Fill: Fills the area under the `paint` with colors of the image. Then, generates an image there based on the prompt
- Original: Pays attention to what was under the `paint` and edits it
- Latent noise: Converts the area under the `paint` into latent space noise. Requires a high denoising value
- Latent nothing: Fills it in with latent space zeros. Not too sure what this does to be honest
- Inpaint at full resolution: Creates a square bounding box that will enclose the edges of your inpaint and upscales it to the desired resolution. Then, does the inpainting process. Generally adds more details than inpainting without this option
- Inpaint at full resolution padding, pixels: Adds padding on the edge of this bounding box. Extremely helpful when you want the inpaint to take into account the surrounding context

### Extra
The extra butter of Stable Diffusion

You can do final edits to your generation

- Scale by: Resize your image using a multiplier and upscaler
- Scale to: Resize your image using a custom width x height and upscaler
	- Width/Height: The desired width/height of your output
	- Crop to fit: Will crop to fit
- Upscaler 1: Primary upscaler. Has different upscalers that will upscale your image in different ways. Some require more vram than others. Test to see which you like. Since the last time I used it, I like LDSR and ESRGAN_4x
- Upscaler 2: Secondary upscaler
- Upscaler 2 visibility: How much the secondary upscaler should be visible in the upscaling process
- GFPGAN visibility: Face restoration model. I use this a lot
- CodeFormer visibility: Face restoration model
- CodeFormer weight: How strong CodeFormer should be. 0 = maxmium effect, 1 = minimum effect
- Upscale before restoring faces: Will upscale before restoring faces

### PNG Info
The cookbook of Stable Diffusion

You can upload a generated image here. The webui will read its exif data if it has any. Clicking `Send to X` will send the exact prompt and settings you see to the desired location. This is extremely helpful if you want to recreate an image without having to type everything in

### Extensions
The appliances of Stable Diffusioon

You can download addons to your Stable Diffusion download here

- Installed: What you have installed
- Available: Available extensions for download
	- Load from: What repo to get the prompts from. The default is good
	- Hide extensions with tags: Will hide extensions with the marked tags. I hate ads, so I have the ads tag marked

Recommended (ones I personally use):
- SD-latent-mirroring: Fun, gives symmetry
- a1111-sd-webui-tagcomplete: Useful if using Danbooru models (like NAI). Provides autocomplete to your prompts
- sd-dynamic-prompts: Wildcard extension. Helpful if you want randomization of things like clothes without thinking about it

## Prompting
This section will cover all the areas from [Chapter 3](#the-webui-pt1)

Honestly, prompting is very trial and error. Go here for a complete tutorial on prompting: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#prompt-editing. This section is for a few select settings

Here are some tips if you're just starting out. Anything can be changed as you wish

### Txt2img Tips

#### Syntax
- Positive: Add `masterpiece, best quality` to the beginning of all your prompts
	- This is NovelAI's default positive
- Negative: Add `lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry` to your negatives
	- This is NovelAI's default negative
- Emphasis: You can add emphasis using the following syntax: `(prompt here:multiplier)`
	- Example: `1girl, yellow hair, (beautiful eyes:1.2), (flowing hair), ((smiling)), (dark aesthetic:0.25), [bloom], [[particles]]`
		- In this case
			- `beautiful eyes` will have its strength multiplied by 1.2
			- `flowing hair` will have its strength multiplied by 1.1
			- `smiling` will have its strength multiplied by 1.21 (1.1 * 1.1)
			- `dark aesthetic` will have its strength reduced by a factor of 4 (1 / 0.25)
			- `bloom` will have its strength reduced by a factor of 1.1
			- `particles` will have its strength reduced by 1.21 (1.1 * 1.1)
	- The conversion of syntax from NovelAI to AUTOMATIC1111's webui is as follows:
		- {word} = (word:1.05)
		- {{word}} = (word:1.1025)
			- 1.05 * 1.05 = 1.1025
		- [word] = (word:0.952)
			- 1 / 1.05 - 0.952
		- [[word]] = (word:0.907)
			- 1 / 1.05 / 1.05 = 0.907
- You should order your prompt from most to least important and using categories since that's how the AI processes your prompt
	- Example order: `(general positives), (descriptors of subject), (descriptors of background), (post-processing, camera, etc.)`
		- Example (might be bad): `masterpiece, best quality, 1girl, solo, portrait, beautiful, smiling, red flowing hair, sparking eyes, wearing a dress, bright sunny background, bloom, world theater masterpiece, particles, bokeh effect`
- You can go above 75 tokens. The webui will pad the last 20-ish tokens with blank tokens if this happens (unless this was changed in the settings). When the 76th token is reached, the weights reset.
	- Example: 1girl (1), apple (2), ..., banana (54), grapes (55), pear (56), mango (57) ... , orange (74), plum (75), tangerine (1) --> the last 20 tokens are padded --> banana (54), grapes (55),,,,,,,,,,,,,,,,,,,, pear (1), mango (2)
		- 1girl will have the most focus, pear will have the most focus
- AND statements: Prompts two separate prompts at once and combines them 
	- The easiest way to visualize what this does and create appropraite prompts is as follows: 1girl AND apple
		- 1girl (1), apple (2), 1girl (3), apple (4)
			- 1girl is prompted for and produced by the AI in step 1, apple in step 2, 1girl in step 3, etc.
	- Specify locations for things so they don't get combined
		- Example: 1girl standing on grass in front of castle AND castle in background
			- This will create a girl standing in front of a castle and a castle that is conveniently in the background
- Prompt Editing: Allows you to start generating one picture but switch midway
	- Example: `a [red:blue:10] sky` will generate `a red sky` for 10 steps and swap to `a blue sky` for the remaining steps
	- Example: `a [red:blue:10] sky` will generate `a red sky` for half the total steps and swap to `a blue sky` for the remaining steps
	- Example for 100 steps: `beach with [oak:palm:0.25] trees and a [red:blue:0.5] sky, [masterpiece: by Greg Rutkowski:65]`
		- Start: `beach with oak trees and a red sky, masterpiece`
		- After step 25: `beach with palm trees and a red sky, masterpiece`
		- After step 50: `beach with palm trees and a blue sky, masterpiece`
		- After step 65: `beach with palm trees and a blue sky, by Greg Rutkowski`
- X/Y Plot: Useful if you want to test multiple settings without having to change it manually and generate another image

#### Txt2img Settings
- Samplers: Use the DPM++ samplers for general prompting. These require far fewer steps while producing good outputs (~8-10 steps are required)
- Width/Height: Make the height bigger than the width if you plan to do portraits. Do the opposite if you plan to do landscapes. In any case, if you go above 512px in any direction, you should use Hires fix (though you might not need it)

### Img2img Tips
- The higher the denoising, the less related the original image is to the final image
- Scripts --> SD Upscale: Really good tool to add detail that can be used instead of an upscaler
	- The input image is broken down into tiles (size of the tiles is specified by the width x height) and ran through img2img. The output image is doubled in size, meaning the size of the tiles matters due to overlapping tiles
		- Ex: a 512x512 input image needs 9 512x512 tiles but only 4 640x640 tiles		
	- Example prompt to use: `detailed, high quality`

### Inpainting Tips
Recommended guide (NSFW): https://rentry.org/inpainting-guide-SD

- I recommend to always use `Inpaint at full resolution` for more details
- The more an object to be inpainting requires context, the more padding you should add
	- If not using `Inpaint at full resolution`, use the brush to paint extra space outside of the desired inpainting region

## Webui Pt 2
This section covers more advanced stuff for the webui

** Note: As of right now, .ckpts, hypernetworks, embeddings, vaes, and scripts downloaded anywhere, including here, are not inherently safe. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet. **

### Models
The models you use determine what the AI "knows" and can generate

For a comprehensive list, check out: https://rentry.org/sdmodels and https://rentry.org/sdgoldmine

Prominent models:
- SD v1.4: A model trained by the original creators of Stable Diffusion. Trained on billions of images
	- Repo: https://huggingface.co/CompVis/stable-diffusion-v1-4
	- Many derivative models are trained on this
- SD v2.0: An updated model trained by StabilityAI. Supposedly an upgrade to SD v1.4
	- Repo: https://huggingface.co/stabilityai
- NAI: A model trained by NovelAI. Primarily trained on anime from Danbooru
	- The most popular model for anime
- Waifu Diffusion: A model trained on anime from Danbooru

### Dreambooth
Dreambooth is a training method to train extra data into a model

Find a bunch here:
https://rentry.org/sdgoldmine
https://huggingface.co

Pros:
- Generally good for everything
- Pretty quick to train

Cons:
- Large in filesize
- Requires at least 8gb of vram to train (and even then, 8gb is iffy)

### Embeddings
Textual inversion generates embeddings. Textual inversion is a training method that finds the most relevant tags to create the input images

Find a bunch here:
https://rentry.org/sdgoldmine
https://huggingface.co

Note: .bin files are .pt files

Use: To use embeddings, place them in `[your directory]\stable-diffusion-webui\embeddings`. To invoke them when prompting, simply type the name of your embedding.
- Example: If your embedding is named `power.pt`, typing `power` in the prompt will invoke the embedding
- You can rename the embedding

Pros:
- Really small filesize (<1MB)
- Easy to share (.pt and images)
- Easily combinable with other embeds
- Good

Neutral:
- Might or might not be good. It varies depending on who you ask

### Hypernetworks
Hypernetworks filter the outputs of images

Find a bunch here:
https://rentry.org/sdgoldmine

Use: To use hypernetworks, place them in `[your directory]\stable-diffusion-webui\models\hypernetworks`. To invoke them, go to the `Settings` tab --> `Hypernetwork`
- You can edit its strength by editing `Hypernetwork strength` in `Settings`

Pros:
- Small filesize (~100MB)
- Easy to share
- Good

Neutral:
- Not much is known about training these well. Check out https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017for an up to date discussion on them
- Might or might not be good. It varies depending on who you ask

### VAE
VAEs filter the output of images and adds small changes

Use: To use VAEs, place them into `\stable-diffusion-webui\models\VAE`. Or, rename them to `[your model name].vae.pt` and place them into `\stable-diffusion-webui\models\Stable-diffusion`. Head over to `Settings` --> `SD VAE`

Known VAEs:
- StabilityAI: https://huggingface.co/stabilityai
	- Most people recommend this one specifically: https://huggingface.co/stabilityai/sd-vae-ft-mse-original/tree/main
- NovelAI's VAE
	- Popular VAE
- Trinart's VAE: https://huggingface.co/naclbit/trinart_characters_19.2m_stable_diffusion_v1
- SD 1.4 Anime Styled by WD dev: https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime.ckpt

### Checkpoint Merging
You can combine checkpoints (models) togther here. As of right now, it's a destructive process that breaks some of the model's "neurons", but can produce great results.

Weighted Sum: Standard mixing
- Primary Model (1 - Multiplier) + Secondary Model * Mutliplier
- A (1 - M) + B * M
- Multiplier: 0 = A, 1 = (B - C)

Add Difference: Mixes the difference between two models and a primary model
- Primary Model * (Secondary Model - Tertiary Model)
- A * (B - C)
- Multiplier: 0 = A, 1 = (B - C)
- (B - C) takes the "neurons" from `C` and subtracts them from `B`

Save as float16: Check the common questions

Prominent Merges:
- Berry Mix: The original "mix" that spawned the other fruit mixes

## Training
Training is a very experimental area right now. 

### Models
I don't train models, so try following this guide: https://rentry.org/informal-training-guide

### Dreambooth
Here's HuggingFace's official guide, which may or may not be good: https://huggingface.co/blog/dreambooth  
Here's another guide: https://github.com/d8ahazard/sd_dreambooth_extension

### Embeddings
Here's the official guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Textual-Inversion

### Hypernetworks
Find the most up to date resources for hypernetworks here: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017  
Find a simple guide here: https://rentry.org/hypernetwork4dumdums

## Developments
This covers important events that you should know about

NovelAI leak (refered to as NAI in this guide): NovelAI trained a really good closed source model on millions of Danbooru images. People got peeved that it was closed source and someone leaked it. This brought the following improvements to Stable Diffusion
- Hypernetworks: Filters to outputs
- Aspect Ratio Bucketing: Better cropping for training
- A model that was really good (no need for heavy prompting)

Anything.ckpt: A Chinese group continued training on NAI to produce images that seemed even better (at least the portrait ones). You can find download links at https://rentry.org/sdgoldmine and https://rentry.org/NAI-Anything_v3_0_n_v2_1

## Modifications
For a complete list: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings

Prominent optional commandline args:
- `--xformers` enables xformers for cross attention layers. Generally boosts it/s
- `--deepdanbooru` enables deepdanbooru for AUTOMATIC1111's webui. It's basically the CLIP interrogator except using Danbooru tags. Very helpful when tagging datasets or finding tags that make an image

Prominent optional settings:
- `Enable quantization in K samplers for sharper and cleaner results. This may change existing seeds. Requires restart to apply.` should be turned on

## Common Questions
This will be populated as I find/get more questions to answer

What is float16/fp16?: Float16 significantly reduces the size of models by using estimations. 16xx cards have issues with these estimations, which is why they need to have `--precision full --no-half`

## Resources
News: https://rentry.org/sdupdates, https://rentry.org/sdupdates2, https://rentry.org/sdupdates3
Goldmine (Literally everything): https://rentry.org/sdgoldmine