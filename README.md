# SD Updates (3)
->Only news here<-
->Find downloads and links here: https://rentry.org/sdgoldmine<-
->Old stuff here https://rentry.org/sdupdates2 and here https://rentry.org/sdupdates<-

!!! danger Warnings: 

	1. Ckpts/hypernetworks/embeddings and scripts downloaded from here are ==not== interently safe as of right now. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet.

	2. Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps.

All rentry links are ended with a '.org' here and can be changed to a '.co'. Also, use incognito/private browsing when opening google links, else you lose your anonymity / someone may dox you

## Contact

If you have information/files (e.g. embed) not on this list, have questions, or want to help, please contact me with details

Socials: 
Trip: questianon !!YbTGdICxQOw 
Discord: malt#6065
Reddit: u/questianon
Github: https://github.com/questianon
Twitter: https://twitter.com/questianon)

!!! note Don't forget to git pull to get a lot of new optimizations + updates, if SD breaks go backward in commits until it starts working again
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
		
!!! info

	**Notable upcoming events:**


	**Waifu Diffusion v1.4 is coming out on December 26th**
	* WD 1.4 information provided to me:
		* New Deepdanbooru for better tagging (prerelease right now)
		* much better hands - look at 'Cafe Unofficial Instagram TEST Model Release' for a sample of what it can do in an unfinished model
		* Trained off SD 1.5
		* Creator: "In terms of general flexibility of being able to prompt a wide range of things, wd1.4 should be better than everything" (planned to supercede all current models, including NAI and anything.ckpt, to the point where you don't need to merge)
		* Creator: "we may create our own version of hypernetworks and create fine tunes for anime and realistic styles"
		* Creator: the instagram model training includes improvements such as:
			1. dynamic image aspect training (as in we trained images with ZERO cropping, the entire image is fed into SD all at once, even if it's landscape or portrait)
			2. unconditional training such that the model can somewhat self improve
			3. higher resolutions during training (640x640 max)
			4. much faster training code (6-8x performance increase)
			5. better training hyperparameters
			6. automated blip captioning of all images
		* Dataset and associated tags will be public
		* Haru and Cafe came up with a temporary plan that may be able to drastically improve the performance of clip without having to retrain clip from scratch, though it'll have to happen after wd1.4
		* to prevent bleed from the images, each source will have a tag associated with it in the caption data when fed into SD		
		
>11/26 to 12/12
- Goldmine is being reorganized and curated, update will come out when it looks organized
- Update your AUTOMATIC1111 installation for a lot of fixes + features
	- Notable updates I can find:
		- Adding --gradio-inpaint-tool and color-sketch: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/5cd5a672f7889dcc018c3873ec557d645ebe35d0
		- Safetensors merged: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4930
			- To enable SafeTensors for GPU, the `SAFETENSORS_FAST_GPU environment` variable needs to be set to `1`
			- Batch conversion script is in the PR
			- Convert: https://huggingface.co/spaces/safetensors/convert
		- A bunch of UI updates/fixes
		- Proper SD 2.0 support (primary commit linked): https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/ce6911158b5b2f9cf79b405a1f368f875492044d
		- Improvements for various tools (like upscalers)
- (forgot to put this ever since it was created, but it's really good) InvokeAI, an all-in-one alternative to Automatic1111's webui, is updated with a lot of stuff: https://github.com/invoke-ai/InvokeAI
	- InvokeAI needs only ~3.5GB of VRAM to generate a 512x768 image (and less for smaller images), and is compatible with Windows/Linux/Mac (M1 & M2).
	- Has features like: UI Outpainting, Embedding Management, a unified (infinite) canvas, and an image viewer
	- Very user friendly (simple UI) and super easy to install (1-clicK)
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/zabmht/invokeai_22_release_the_unified_canvas/
- Unstable Diffusion reaches $25000 kickstarter goal for further training of SD 2.0
	- https://www.kickstarter.com/projects/unstablediffusion/unstable-diffusion-unrestricted-ai-art-powered-by-the-crowd
	- Goals:
		- Community GPU Cloud: researchers and community model makers can request compute grants and train their own models and datasets on our system, provided they will release the results open source
		- Further training using more steps and images
		- Only filtered out children to prevent misuse
- Stable Diffusion v2.1 released: https://stability.ai/blog/stablediffusion2-1-release7-dec-2022
	- https://huggingface.co/stabilityai/stable-diffusion-2-1
	- Reduced the strength of filters to allow for generating better people
- LORA - Low-rank Adaptation for Fast Text-to-Image Diffusion Fine-tuning space (based on the github from below): https://huggingface.co/spaces/ysharma/Low-rank-Adaptation
	- Dreambooth at twice the speed
	- Super small model file sizes (3-4MB)
	- Supposedly better than full fine-tuning according to author of the linked space
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/ziwwzh/lora_dreambooth_web_ui_finetune_stable_diffusion/
- Dreambooth on 6 GB VRAM and under 16 GB RAM released (LORA from above): https://github.com/cloneofsimo/lora
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/zfqkh3/we_can_now_do_dreambooth_on_a_gpu_with_only_6gb/
	- How to run on Windows natively without WSL (uses similar steps to linked guide): https://www.reddit.com/r/StableDiffusion/comments/ydip3s/guide_dreambooth_training_with_shivamshriraos/
- StableTuner, a GUI based Stable Diffusion finetuner, released: https://github.com/devilismyfriend/StableTuner
	- Easy to install and use, friendly GUI, and all-in-one finetuner/trainer
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/zd3xut/stabletuner_a_nononsense_powerful_finetuner_with/
- openOutpaint released: https://github.com/zero01101/openOutpaint
	- Open source, self-hosted, offline, lightweight, easy to use outpainting for AUTOMATIC1111's webui
	- Guide: https://github.com/zero01101/openOutpaint/wiki/SBS-Guided-Example
	- Manual: https://github.com/zero01101/openOutpaint/wiki/Manual
	- Reddit (has more features listed in comments): https://www.reddit.com/r/StableDiffusion/comments/zi2nr9/openoutpaint_v0095_an_aggressively_open_source/
- OpenAI releases ChatGPT, a language model for dialogue (info in the link): https://openai.com/blog/chatgpt/
	- Demo (requires account): https://chat.openai.com/	
- Automatic1111 adds support for SD depth model
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/zi6x66/automatic1111_added_support_for_new_depth_model/
	- Instructions on how to use by reddit user: 
		1. Download https://huggingface.co/stabilityai/stable-diffusion-2-depth (model) and place it in models/Stable-diffusion
		2. Download https://raw.githubusercontent.com/Stability-AI/stablediffusion/main/configs/stable-diffusion/v2-midas-inference.yaml (config) and place it in the same folder as the checkpoint
		3. Rename the config to 512-depth-ema.yaml
		4. Start Stable-Diffusion-Webui, select the 512-depth-ema checkpoint and use img2img as you normally would.
- depthmap2mask extension released that can create 3d depth map masks --> supposedly better img2img
	- Seems to be an alternative to conditioning image mask weight
- Dreambooth training based on Shivam's repo extension updated to support SD v2.0 (find it in the extensions tab)
- Script to convert diffusers models to ckpt and (vice versa?) released: https://github.com/lawfordp2017/diffusers/tree/main/scripts
- AUTOMATIC1111 webui now on HuggingFace: https://huggingface.co/spaces/camenduru/webui
- Pickle Scanner GUI updated: https://github.com/diStyApps/Stable-Diffusion-Pickle-Scanner-GUI
- Dream Textures (Stable Diffusion for Blender) demo: https://twitter.com/CarsonKatri/status/1600248599254007810
	- Github: https://github.com/carson-katri/dream-textures
	- Reddit: https://www.reddit.com/r/StableDiffusion/comments/zf2b9k/absolutely_crazy_addon_in_blender_to_add_textures/
- Stable Diffusion IOS app  released: https://www.reddit.com/r/StableDiffusion/comments/z5ndpw/i_made_a_stable_diffusion_for_anime_app_in_your/
	- Offline?
	- App Store: https://apps.apple.com/us/app/waifu-art-ai-local-generator/id6444585505
- Simple Dreambooth training (but costs money) service released: https://openart.ai/photobooth
- All in one Stable Diffusion server (costs money but seems cheap and easy to use) released: https://rundiffusion.com/
	- https://www.reddit.com/r/StableDiffusion/comments/zea5rd/thank_you_to_all_the_alpha_testers/
- Waifu Diffusion 1.4 is delayed to Dec 26 due to a database issue (not SD 2.0)

>11/25+11/26
- My SD Hypertextbook, a tutorial that teaches a newcomer how to install and use Stable Diffusion, is released: https://rentry.org/sdhypertextbook
- SD 2.0 has support in AUTOMATIC1111's webui: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/ce6911158b5b2f9cf79b405a1f368f875492044d
- (Reupload with new info) Pull request to support safetensors, the unpickleable and fast format to replace pytorch: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4930
	- Git checkout this commit
	- Convert your models locally: read the PR's first comment 
	- Convert your models in the cloud: https://colab.research.google.com/drive/1YYzfYZEJTb3dAo9BX6w6eZINIuRsNv6l#scrollTo=ywbCl6ufwzmW
		
>11/24
* SD Training Labs is going to conduct the first global public distributed training on November 27th
	* Distributed training information provided to me:
		* Attempted combination of the compute power of over 40+ peers worldwide to train a finetune of Stable Diffusion with Hivemind
		* This is an experimental test that is not guaranteed to work
		* This is a peer-to-peer network.
			* You can use a VPN to connect
			* Run inside an isolated container if possible
			* Developer will try to add code to prevent malicious scripting, but nothing is guaranteed
		* Current concerns with training like this:
			* Concern 1 - Poisoning: A node can connect and use a malicious dataset hence affecting the averaged gradients. Similar to a blockchain network, this will only have a small effect on the averaged weights. The larger the amount of malicious nodes connected, the more power they will have on the averaged weights. At the moment we are implementing super basic (and vague) discord account verification. 
			* Concern 2 - RCE: Pickle exploits should not be possible but haven't been tested. 
			* Concern 3 - IP leak & firewall issues: Due to the structure of hivemind, IPs will be seen by other peers. You can avoid this by seting client-only mode, but you will limit the network reach. IPFS should be possible to be used to avoid firewall and NAT issues but doesn't work at the moment
* Unstable Diffusion launching Kickstarter on December 9th to fund the research and development of AI models fine-tuned and trained on extremely large datasets specifically curated on NSFW
	- https://discord.com/channels/1010980909568245801/1011042718853648526/1045519049955749898
* Current implementations (WIP or not) of getting SD V2 on AUTOMATIC1111's webuiL
	- https://gist.github.com/toriato/3d1b2da54ef15c100e8996dd546da825
	- Pull request: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/5011#issuecomment-1326384199
	- https://github.com/uservar/stable-diffusion-webui/commits/dev2
- Harem generator released: https://github.com/Extraltodeus/multi-subject-render
	- Generates multiple complex subjects on a single image all at once
- New Stable Diffusion trainer released: https://github.com/CCRcmcpe/scal-sdt
	- Meant as a replacement for https://github.com/CCRcmcpe/diffusers
	- "Developed in parallel to https://github.com/Mikubill/naifu-diffusion, but I focus more on training in local environment instead of hivemind"
* **SD V2 released: https://stability.ai/blog/stable-diffusion-v2-release**
	- https://www.reddit.com/r/StableDiffusion/comments/z36mm2/stable_diffusion_20_announcement/
	- Stable Diffusion 2.0: An all-new text-to-image model trained with a brand new text encoder OpenCLIP, greatly improving the quality of generated images relative to earlier V1 releases
		- Trained from scratch using OpenCLIP-ViT/H text encoder that generates 512x512 images, with improvements over previous releases (better FID and CLIP-g scores)
	- Updated Inpainting Diffusion: A new text-guided inpainting model fine-tuned on Stable Diffusion 2.0
	- Upscaler Diffusion: Enhance image resolution by 4x while preserving fine details
	- depth2img: A variant image-to-image model focused on the overall structure and shape of input images, allowing you to radically change up the contents of your images without altering their composition
		- Infers the depth of input images --> better img2img (preserved coherence)
		- Seems like it's similar to Midjourney's "remix" feature
		- This model is conditioned on monocular depth estimates inferred via MiDaS and can be used for structure-preserving img2img and shape-conditional synthesis
	* Trained on 512x512 and 768x768 --> can generate images at these resolutions by default
		- For 768x768, the model was fine-tuned to generate 768x768 images, using v-prediction
	* Combined with the upscaler, you can generate images of at least 2048x2048 by default. It's recommnended to install Efficient Attention (https://github.com/facebookresearch/xformers)
	* Trained on an aesthetic subset of the LAION-5B dataset created by the DeepFloyd team at Stability AI, **which is then further filtered to remove adult content using LAION’s NSFW filter**.
	* Optimized to run on one GPU
	* Model is released under a revised "CreativeML Open RAIL++-M License" license
	* Download: https://huggingface.co/stabilityai
	* Github: https://github.com/Stability-AI/stablediffusion
	* Emad's statement: https://discord.com/channels/1002292111942635562/1002292398703001601/1045151904767942818
	* Twitter: https://twitter.com/StabilityAI/status/1595590319566819328?t=PXgar920uu4SnCOSjx0Mkw&s=19
	* Current implementations of Stable Diffusion need to have their code edited to support SD v2. It shouldn't be too hard to implement according to Emad

	- Running SD 2.0:
	`python scripts/txt2img.py --prompt "a professional photograph of an astronaut riding a horse" --ckpt <path/to/model.ckpt/> --config <path/to/config.yaml/>` 
	Example: `python scripts/txt2img.py --prompt "a professional photograph of an astronaut riding a horse" --ckpt <path/to/768model.ckpt/> --config configs/stable-diffusion/v2-inference-v.yaml --H 768 --W 768 `
	Another example: `python3.10 txt2img.py --prompt "woman showing her hands" --ckpt ../stable-diffusion-2/768-v-ema.ckpt --config configs/stable-diffusion/v2-inference-v.yaml --H 768 --W 768`

	- Rudimentary support on AUTOMATIC1111's webui: https://github.com/MrCheeze/stable-diffusion-webui/commit/069591b06bbbdb21624d489f3723b5f19468888d
	- Free tier colab (didn't test): https://colab.research.google.com/drive/1YPFfjFC2NFm0nIxNHXm4fVsxmGPsf38S?usp=sharing
	- Local (didn't test): https://github.com/AmericanPresidentJimmyCarter/stable-diffusion
	- Discord bot (didn't test): https://github.com/AmericanPresidentJimmyCarter/yasd-discord-bot
- StabilityAI solves legal problems --> it's possible there will be more frequent news and releases: https://discord.com/channels/1002292111942635562/1002292112739549196/1045158750631243786
	- https://www.reddit.com/r/StableDiffusion/comments/z37ke7/emad_just_said_on_discord_that_it_is_possible/
- Completely A.I. generated webcomic: https://globalcomix.com/c/paintings-photographs/chapters/en/1/4
	- https://www.reddit.com/r/StableDiffusion/comments/z2qkyj/i_created_a_completely_aigenerated_webcomic_over/
- Another pickle scanner released: https://www.reddit.com/r/StableDiffusion/comments/z2zu2x/keep_yourself_safe_when_downloading_models_pickle/
	- GUI repo: https://github.com/diStyApps/Stable-Diffusion-Pickle-Scanner-GUI
	- Windows app: https://github.com/diStyApps/Stable-Diffusion-Pickle-Scanner-GUI/releases/download/v0.1.0/distys-Stable-Diffusion-Pickle-Scanner-GUI.v0.1.0.zip
	- original repo: https://github.com/mmaitre314/picklescan

>Rest of 11/22 + 11/23
* Emad Q&A on 11/24: https://discord.gg/TeTtZGTq?event=1045032204557897768 
* NULL-text inversion for editing real images using guided diffusion models (AKA convert an image into latent space and edit it): https://github.com/thepowerfuldeez/null-text-inversion
	* https://www.reddit.com/r/StableDiffusion/comments/yyqufb/nulltext_inversion_for_editing_real_images_using/
* First multilingual text2image model released: https://huggingface.co/sberbank-ai/Kandinsky_2.0
* Improving Addam's second-order approximation: https://twitter.com/_clashluke/status/1594327381317419010
* Lightweight library to accelerate Stable-Diffusion, Dreambooth into fastest inference models with one single line of code: https://github.com/VoltaML/voltaML-fast-stable-diffusion
* New sampler pull request (DPM++ SDE): https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4961
* Extension that patches hypernetwork training released: https://github.com/aria1th/Hypernetwork-MonkeyPatch-Extension
	* Related PR: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4965
* Better, easier, and faster(?) training discussion: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/4940
* Animus's premium models got leaked (not sure if safe): https://rentry.org/animusmixed
* (update) pickle inspector has a script now and a stable diffusion whitelist: https://github.com/lopho/pickle_inspector/blob/main/README.md
* Midjourney x Spellbrush creates https://nijijourney.com/ (midjourney but anime)
		
>11/19 (continued) + 11/20 + 11/21 + some of 11/22
* Someone took sdupdates6. I stopped at sdupdates5. I only own sdupdates, 2, 3, 4, 5, and goldmine, 2, and 3. Anything else is fake
* (Not sure if implemented) Textual inversion training is implemented incorrectly in AUTOMATIC1111's webui, the original authors edited something that allowed for better training in less time (someone reported 4 vectors, 30 images, Learning Rate 0.1, and 30 steps of training on a 3090 was enough for a good embedding): https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4680
	* Another pull request: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4886
	* Related PR for hypernetworks: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4509
* Pull request to support safetensors, the unpickleable and fast format to replace pytorch: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4930
	* Another: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4869
* HuggingFace and Pytorch collaborated to make transformer based models faster using optimum library: https://twitter.com/huggingface/status/1594783600855158805
	* https://twitter.com/PyTorch/status/1594766050851102720
	* Docs: https://huggingface.co/docs/optimum/bettertransformer/overview
* SceneComposer: Any-Level Semantic image Synthesis releasd (basically prompting but it puts the things where you actually want it) by John Hopkins University and Adobe: https://zengyu.me/scenec/
	* Text -> mask the area you want with the level of "precision" (coarse to fine) -> draws the stuff where you want it -> can further refine with more masks (watch the demo to see an example)
	* Demo: https://zengyu.me/scenec/resources/demo_video.mp4
	* Git: https://github.com/zengxianyu/scenec
	* Paper: https://arxiv.org/abs/2211.11742
* Magic3D (Text to 3D) by NVIDIA released: https://deepimagination.cc/Magic3D/
	* Creates 3D mesh models using text
* Pure pytorch implementation of deepdanbooru released: https://github.com/AUTOMATIC1111/TorchDeepDanbooru
	* AUTOMATIC1111 debating wheter to remove tensorflow version from webui or keep both in. He prefers the former
* Extension to test phrase similarity in AUTOMATIC1111's webui released: https://gitlab.com/azamshato/simula
* (Added related extension) CLIPSeg demo (text-based inpainting): https://huggingface.co/spaces/nielsr/text-based-inpainting
	* Txt2mask (current webui extension): https://github.com/ThereforeGames/txt2mask
* (recently updated) Prompt travel: https://github.com/Kahsolt/stable-diffusion-webui-prompt-travel
* Accelerate launch implemented: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4527
	* https://huggingface.co/docs/accelerate/index
* Upload to 4chan with a prompt automatically: https://rentry.org/promptchan
* Anime NYK and Anime LA ban AI art: https://www.artnews.com/art-news/news/anime-conventions-ban-ai-art-1234647165/

>11/19
* AUTOMATIC1111 webui updated, git pull to update for fixes + some new features
	* Updates: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commits/master
* (From yesterday, fixed the image) AltDiffusion released: https://huggingface.co/BAAI/AltDiffusion-m9
	* Supports English(En), Chinese(Zh), Spanish(Es), French(Fr), Russian(Ru), Japanese(Ja), Korean(Ko), Arabic(Ar) and Italian(It)
	* Original Chinese and English based model: https://huggingface.co/BAAI/AltDiffusion
	* Open source
	* Backed by bilingual CLIP model named AltCLIP
	* Example: https://i.4cdn.org/g/1668837915177041.png

>11/14+11/15+11/16+11/17+11/18 (sdg + hdg done)
* High Performance Machine Learning and Data Analytics for CPUs, GPUs, Accelerators and Heterogeneous Clusters released (not sure if safe): https://github.com/nod-ai/SHARK
* Safetensors, the pickleless format, is way faster than pytorch: https://huggingface.co/docs/safetensors/speed
* Img2img using "human" instructions through language model + text to image model: https://www.timothybrooks.com/instruct-pix2pix
* Dynamic Prompts now supports first-class templating logic: https://github.com/adieyal/sd-dynamic-prompts/blob/main/jinja2.md
* Latent-NERF released, similar to stable-dreamfusion that creates more constrained outputs (?): https://github.com/eladrich/latent-nerf
* Easy to use local install of SD released: https://artroom.ai/download-app
	* Documentation: https://docs.equilibriumai.com/artroom
	* Github: https://github.com/artmamedov/artroom-stable-diffusion
	* Discord: https://discord.com/invite/XNEmesgTFy
	* https://www.reddit.com/r/StableDiffusion/comments/yxdgps/easytouse_local_install_of_stable_diffusion/
	* inpainting, outpainting (with the runway model), textual inversion and hypernetworks are coming in an update
* Brain to Stable Diffusion: https://mind-vis.github.io/
* General purpose scientific language model (Can do things like write code, https://i.4cdn.org/g/1668563334234815s.jpg) (Completely open source): https://github.com/paperswithcode/galai
	* https://twitter.com/paperswithcode/status/1592546938473549824
	* Can summarize academic literature, solve math problems, generate Wiki articles, write scientific code, annotate molecules and proteins, and more
	* "To accelerate science, we open source all models including the 120 billion model with no friction."
* Script to load multiple hypernetworks at once in AUTOMATIC1111's webui (didn't test myself): https://github.com/antis0007/sd-webui-multiple-hypernetworks
* WD 1.4 tagger extension (didn't test myself): https://github.com/toriato/stable-diffusion-webui-wd14-tagger
* (added some info) Watermark applicator to prevent img2img from working well: https://github.com/MadryLab/photoguard
	* Setup(?), has sample image to test for yourself: https://github.com/MadryLab/photoguard/blob/main/notebooks/demo_complex_attack_inpainting.ipynb
	* Anons reported that it doesn't work that well/only works with a specific model + introduces artifacts
	* Seems similar to https://github.com/ShieldMnt/invisible-watermark
* Search danbooru for tags directly in AUTOMATIC1111's webui extension released: https://github.com/stysmmaker/stable-diffusion-webui-booru-prompt
	* Supports post IDs
	* Supports all the search syntax Danbooru uses normally
* Merge SD models without distortion (3rd party git-re-basin method: https://github.com/samuela/git-re-basin): https://github.com/ogkalu2/Merge-Stable-Diffusion-models-without-distortion
* Fast SD by Facebook: https://github.com/facebookincubator/AITemplate/tree/main/examples/05_stable_diffusion
	* Anon reports 35.81 it/s on 3090, 512x512, 50 steps

>11/13+11/14
* Text to shape generation using CLIP (image-text) and zero-shot text to shape generation AKA words to shapes: https://github.com/AutodeskAILab/Clip-Forge
* Self-signed TLS/HHTPS extension (not sure if it covers the system cert store for windows/linux/mac): https://github.com/papuSpartan/stable-diffusion-webui-auto-tls-https
* Cool demonstration of Stable Diffusion + production company (?): https://www.youtube.com/watch?v=QBWVHCYZ_Zs
* (Old but not implemented yet) Stabilize the sampling of DPM Solver++ 2M with a stabilizing trick: https://github.com/crowsonkb/k-diffusion/issues/43#issuecomment-1304916783
	* Edit to make: https://rentry.org/wf7pv
* Repo to train stable diffusion model with Diffusers, Hivemind and Pytorch Lightning released (according to anon: finetune NAI models with their blog mentioned enhancements): https://github.com/Mikubill/naifu-diffusion

>11/11+11/12
* Open source SD model based on chinese text and images released: https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1
	* To allow it to work with AUTOMATIC1111's webui (I think): https://github.com/IDEA-CCNL/stable-diffusion-webui/commit/61ece0cec1097ab8f5e2b52c8d340ca203c5917b
* Explicit padding in prompt (slightly old): https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2642
	* Related, might help with prompting: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/2305
* DeviantArt released an AI image generator: https://twitter.com/DeviantArt/status/1591113199218487300
	* Costs money for premium and is probably not as good as webui
	* Immediately gets nerfed: https://www.deviantart.com/team/journal/UPDATE-All-Deviations-Are-Opted-Out-of-AI-Datasets-934500371
		* https://twitter.com/arvalis/status/1591242450055892992
* Stable Diffusion with ColossalAI for training: https://github.com/hpcaitech/ColossalAI/tree/main/examples/images/diffusion
	* 6.5x faster training and pretraining cost saving, the hardware cost of fine-tuning can be almost 7X cheaper (from RTX3090/4090 24GB to RTX3050/2070 8GB)
* Animating generated face test: https://www.reddit.com/r/StableDiffusion/comments/ys434h/animating_generated_face_test/
* Waifu Diffusion 1.4 Tagger (next iteration of deepdanbooru?): https://mega.nz/file/ptA2jSSB#G4INKHQG2x2pGAVQBn-yd_U5dMgevGF8YYM9CR_R1SY
	* Waifu Diffusion dev (SD training labs server): https://discord.com/channels/1038249716149928046/1038249717001359402/1041160494150594671
* DreamArtist extension changes ui.py code in the modules directory
	* Extension: https://github.com/7eu7d7/DreamArtist-sd-webui-extension
	* Relevant code: https://github.com/7eu7d7/DreamArtist-sd-webui-extension/blob/9f65d05127a551e5dcf044ed6340510f3ba082f4/install.py#L15-L28
	* Breaks itself and normal textual inversion until all the files in the repo are replaced with fresh copies
	* Webui doesn't start after disabling the extension, because of the addition 'dream_artist_trigger'
	* So far, it's not in the wiki extensions list and must be downloaded via repo url. If you want to download it, do it at your own risk
	* To fix your install, do a `git stash` and `git pull`
* Automatically adjust hypernetwork learning rates based on how different the preview image is from the learning data (automate what trainers already do): https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4509
* Diffusion attentive attribution maps for interpreting Stable Diffusion (aka heat maps for what your prompt does): https://github.com/castorini/daam
	* Request: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/4592
* DeepDanbooru broken (not sure if fixed yet): https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/4458
* macOS Finder right-click menu extension released: https://github.com/anastasiuspernat/UnderPillow

>11/10
* WD 1.4 information:
	* New Deepdanbooru for better tagging (prerelease right now)
	* much better hands - look at 'Cafe Unofficial Instagram TEST Model Release' for a sample of what it can do in an unfinished model
	* Trained off SD 1.5
	* Creator: "In terms of general flexibility of being able to prompt a wide range of things, wd1.4 should be better than everything" (planned to supercede all current models, including NAI and anything.ckpt, to the point where you don't need to merge)
	* Creator: "we may create our own version of hypernetworks and create fine tunes for anime and realistic styles"
	* Creator: the instagram model training includes improvements such as:
		1. dynamic image aspect training (as in we trained images with ZERO cropping, the entire image is fed into SD all at once, even if it's landscape or portrait)
		2. unconditional training such that the model can somewhat self improve
		3. higher resolutions during training (640x640 max)
		4. much faster training code (6-8x performance increase)
		5. better training hyperparameters
		6. automated blip captioning of all images
	* Dataset and associated tags will be public
	* Haru and Cafe came up with a temporary plan that may be able to drastically improve the performance of clip without having to retrain clip from scratch, though it'll have to happen after wd1.4
	* to prevent bleed from the images, each source will have a tag associated with it in the caption data when fed into SD
* Intel Arc (A770) can get ~5.2 it/s right now with unoptimized SD, fp16: https://github.com/rahulunair/stable_diffusion_arc
* NovelAI releases their Furry (Beta V1.2) model: https://twitter.com/novelaiofficial/status/1590814613201117184
* PR for inpainting with color: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3865
* Models trained on synthetic data can be more accurate than other models in some cases, which could eliminate some privacy, copyright, and ethical concerns from using real data: https://news.mit.edu/2022/synthetic-data-ai-improvements-1103
* Japanese text to speech (sounds pretty good, can probably use for a VN): https://huggingface.co/spaces/skytnt/moe-tts
	* Colab: https://colab.research.google.com/drive/14Pb8lpmwZL-JI5Ub6jpG4sz2-8KS0kbS?usp=sharing
* VAE selector fixes: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4214
* xformers collection of issues: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2958#discussioncomment-4024359
* Berkeley working on a cheap way to train on the scale of SD using something like a 2070 (easy, efficient, and scalable distributed training): https://github.com/hpcaitech/ColossalAI
	* https://medium.com/@yangyou_berkeley/diffusion-pretraining-and-hardware-fine-tuning-can-be-almost-7x-cheaper-85e970fe207b

>11/9+11/8
* Advanced Prompt Tuning method (APT), can train embeddings with one image: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2945
	* Will be an extension (?)
	* SD with APT: https://github.com/7eu7d7/DreamArtist-stable-diffusion
	* pretrained model for fast training by creator: https://github.com/7eu7d7/pixiv_AI_crawler
	* https://twitter.com/RiversHaveWings/status/1589724378492592128
* New latent diffusion-based upscaler by StabilityAI staff member: https://twitter.com/StabilityAI/status/1590531946026717186
	* Colab: https://colab.research.google.com/drive/1o1qYJcFeywzCIdkfKJy7cTpgZTCM2EI4
* Discovered what NAI's "Variations" feature does (by enhance anon): Alright, variations is really similar to enhance. It sends it to img2img with strength hardcoded @ 0.8, and then increments the seed by 1 for each variation given. Nothing super special.
* Discovered what NAI's "Enhance" feature does (by anon): It upscales the image with Lanczos (defaults to 1.5x, which is the max), and then sends it to img2img with [whatever sampler you specified] @ 50 steps, with the denoising strength ranging from 0.2 to 0.6 (this is the "Magnitude" value that NAI shows, ranging from 1 to 5). It's like a much more expensive version of SD Upscale, which does it as tiles to save VRAM, and instead this does it on the whole image at once, so it requires more VRAM.
* US imposes new export restrictions on NVIDIA to China

>11/8+11/7
* AI video by google (Phenaki + Imagen Video Combination): https://www.youtube.com/clip/Ugkx_p77cvDSUkXBXRlVuq2sHVTu5YTwGiFB
* Using SD as a compressor: https://pub.towardsai.net/stable-diffusion-based-image-compresssion-6f1f0a399202
* Unofficial "paint with words" implementation for SD: https://github.com/cloneofsimo/paint-with-words-sd
	* From NVIDIA's eDiffi that lets you choose areas to prompt ("painting with your words") > helps choose locations for objects (word > attention map)
* Style transfer script: https://github.com/nicolai256/Few-Shot-Patch-Based-Training
* Dreambooth extension released: https://github.com/d8ahazard/sd_dreambooth_extension
	* Downloadable through the extension manager
	* Bug (anon provided): checkpoint saving per N iteration makes you OOM if you are on 12gb, if you disable that then your entire thing wont save, so you have to make the number match the maximum steps for it to save properly
* anything.ckpt (v3 6569e224; v2.1 619c23f0), a Chinese finetune/training continuation of NAI, is released: https://www.bilibili.com/read/cv19603218
	* Huggingface, might be pickled: https://huggingface.co/Linaqruf/anything-v3.0/tree/main
		* Uploader pruned one of the 3.0 models down to 4gb
	* Torrent: https://rentry.org/sdmodels#anything-v30-38c1ebe3-1a7df6b8-6569e224
	* Supposed ddl, I didn't check these for pickles: https://rentry.org/NAI-Anything_v3_0_n_v2_1
	* instructions to download from Baidu from outside China and without SMS or an account and with speeds more than 100KBps: 
		>Download a download manager that allows for a custom user-agent (e.g. IDM)
			>If you need IDM, contact me
		>Go here: https://udown.vip/#/
		>In the "在线解析" section, put 'https://pan.baidu.com/s/1gsk77KWljqPBYRYnuzVfvQ' into the first prompt box and 'hheg' in the second (remove the ')
		>Click the first blue button
		>In the bottom box area, click the folder icon next to NovelAI
		>Open your dl manager and add 'netdisk;11.33.3;' into the user-agent section (remove the ')
		>Click the paperclip icon next to the item you want to download in the bottom box and put it into your download manager
		>
		>To get anything v3 and v2.1: first box:https://pan.baidu.com/s/1r--2XuWV--MVoKKmTftM-g, second box:ANYN
			* another link that has 1 letter changed that could mean it's pickled: https://pan.baidu.com/s/1r--2XuWV--MVoKKmTfyM-g
	* SDmodel owner thinks it's resumed training
	* seems to be better (e.g. provide more detailed backgrounds and characters) than NAI, but can overfry some stuff. Try lowering the cfg if that happens
	* Passes AUTOMATIC's pickle tester and https://github.com/zxix/stable-diffusion-pickle-scanner, but there's no guarantee on pickle safety, so it still might be ccp spyware
	* Use the vae or else your outputs will have a grey filter

>11/7
* ddetailer released: https://github.com/dustysys/ddetailer
	* object detection and auto-mask, helpful in fixing faces without manually masking
* (didn't see this until now) Training TI on 6gb when xformers is available inplemented: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4056
* (From yesterday) Unprompted extension has ads (self-ad, not google ad) now
	* Extensions > uncheck unprompted and reload
	* There are ways to mod it to hide ads
		* Way by anon (This does not remove the ads, CSS only affects appearance. Everything going on in the background to fetch the ad before displaying it, is still happening, including potentially sending info such as your prompts): Edit style.css so it has:
			>#unprompted #toggle-ad {opacity:0.5}
			>#unprompted #toggle-ad:hover {opacity:1;}
			>#unprompted {margin-bottom:2em}
			>#unprompted #ad.active {opacity:0;max-height:000px;padding:00px 00px;transition:1s cubic-bezier(0, 0, 0, 0);}
			>#unprompted #ad {transition:0.5s cubic-bezier(0, 0, 0, 0);max-height:0;overflow:hidden;opacity:0;padding:0px 00px;}
	* FOSS with ads will be the norm if enough support is given
	* https://www.reddit.com/r/StableDiffusion/comments/ynshup/ads_are_starting_to_appear_in_our_foss/
	* Creator's statement: https://www.reddit.com/r/StableDiffusion/comments/ynshup/comment/ivbhhrf/?utm_source=share&utm_medium=web2x&context=3

>11/5 continued+11/6
* ~~Drama in SD Training Labs server/ML Research Labs server~~ Drama resolved
* Lots of issues with overpaying for dreambooth training: https://www.reddit.com/r/StableDiffusion/comments/ynb6h1/dont_overpay_for_dreambooth_training/
	* TLDR (from the creator of the dreambooth ui):
		You don't need pay more than 10$ for a hosted dreambooth training.
		Make sure you have access the trained model (ckpt) before you pay for it.
* Anon says that if you mess with k-diffusion's scheduling, you can make DPM++ 2M Karras a lot better at low steps.
	* https://rentry.org/wf7pv
	* Reasoning: https://github.com/crowsonkb/k-diffusion/issues/43#issuecomment-1304916783
		* tldr: we are using the sigmas of the next step instead of the current step
	* https://i.4cdn.org/g/1667784374378916.png
* (somehow forgot to add this since it's release) Inpainting conditioning mask strength released for AUTOMATIC1111 (save composition while img2img/inpainting)
* (info from anon, not sure if true): Apparently there's a bug where "Desktop Window Manager" eats GPU-cycles randomly when generating
* Standalone dreambooth extension based on ShivShiram's repo: https://github.com/d8ahazard/sd_dreambooth_extension
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3995
	* Author note: I've added requirements installer, multiple concept training via JSON, and moved some bit about. UI still needs fixing, some stuff broken there, but it should be able to train a model for now.
* Huggingface pickle info: https://huggingface.co/docs/hub/security-pickle
* AUTOMATIC1111's webui now has another layer of ckpt filtering before the pickle inspector named safe.py: https://github.com/AUTOMATIC1111/stable-diffusion-webui/blob/master/modules/safe.py
* UMI AI updated to become an extension + major updates (improvements, added stuff, randomization): https://www.patreon.com/posts/74267457
* Loab, might be creepypasta: https://en.wikipedia.org/wiki/Loab
* AUTO UI speedup fix: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/32c0eab89538ba3900bf499291720f80ae4b43e5
* AUTOMATIC1111 added the ability to create extensions that add localizations: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/a2a1a2f7270a865175f64475229838a8d64509ea
	* Related note from AUTO: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/9cd1a66648b4c19136687100f9705d442f31e7f9
* Karras scheduler fix PR (I'm not sure if this change is better): https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4373/commits/f508cefe7995603a05f41b8e948ec1c80631360f
	* anon says that DPM++2S a can converge in 6 steps using this fix
* On August 13, 2018, Section 1051 of the John S. McCain National Defense Authorization Act for Fiscal Year 2019 (P.L. 115-232) established the National Security Commission on Artificial Intelligence as an independent Commission “to consider the methods and means necessary to advance the development of artificial intelligence, machine learning, and associated technologies to comprehensively address the national security and defense needs of the United States.”
	* https://www.nscai.gov/about/
	* https://www.nscai.gov/commissioners/commissioner-bio/
* How Google’s former CEO Eric Schmidt helped write A.I. laws in Washington without publicly disclosing investments in A.I. startups
	* https://www.cnbc.com/2022/10/24/how-googles-former-ceo-eric-schmidt-helped-write-ai-laws-in-washington-without-publicly-disclosing-investments-in-ai-start-ups.html
* Pickle scanner catered for SD models, hypernetworks, and embeddings released: https://github.com/zxix/stable-diffusion-pickle-scanner
* Visual novel released: https://beincrypto.com/ai-art-worlds-first-bot-generated-graphic-novel-hits-the-market/
	* https://www.amazon.com/Star-Maker-Illustrated-Olaf-Stapledon-ebook/dp/B0BFHJPGKP#customerReviews
* DPM solver++, the successor to DDIM (which was already fast and converged quickly) released and added to webui: https://github.com/LuChengTHU/dpm-solver
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4304#issuecomment-1304571438
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/4280
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4304
	* Relevant k-diffusion update: https://github.com/crowsonkb/k-diffusion
	* https://arxiv.org/abs/2211.01095
	* Comparison: https://i.4cdn.org/g/1667590513563375.png
	* Comparison 2: https://user-images.githubusercontent.com/20920490/200128399-f6f5c332-af80-4a0c-ba6d-0cb299744418.jpg
	* Comparison 3: https://i.4cdn.org/h/1667717716435289.jpg

>11/5
* new pickle inspector: https://github.com/lopho/pickle_inspector
	* From ML research labs server

>11/4
* New version of DiffusionBee released: https://www.reddit.com/r/StableDiffusion/comments/ylmtsz/new_version_of_diffusionbee_easiest_way_to_run/
	* https://github.com/divamgupta/diffusionbee-stable-diffusion-ui
* Artist gives observations on using AI to make money: https://www.reddit.com/r/StableDiffusion/comments/yh8j0a/ai_art_is_popular_and_makes_money_confessions_of/
* US Copyright Office supposedly states that visual work shall be substantially made by a human to be copyrightable
	* Pt. 1: https://www.reddit.com/r/COPYRIGHT/comments/xkkh3d/us_copyright_office_registers_a_heavily/
	* https://www.reddit.com/r/StableDiffusion/comments/yhdyc0/artist_states_that_us_copyright_office_intends_to/
	* https://www.reddit.com/r/COPYRIGHT/comments/yhdtnb/artist_states_that_us_copyright_office_intends_to/
* From one of the original DreamBooth authors: Stop using SKS as the initializer word
	* SKS is a gun recognized by SD
	* https://i.imgur.com/tFA0Vy1.jpg
	* https://www.reddit.com/r/StableDiffusion/comments/yju5ks/from_one_of_the_original_dreambooth_authors_stop/
* Unprompted extension has ads
	* Apparently it can be easily modified to get rid of the ads
* Established artist gives a good take about SD: https://www.reddit.com/r/StableDiffusion/comments/yhjovv/how_to_make_money_as_an_artist_with_a_personal/
* (repost from 11/3 with extra information) NVIDIA new paper detailing a better model than imagen: https://deepimagination.cc/eDiffi/
	* You can "paint with words" (select part of the prompt and put it in the image)
	* conditioned on the T5 XXL text embeddings (higher quality, incorrect objects, text to text), CLIP image embeddings (style + inspiration, text to image) and CLIP text embeddings (correct objects, less detail)
	* Uses expert models: each step/group of steps uses a different model
	* has style transfer (control the style of the genreated sample using a reference style image)
	* has better text in the final image (look through paper)
	* **issue would be running on consumer hardware since the T5 XXL embedding is 40+ gb VRAM**
	* https://arxiv.org/abs/2211.01324
	* https://www.reddit.com/r/StableDiffusion/comments/ykqfql/nvidia_publishes_paper_on_their_own_texttoimage/
* (oldish news) Extension installer and manager in AUTOMATIC1111's webui
* NovelAI tokenizer for CLIP and some other models: https://novelai.net/tokenizer
* Batch model merging script released: https://github.com/lodimasq/batch-checkpoint-merger
* script that pulls prompt from Krea.ai and Lexica.art based on search terms released: https://github.com/Vetchems/sd-lexikrea
* Depthmap script released: https://github.com/thygate/stable-diffusion-webui-depthmap-script
	* creates depth maps from generated images
	* outputs can be viewed on 3D or holographic devices like VR headsets, can be used in render or game engines, or maybe even 3D printed
* Training picker extension released: https://github.com/Maurdekye/training-picker
	* video > keyframes > training
* Some statements from Emad (CEO of StabilityAI)
	* next model will be released after retraining some stuff
	* New **open source** models are expected to be released by other groups in the upcoming months that are better than 1.5
	* Making it easier to fine tune models
	* 2.0 model will be "done when done"
	* https://cdn.discordapp.com/attachments/662466568172601369/1038223793279217734/1.png

>11/3
* More hypernetwork changes
* Unofficial MagicMix implementation with Stable Diffusion in PyTorch: https://github.com/cloneofsimo/magicmix
	* Good img2img with "geometric coherency and semantical layouts"
* Convert any model to Safetensors and open a PR (pull request = a request/proposal to apply a modification to a github repository)
	* Safetensors are the unpicklable format
	* https://huggingface.co/spaces/safetensors/convert
	* https://github.com/huggingface/safetensors
* Zeipher AI f222 model release: https://ai.zeipher.com/#tabs-2
	* torrent: magnet:?xt=urn:btih:GR3IGMJDPJPW3B4WRT5B7SAN7CEBHWSZ&dn=f222&tr=http%3A%2F%2Ftracker.openbittorrent.com%2Fannounce
* NovelAI releases source code and documentation for training on non 512x512 resolutions (Aspect Ratio Bucketing)
	* https://github.com/NovelAI/novelai-aspect-ratio-bucketing
	* https://blog.novelai.net/novelai-improvements-on-stable-diffusion-e10d38db82ac
	* https://www.reddit.com/r/NovelAi/comments/ykgns6/novelai_aspect_ratio_bucketing_source_code/
	* https://twitter.com/novelaiofficial/status/1587907133643034624

>11/2
* f222 model release date on Friday from Zeipher AI (f111 was better female anatomy, so maybe this is their next iteration)
	* Discord: https://discord.gg/hqbrprK6
	* Site: https://ai.zeipher.com/
* Multiple people are working on a centralized location to upload embeddings/hypernetworks
	* AIBooru devs
	* Independent dev irythros
	* Questianon (me)
* Correction from sdupdates1
	* New Windows based Dreambooth solution with Adam8bit support might support 8gb cards (anon reported 11 MBs of extra vram needed, so if you lower your vram usage to its absolute minimum, it might work)
		* https://github.com/bmaltais/kohya_ss
		* instructions: https://note.com/kohya_ss/n/n61c581aca19b
		* new + low number of stars, so not sure if pickled
* Chinese documentation with machine translation for English: https://draw.dianas.cyou/en/
* Auto-SD-Krita is getting turned into an extension: https://github.com/Interpause/auto-sd-paint-ext
	* Original auto-sd-krita will be archived
* Training image preview PR: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3594
* Artist gives their thoughts on using AI (what problems it currently has): https://twitter.com/jairoumk3/status/1587363244062089216?t=HEd1gQkIiSLbvOk9X7lEeg&s=19
* Clarification from yesterday's news:
	* MMD + NAI showcase (UC = undesired content [NAI]/negative prompt [non-NAI], ): https://twitter.com/8co28/status/1587238661090791424?t=KJmJhfkG6GPcxS5P6fADgw&s=19 
		* Creator found out that putting "3d" in the negative prompts makes outputs more illustration-like: https://twitter.com/8co28/status/1587004598899703808

>11/1
* SD Upscale broken on latest git pull: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/4104
	* Seems to affect some other parts of webui too
* PR for hypernetwork resume fix: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3975
* Dreambooth will probably not be integrated into AUTOMATIC1111's webui normally. It's likely to be turned into an extension: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3995#issuecomment-1298741868
* Dehydrate ("compress" down to 1gb) and rehydrate models: https://github.com/bmaltais/dehydrate
	1. Use the ckpt_subtract.py script to subtract the original model from the DB model, leaving behind only the difference between the two.
    2. Compress the resulting model using tar, gzip, etc to roughly 1GB or less
    3. To rehydrate the model simply reverse the process. Add the diff back on top of the original sd15 model (or actually any other models of your choice, can be a different one) with ckpt_add.py.
* 6gb textual inversion training when xformers is available merged: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/4056
* From the Chinese community (some news is old, info provided by Chinese anon):
	* Someone made a fork of diffusers, added support of wandb, and reduced the size of ckpt to about 2G by changing the precision to fp16
		* Supposedly makes it easier to prune the ckpt
		* Repo: https://github.com/CCRcmcpe/diffusers
	* It's believed that the size can possibly be further reduced by removing the vae
	* WIP of using the training difference to distribute the ckpt
		* Original reddit post about it: https://www.reddit.com/r/StableDiffusion/comments/ygl75c/not_really_working_poorly_coded_sparse_tensor/ 
		* Modified version that Chinese anons are testing: https://gist.github.com/AmericanPresidentJimmyCarter/1947162f371e601ce183070443f41dc2
		* If I recall correctly, this is how ML Research Lab plans to do distributed model training
	* Huggingface for ERNIE-ViLG: https://huggingface.co/spaces/PaddlePaddle/ERNIE-ViLG
* AI art theft is now appearing (reuploads of AI art)
	* Example: https://www.reddit.com/r/StableDiffusion/comments/yipeod/my_sdcreations_being_stolen_by_nftbros/
	* anons reported stealing too
* Lots of localization updates + improvements + extra goodies added if you update AUTOMATIC1111's webui
* Wildcard script + collection of wildcards released: https://app.radicle.xyz/seeds/pine.radicle.garden/rad:git:hnrkcfpnw9hd5jb45b6qsqbr97eqcffjm7sby

>10/31
* Unprompted extension released: https://github.com/ThereforeGames/unprompted
	* Wildcards on steroids
	* Powerful scripting language 
	* Can create templates out of booru tags
	* Can make shortcodes
	* "You can pull text from files, set up your own variables, process text through conditional functions, and so much more "
* You might be able to get more performance on windows by disabling hardware scheduling
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/3889
* (semi old news) New inpainting options added
* Extensions manager added for AUTOMATIC1111's webui
* Pixiv adding AI art filter: https://www.pixiv.net/info.php?id=8729
	* https://www.pixiv.net/info.php?id=8711
	* https://www.pixiv.net/en/artworks/102382801
* VAE selector PR: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3986
* Open sourced, AI-powered creator released
	* https://github.com/carefree0910/carefree-creator#webui--local-deployment
	* Can run local and through their servers
	* Copied from their github: 
		* An infinite draw board for you to save, review and edit all your creations.
		* Almost EVERY feature about Stable Diffusion (txt2img, img2img, sketch2img, variations, outpainting, circular/tiling textures, sharing, ...).
		* Many useful image editing methods (super resolution, inpainting, ...).
		* Integrations of different Stable Diffusion versions (waifu diffusion, ...).
		* GPU RAM optimizations, which makes it possible to enjoy these features with an NVIDIA GeForce GTX 1080 Ti  
* ERNIE-ViLG 2.0 (new open source text to image generator developed by Baidu): https://arxiv.org/abs/2210.15257
	* https://github.com/PaddlePaddle/ERNIE
	* Supposedly has benefits over SD?
* (old news) Google AI video showcase: https://imagen.research.google/video/
* (old news) Facebook Img2video: https://makeavideo.studio/
* (Info by anon) A look into better trainings: https://arxiv.org/pdf/2210.15257.pdf
>train multiple denoisers, use one for the starting few steps to form rough shapes, use one for the last few steps to finalize detail
>while training, use a image classifier to mark regions corresponding to subjects in the text descriptor. If text descriptor doesn't exist, add it to the prompt
>modify attention function to increase the attention weight between subjects found by the classifier
>modify loss function to give regions marked by the classifier more weight
* PaintHua.com - New GUI focusing on Inpainting and Outpainting
	* https://www.reddit.com/r/StableDiffusion/comments/ygp0iv/painthuacom_new_gui_focusing_on_inpainting_and/
* Training a TI on 6gb: https://pastebin.com/iFwvy5Gy
	* Have xformers enabled.
	> This diff does 2 things.
	> 1. enables cross attention optimizations during TI training. Voldy disabled the optimizations during training because he said it gave him bad results. However, if you use the InvokeAI optimization or xformers after the xformers fix it does not give you bad results anymore.
	>This saves around 1.5GB vram with xformers
>
	>2. unloads vae from VRAM during training. This is done in hypernetworks, and idk why it wasn't in the code for TI. It doesn't break anything and doesn't make anything worse.
	>This saves around .2 GB VRAM
	>
	>After you apply this, turn on Move VAE and CLIP to RAM and Use cross attention optimizations while training
* Google AI demonstration: https://youtu.be/YxmAQiiHOkA
* Deconvolution and Checkerboard Artifacts: https://distill.pub/2016/deconv-checkerboard/

>10/30
* (oldish news) Mubert, text to music released: https://github.com/MubertAI/Mubert-Text-to-Music
	* app to listen: https://apps.apple.com/app/apple-store/id1154429580
	* search for music: https://mubert.com/render
	* Huggingface demo: https://huggingface.co/spaces/Mubert/Text-to-Music
* Stable diffusion "deepfake" (good with few keyframes)
	* https://twitter.com/NicolaiNightVi1/status/1586434671663013889
	* https://github.com/nicolai256/Few-Shot-Patch-Based-Training
* Git pull for some updates
	* Hypernetwork training fixed (continuing training off old checkpoints for HNs and embeds is still broken)
		* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3771
		* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-3980624
* shrink the size of ckpts and grow them back to their original size: https://github.com/bmaltais/dehydrate
	* not sure if safe, but it seems to work
* Blender camera animations to deforum released: https://github.com/micwalk/blender-export-diffusion
* New Windows based Dreambooth solution with Adam8bit support (should run on 8gb and 12gb cards): https://github.com/bmaltais/kohya_ss
	* instructions: https://note.com/kohya_ss/n/n61c581aca19b
	* new, so not sure if pickled
* Img2music (fun): https://huggingface.co/spaces/fffiloni/img-to-music
* **GUI helper for manual tagging and cropping released: https://github.com/arenatemp/sd-tagging-helper**
* Dreambooth PR: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3995
* Video diffusion models: https://video-diffusion.github.io/
* Dataset shuffling should be fixed now so that it actually shuffles.
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3803


>10/29
* SD multiplayer: https://huggingface.co/spaces/huggingface-projects/stable-diffusion-multiplayer
	* kind of like r/place
* Big inpainting updated released (composition stays the same but style changes)
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3669
* Unreal engine 5 plugin released
	* https://github.com/albertotrunk/ue-stable-diffusion
* Hires broken on the latest commit
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/3888
* (old news) new hypernetwork training added

>10/28
* Largest Korean hypernetwork/embedding sharing forum post with a ton of hypernetworks/embeddings + images (highly recommended)
	* https://arca.live/b/hypernetworks/60940948
	* has an English explanation of some stuff at the top
		* koreanon requests for good embeddings to be posted in the comments with artist name
* ~~Rumor on /g/ that AUTOMATIC1111 was conscripted into the russian army~~ False rumor, AUTOMATIC1111 said that he's fine and is just resting from Stable Diffusion and will probably:
	* work on PRs soon
	* "make a tab for extensions for list and easy install from URL"
* Custom poseable doll released
	* Original video: https://youtu.be/iPsX7z5imVY
	* Tutorial: https://youtu.be/MClbPwu-75o
	* Download: https://www.artstation.com/marketplace/p/VOAyv/stable-diffusion-3d-posable-manekin-doll?utm_source=artstation&utm_medium=referral&utm_campaign=homepage&utm_term=marketplace
* Note for training: You can set a learning rate of "0.1:500, 0.01:1000, 0.001:10000" in textual inversion and it will follow the schedule
* Parseq released
	* parameter sequencer
	* "Generate videos with tight control and flexible interpolation over many Stable Diffusion parameters (such as seed, scale, prompt weights, denoising strength...), as well as input processing parameter (such as zoom, pan, 3D rotation...)"
	* https://github.com/rewbs/sd-parseq
* Img2tiles script released
	* https://github.com/arcanite24/img2tiles
* Stable Diffusion Prompt Book released
	* Organized by openart.ai in collab with PublicPrompts (https://publicprompts.art/)
	* https://bit.ly/PromptBook
	* https://openart.ai/promptbook
	* https://www.reddit.com/r/StableDiffusion/comments/yfm8go/im_glad_to_announce_the_release_of_the_stable/
* AI Pictionary released
	* https://pictionairy.com/
* CIO statement from a few days ago
	* https://www.reddit.com/r/StableDiffusion/comments/y9ga5s/stability_ais_take_on_stable_diffusion_15_and_the/
	* https://danieljeffries.substack.com/p/why-the-future-of-open-source-ai
* (old news) Imagic running with Stable Diffusion
	* twitter: https://twitter.com/Buntworthy/status/1582307817884889088
	* github: https://github.com/justinpinkney/stable-diffusion
	* notebook: https://github.com/justinpinkney/stable-diffusion/blob/main/notebooks/imagic.ipynb
* (old news) government letter to Stability AI: https://eshoo.house.gov/sites/eshoo.house.gov/files/9.20.22LettertoNSCandOSTPonStabilityAI.pdf
* (old news) Deviant Art CEO supports ai (?)
	* https://www.deviantart.com/wannabby, check their posts about AI
* (old news) imagic: img2img but better
	* paper: https://arxiv.org/pdf/2210.09276.pdf
	* implementation: https://github.com/justinpinkney/stable-diffusion/blob/main/notebooks/imagic.ipynb

>10/27
* hypernetwork training is currently broken (unsure if fixed now)
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-3973187

>10/26
* Created https://github.com/questianon/sdupdates
	* Rentry backup for now
	* Features people might like:
		* Commit history so you know what's new
		* Watch so you can get notifications
		* The formatting might be nicer
* New generative models, supposedly faster than diffusers
	* https://github.com/Newbeeer/Poisson_flow
	* More info: https://www.assemblyai.com/blog/an-introduction-to-poisson-flow-generative-models/
	* electrodynamics inspired (the current diffusion model is thermodynamics/statistical physics inspired)
	* 10-20x faster
	* https://colab.research.google.com/drive/1neY6OovzZELul9t2OTdThUitptNVnuHR?usp=sharing
* Automatic1111's webui supports subfolders and symlinks
	* saves space + allows for organization
	* https://www.reddit.com/r/StableDiffusion/comments/ye2fwh/tip_automatic1111_supports_model_subfolders/
* Stable Diffusion plugin for Krita and Photoshop (not much info, so not sure if safe)
	* https://internationaltd.github.io/defuser/
	* https://github.com/internationalTD/defuser
	* old version: https://github.com/internationalTD/sd_frontend

>10/21 - 10/25 (big news bolded, big thanks to asuka-test-imgur-anon-who-also-made-the-speedrun-tutorial for some info)
* Latest git pull can break SD (windows)
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/3688
	* update with "git pull origin master" instead of "git pull" until the branch is deleted on the github side
* gaming cock flower arrangement club (Japanese lore)
	* https://twitter.com/ankomelt/status/1584058799865806854
	* https://dic.nicovideo.jp/a/ゲーミングチンポ華道部
	* https://twitter.com/search?q=ゲーミングちんぽ華道部&src=typed_query&f=image
* Deforum (video animation) extension released
	* https://github.com/deforum-art/deforum-for-automatic1111-webui/
	* https://www.reddit.com/r/StableDiffusion/comments/ychq1x/the_official_deforum_script_for_2d3d_stable/
* Many new VAE's (finetunes) released
	* Check https://rentry.org/sdmodels for most of them
* **NovelAI explanation of all their implemations**
	* https://scribe.froth.zone/m/global-identity?redirectUrl=https%3A%2F%2Fblog.novelai.net%2Fnovelai-improvements-on-stable-diffusion-e10d38db82ac
* Infinite outpainting: https://github.com/lkwq007/stablediffusion-infinity
* Safer pickleless (unpickleable) format, still needs to be implemented
	* https://github.com/huggingface/safetensors
	* "This repository implements a new simple format for storing tensors safely (as opposed to pickle) and that is still fast (zero-copy)."
* Temp folder storing generations, space issues (might be fixed now)
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/3278 
* Dreambooth training (now with gui https://github.com/smy20011/dreambooth-gui ), referenced via prompt (?)
* Guided inpainting (video inpainting with keyframes)
	* https://github.com/runwayml/guided-inpainting
* If you build Hydrus from source, someone made a fork to import the tags and other metadata automatically. 
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2087#discussioncomment-3928256
* AUTOMATIC1111's history tab now an extension:
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions#image-browser
* Imagic Stable Diffusion training in 11 GB VRAM
	* https://github.com/ShivamShrirao/diffusers/tree/main/examples/imagic
* Interpolate script for AUTOMATIC1111's webui
	* https://github.com/DiceOwl/StableDiffusionStuff
* Text2LIVE: Text-Driven Layered Image and Video Editing
	* https://github.com/omerbt/Text2LIVE
	* https://www.reddit.com/r/StableDiffusion/comments/y89gz0/text2live_textdriven_layered_image_and_video/
	* demo site: https://text2live.github.io
	* arxiv: https://arxiv.org/abs/2204.02491
* AUTOMATIC1111's webui has an api
	* https://sphuff.dev/automatic-now-has-an-api
	* https://www.reddit.com/r/StableDiffusion/comments/ybhqe8/automatic_now_has_an_api/
* **StabilityAI released a new VAE**
	* Improves eyes, hands, colors, and img2img
	* https://huggingface.co/stabilityai
	* **Tutorial + how to use on ALL models (applies for the NAI vae too): https://www.reddit.com/r/StableDiffusion/comments/yaknek/you_can_use_the_new_vae_on_old_models_as_well_for/**
* **Aesthetic Gradients released**
	* voldy's announcement https://desuarchive.org/g/thread/89343235/#89345163
	* breakdown of new interface https://desuarchive.org/g/thread/89343235/#89345258
	* more explanation https://desuarchive.org/g/thread/89343235/#89345322
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients
* Lama Cleaner released with v1.5 support
	* https://github.com/Sanster/lama-cleaner
	* Good at watermark removal
	* https://www.reddit.com/r/StableDiffusion/comments/y90hzz/lama_cleaner_add_runwaysd15inpainting_support_the
		* Mini tutorial in the comments
* Dance Diffusion (AI Music) released by HarmonAI
	* Discord: https://discord.gg/MunJTXwk
* AI Music by Google
	* https://www.technologyreview.com/2022/10/07/1060897/ai-audio-generation/
* 8-10gb Dreambooth for AUTOMATIC1111's webui WIP
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2002
* **hlky’s/sd-webui rebranded as Sygil.dev**
	* Working on Project Nataili, a common Standard Diffusion backend 
	* Goal is to centralize all resources
	* https://www.reddit.com/r/StableDiffusion/comments/yd5p5s/hlkyssdwebui_announcing_sygildev_project_nataili/
* visualise.ai
	* Account required
	* Free unlimited 512x512/64 step runs
* **Optimized dreambooth**
	* train under 10 minutes without class images on multiple subjects, retrainable-ish model
	* Tutorial: https://www.reddit.com/r/StableDiffusion/comments/yd9oks/new_simple_dreambooth_method_is_out_train_under/
	* Github: https://github.com/TheLastBen/fast-stable-diffusion
* Many sites banned AI art
* **Hypernetwork structures added**
	* more numbers = more vram needed = deeper hypernetwork = better results (?)
	* Deep hypernetworks are suited for training with large datasets
* **Waifu Diffusion 1.4 roadmap:**
	* https://gist.github.com/harubaru/313eec09026bb4090f4939d01f79a7e7
	* Release date: December 1
	* Discord: https://discord.gg/SqrKhArt
* **Extensions added to AUTOMATIC1111's webui**
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions
* Test embeddings before you download them
	* https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer
* UMI AI, a wildcard engine, released
	* Free
	* Tutorial: https://www.patreon.com/posts/umi-ai-official-73544634
	* Discord (SFW and NSFW): https://discord.gg/9K7j7DTfG2
	* More info in https://rentry.org/sdupdates#prompting 
* 3D AI stuff
	* https://www.youtube.com/watch?v=19gzG-AsBNU
	* https://dreamfusion3d.github.io/
	* https://3d-diffusion.github.io/
	* https://medium.com/mlearning-ai/3d-diffusion-models-22fd4ccc41a2
* Pose Estimation
	* https://viso.ai/deep-learning/pose-estimation-ultimate-overview/

>10/20
* SD v1.5 released by RunwayML
	* Uncensored, legitimate 1.5
	* Huggingface: https://huggingface.co/runwayml/stable-diffusion-v1-5
	* Tweet: https://twitter.com/runwayml/status/1583109275643105280
	* https://nitter.it/runwayml/status/1583109275643105280#m
	* https://rentry.org/sdmodels
	* Reddit thread: https://www.reddit.com/r/StableDiffusion/comments/y91pp7/stable_diffusion_v15/
	* Drama recap: https://www.reddit.com/r/StableDiffusion/comments/y99yb1/a_summary_of_the_most_recent_shortlived_so_far/
		* https://rentry.org/sdupdates#confirmed-drama for recap + links


>10/19
* Git pull for a lot of new stuff
	* theme argument: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/665beebc0825a6fad410c8252f27f6f6f0bd900b
	* A lot of optimizations
	* Layered hypernetworks
	* Time left estimation (if jobs take more than 60 sec)
	* Minor UI changes
* Runway released new SD inpainting/outpainting model
	* https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion
* Stability AI event recap
	* https://www.reddit.com/r/StableDiffusion/comments/y6v0v9/stability_event_happening_now_news_so_far/
	* Animation API next week
	* DreamStudio Pro in progress (automatic gen of video from music + latent space exploration)
	* will fund 100 PHDs this year
	* Their cluster is 4000 A100s on AWS and plans to grow 5x-10x next year
	* will reduce price of Dreamstudio by half
	* Game universes created with AI: https://twitter.com/Plinz/status/1582202096983498754
* Dreambooth GUI: https://github.com/smy20011/dreambooth-gui
* NAI possibly tinkering with their backend based on tests by touhou anons
	* better hands
* Unreal Engine 5 SD plugin: https://github.com/albertotrunk/UE5-Dream
* Underreported: You can highlight a part of your prompt and ctrl + up/down to change weights

>10/18
* Clarification on censoring SD's next model by the question asker
	* https://rentry.org/sdupdates#confirmed-drama
	* TLDR: SD will probably release a censored model before releasing their 1.5 model because of legal issues (like with CP)

>10/17
* $101 million in funding from Stability AI for opensource and free AI
	* https://www.prnewswire.com/news-releases/stability-ai-announces-101-million-in-funding-for-open-source-artificial-intelligence-301650932.html
* xformers degrading quality
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2967
	* It's a bug that causes the variance with --xformers
* New trinart model
	* https://huggingface.co/naclbit/trinart_characters_19.2m_stable_diffusion_v1
	* basically SFW
* Discovered hi-res generations are affected by the video card used
	* https://desuarchive.org/g/thread/89259005/#89260871
	* TLDR: 3000s series are similar, 2000s and 1000s will vary

>10/16
* **Remote code execution exploit discovered 2 days ago**
	* AUTOMATIC pushed an update to deal with this. Use the hide_ui_dir_config if you plan on using --share after updating. Set a password.

	* Gradio fix in progress: https://github.com/gradio-app/gradio/issues/2470
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/2571
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/920
	* https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/1576
	* https://www.reddit.com/r/StableDiffusion/comments/y56qb9/security_warning_do_not_use_share_in/
* Deforum script released for AUTOMATIC1111's webui
	* https://github.com/deforum-art/deforum-for-automatic1111-webui/
* Google open sourced their prompt-to-prompt method
	* https://github.com/google/prompt-to-prompt
	* Uses cross attention control
		* https://github.com/bloc97/CrossAttentionControl
		* https://github.com/sunwoo76/CrossAttentionControl-stablediffusion

>10/15
* **Embeddings now shareable via images**
	* No need to download .pt files anymore
	* To use, finish training an embedding, download the image of the embedding (the one with the circles at the edges), and place it in your embeddings folder. The name at the top of the image is the name you use to call the embedding.
	* https://www.reddit.com/r/StableDiffusion/comments/y4tmzo/auto1111_new_shareable_embeddings_as_images/
		* Example (2nd and 3rd image): https://www.reddit.com/gallery/y4tmzo
* Stability AI update pipeline (https://www.reddit.com/r/StableDiffusion/comments/y2x51n/the_stability_ai_pipeline_summarized_including/)
	* This week: 
		* Updates to CLIP (not sure about the specifics, I assume the output will be closer to the prompt)
		* Clip-guidance comes out open source (supposedly)
	* Next week:
    	* DNA Diffusion (applying generative diffusion models to genetics)
			* https://github.com/pinellolab/DNA-Diffusion
    	* A diffusion based upscaler ("quite snazzy")
    	* A new decoding architecture for better human faces ("and other elements")
    	* Dreamstudio credit pricing adjustment (cheaper, that is more options with credits)
    	* Discord bot open sourcing
	* Before the end of the year:
		* Text to Video ("better" than Meta's recent work)
    	* LibreFold (most advanced protein folding prediction in the world, better than Alphafold, with Havard and UCL teams)
    	* "A ton" of partnerships to be announced for "converting closed source AI companies into open source AI companies"
    	* (Potentially) CodeCARP, Code generation model from Stability umbrella team Carper AI (currently training)
    	* (Potentially) Gyarados (Refined user preference prediction for generated content by Carper AI, currently training)
    	* (Potentially) CHEESE (some sort of platform for user preference prediction for generated content)
    	* (Potentially) Dance Diffusion, generative audio architecture from Stability umbrella project HarmonAI (there is already a colab for it and some training going on i think)
* Animation Stable Diffusion:
	* https://github.com/HelixNGC7293/DeforumStableDiffusionLocal
* Stable Diffusion in Blender
	* https://airender.gumroad.com/l/ai-render
	* Uses Dreamstudio for now
* DreamStudio will now use CLIP guidance
* Stable Diffusion running on iPhone
	* https://github.com/madebyollin/maple-diffusion
* Cycle Diffusion: https://github.com/ChenWu98/cycle-diffusion
	* txt2img > img2img editors, look at github to see examples
* Information about difference merging added to FAQ
* Distributed model training planned
	* SD Training Labs server
* Gradio updated
	* Optimized, increased speeds
	* Git pulling should be safe

>10/14
* Fed bait claims
* You can generate forever by right clicking on the generate button
* Can now load checkpoint, clip skip, and hypernet from infotext for AUTO's webui
* Advanced Prompt Tuning, minimizes prompt typing and optimzes output quality
	* https://github.com/7eu7d7/APT-stable-diffusion-auto-prompt
	* planned to be PR on AUTO's repo once updated
* 3D photo inpainting
	* https://github.com/vt-vl-lab/3d-photo-inpainting
* Beginner's guide released:
	* https://rentry.org/nai-speedrun
* New method for merging models on AUTOMATIC1111's UI
	* Double model merging + difference merging using a third model

>10/13
* Emad QnA Summary
	* https://github.com/brycedrennan/imaginAIry/blob/master/docs/emad-qa-2020-10-10.md#summarized-version
* Image animation 
	* https://github.com/yoyo-nb/Thin-Plate-Spline-Motion-Model
* Motion Diffusion available (text to a video of human motion)
	* https://github.com/GuyTevet/motion-diffusion-model
* Text to video available for everyone
	* https://github.com/lucidrains/imagen-pytorch#text-to-video-ongoing-research
* VR SD in the works
	* https://twitter.com/ScottieFoxTTV/status/1579903471943569410
* Emad's statement on censoring SAI's next model: https://desuarchive.org/g/thread/89182040#89182584
	* NSFW model is hard to train right now, meaning the next release will have:
		* No more nudity
		* Violence allowed
		* Opt-out tool coming for artists who do not want their art to be trained
* New method for training styles that doesn't require as many computing resources
	* https://metaphysic.ai/custom-styles-in-stable-diffusion-without-retraining-or-high-computing-resources/
	* https://github.com/vicgalle/stable-diffusion-aesthetic-gradients
* Method for faster and low step count generations
	* https://arxiv.org/abs/2210.03142

>10/12
* StabilityAI is only releasing SFW models from now on
	* https://www.reddit.com/r/StableDiffusion/comments/y2dink/qa_with_emad_mostaque_formatted_transcript_with/is32y1d/

>10/11
* Training embeddings and hypernetworks are possible on --medvram now
* Easy to setup local booru by booru anon, might be pickled (NOW OPEN SOURCE, HIGHLY RECOMMENDED): https://github.com/demibit/stable-toolkit
	* Planned to be open source in about a week
* Can now train hypernetworks, git pull and find it in the textual inversion tab
	* Sample (bigrbear): https://files.catbox.moe/wbt30i.pt
* Anon (might be wrong): xformers now works on a lot of cards natively, try a clean install with --xformers
* Early Anime Video Generation, trained by dep
	* Colab: https://colab.research.google.com/drive/14xl37LceSXhdc5u7v5uL0bk09BpAL7CJ?usp=sharing
	* Models: https://huggingface.co/chavinlo/anime-video-diffusion
	* Code: https://github.com/chavinlo/video-diffusion-pytorch

>10/10
* New unpickler for new ckpts: https://rentry.org/safeunpickle2
* ~~HENTAI DIFFUSION MIGHT HAVE A VIRUS~~ confirmed to be safe by some kind people 
	* github taken down because of nude preview images, hf files taken down because of complaints, windows defender false positive, some kind anons scanned the files with a pickle scanner and and it came back safe
	* automatic's repo has security checks for pickles
	* anon scanned with a "straced-container", safe
* NAI's euler A is now implemented in AUTOMATIC1111's build
	* git pull to access
* New open-source (?) generation method revealed making good images in 4 steps
	* Supposedly only 64x64, might be wrong
* Discovered that hypernetworks were meant to create anime using the default SD model

>10/9
* Full NAI frontend + backend implementation: https://desuarchive.org/g/thread/89095460#89097704 (PICKLE??, careful might actually be pickled)
	* 1:1 recreation, is NAI ran locally (offline NAI)
	* 8GB VRAM required
	* has danbooru tag suggestions, past generation history, and mobile support (from anon)
* Unlimited prompt tokens
* NAI 1:1 Recreation for Euler (ASUKA, https://desuarchive.org/g/thread/89097837#89098634 https://boards.4chan.org/h/thread/6887840#p6888020)
	* detailed setup guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
* xformers working for 30s series and up, anything below needs tinkering (https://rentry.org/25i6yn) 
	* Use --xformers to enable for 30s series, --force-enable-xformers for others
* Deepdanbooru integrated: Use --deepdanbooru as an argument to webui-user.bat and find the interrogation change in img2img
* CLIP layer thing integrated, check settings after update
* v2.pt working
* VAE working
* Full models working

# SD RESOURCE GOLDMINE

## Preamble
This is a curated collection of up to date links and information. Everything else is put into one of the collections in [Archives](#archives) for archival or sorting purposes.

This collection is currently hosted on the [SD Goldmine rentry](https://rentry.org/sdgoldmine), the [SD Updates rentry (3)](https://rentry.org/sdupdates3), and [Github](https://github.com/questianon/sdupdates)

All rentry links are ended with a '.org' here and can be changed to a '.co'. Also, use incognito/private browsing when opening google links, else you lose your anonymity / someone may dox you

## Contact

If you have information/files not on this list, have questions, or want to help, please contact me with details

Socials: 
Trip: questianon !!YbTGdICxQOw 
Discord: malt#6065
Reddit: u/questianon
Github: https://github.com/questianon
Twitter: https://twitter.com/questianon)

## How to use this resource
The goldmine is ordered from surface-level content to deep level content. If you are a newcomer to Stable Diffusion, it's highly recommended to use start from the beginning.

To prevent redundancies, all items on this list are listed only once. To make sure you find what you're looking for, please use 'Ctrl + F' ('Cmd + F' on macOS).

## Emoji
Items on this list with a :cucumber: next to them represent my top pick for the category. This rating is entirely opinionated and represents what I have personally used and recommend, not what is necessarily "the best".

## Warnings
1. Ckpts/hypernetworks/embeddings and things downloaded from here are ==not== interently safe as of right now. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet.

2. Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps.

## Updates
Don't forget to git pull to get a lot of new optimizations + updates. If SD breaks, go backward in commits until it starts working again

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
		a. if this doesn't work, run ```python -m venv venv``` beforehandww
	3. ```git pull```
	4. ```pip install -r requirements.txt```

## Localizations
French:
* https://rentry.org/stablediffusionfr (contains four localizations: Voldy, sdmodels, sdgoldmine, sdupdates3)

---

## Contents
- [Tutorial](#tutorial)
- [Getting Started](#getting-started)
	- [AMD](#amd)
	- [Linux](#linux)
	- [CPU](#cpu)
	- [Apple Silicon](#apple-silicon)
- [Troubleshooting](#troubleshooting)
- [Repositories](#repositories)
- [Prompting](#prompting)
	- [Documents](#documents)
	- [Prompt Database](#prompt-database)
	- [Tags](#tags)
		- [Tag Rankings](#tag-rankings)
		- [Tag Comparisons](#tag-comparisons)
	- [Artist Comparisons](#artist-comparisons)
		- [Images](#images)
		- [Sites](#sites)
	- [Other Comparisons](#other-comparisons)
	- [Tips](#tips)
	- [Negatives](#negatives)
	- [Extensions](#extensions)
	- [Wildcards](#wildcards)
- [Plugins for External Apps](#plugins-for-external-apps)
- [Downloads](#downloads)
	- [Models](#models)
	- [Dreambooth Models](#dreambooth-models)
	- [Embeddings](#embeddings)
	- [Hypernetworks](#hypernetworks)
	- [Misc](#misc)
		- [Aesthetic Gradients](#aesthetic-gradients)
		- [VAEs](#vaes)
		- [Dead/Missing](#deadmissing)
- [Training](#training)
- [FAQ](#faq)
- [Glossary](#glossary)

## Tutorial
Hypertextbook: https://rentry.org/sdhypertextbook This is a tutorial/commentary to guide a newcomer how to setup and use Stable Diffusion to its fullest. It's meant to be a supplementary to SD Goldmine: https://rentry.org/sdgoldmine, but can be used without it.

## Getting Started
- NAI Speedrun: https://rentry.org/nai-speedrun :cucumber: Easy to follow tutorial with pictures that gets you setup with a 1:1 recreation of NovelAI. Takes < 5 minutes (minus the download times)
- Official Guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs Official AUTOMATIC1111 webui install guide for NVIDIA (Windows and Linux)
- Voldy: https://rentry.org/voldy In-depth tutorial that's been around for a few months. Can help if the speedrun doesn't work
- Emulate NovelAI: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017 A discussion that takes you through emulating NovelAI. Has troubleshooting in the comments

### AMD
AMD isn't as easy to setup as NVIDIA. I don't have an AMD so I don't know if these guides are good
- :cucumber: OnnxDiffusersUI https://github.com/azuritecoin/OnnxDiffusersUI A compilation of guides. Contains another version of Stable Diffusion
- https://rentry.org/sd-amd-gfx803-gentoo Stable Diffusion with AMD RX580 on Gentoo (and possibly other RX4xx and RX5xx AMD cards)
- https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-AMD-GPUs Guide from the official AUTOMATIC1111 webui wiki
- https://rentry.org/sdamd Seems to be similar to the one above
- https://rentry.org/sd-nativeisekaitoo 
- https://rentry.org/ayymd-stable-diffustion-v1_4-guide

### Linux
Honestly I don't know what goes here. I'll add a guide if I remember

### CPU
CPU is even less documented. I don't use my CPU for SD, so I don't know if these guides are good

- https://rentry.org/cputard

### Apple Silicon
Even less documented
- :cucumber: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon

## Troubleshooting
- Asuka Euler: https://imgur.com/a/DCYJCSX
- Asuka Euler a: https://imgur.com/a/s3llTE5

Why are my outputs black? (Any card)
> Add " --no-half-vae " (remove the quotations) to your commandline args in webui-user.bat

Why are my outputs black? (16xx card)
> Add " --precision full --no-half " (remove the quotations) to your commandline args in webui-user.bat

## Repositories
These are repositories containing general AI knowledge

English:
- :cucumber: /sdg/ https://boards.4channel.org/g/catalog#s=sdg
- :cucumber: /hdg/ https://boards.4chan.org/h/catalog#s=hdg
- :cucumber: /vt/ https://boards.4channel.org/vt/catalog#s=vtai
- :cucumber: Stable Diffusion Reddit https://www.reddit.com/r/StableDiffusion/

Korean:
- Korean wiki: https://arca.live/b/aiart

## Prompting

### Documents
These are documents containing general prompting knowledge

English:
- English Grimoire: https://lunarmimi.net/freebies/novelai-anime-girl-prompt-guide/ An AI prompt guide by Lunar Mimi
- Prompt book: https://openart.ai/promptbook A prompt guide by PublicPrompts and OpenArt

Chinese:
- Chinese scroll collection: https://note.com/sa1p/
- Scroll 1: https://docs.qq.com/doc/DWHl3am5Zb05QbGVs
	* Site: https://aiguidebook.top/
	* Backup: https://www105.zippyshare.com/v/lUYn1pXB/file.html
	* translated + download (not sure if safe): https://mega.nz/folder/MssgiRoT#enJklumlGk1KDEY_2o-ViA
	* another backup? https://note.com/sa1p/n/ne71c846326ac
	* another backup: https://files.catbox.moe/tmvjd7.zip
- Scroll 2: https://docs.qq.com/doc/DWGh4QnZBVlJYRkly
- Scroll 3 (spooky): https://docs.qq.com/doc/DWEpNdERNbnBRZWNL
- Tome: https://docs.qq.com/doc/DSHBGRmRUUURjVmNM
- Tome 2 (missing link)
- Spellbook: https://docs.qq.com/doc/DWHFOd2hDSFJaamFm
	* https://www.bilibili.com/read/cv19903596
	* https://www.bilibili.com/read/cv19903680

Japanese:
- Japenese wiki: https://seesaawiki.jp/nai_ch/
- Scroll: https://p1atdev.notion.site/021f27001f37435aacf3c84f2bc093b5?p=f9d8c61c4ed8471a9ca0d701d80f9e28
	* author: https://twitter.com/p1atdev_art/

Korean:
- Korean 1: https://arca.live/b/aiart/60392904
- Korean 2: https://arca.live/b/aiart/60466181

### Prompt Database
- Anon's prompt collection for characters from anime series: https://mega.nz/folder/VHwF1Yga#sJhxeTuPKODgpN5h1ALTQg
- :cucumber: Hololive (1): https://rentry.org/3y56t Anon's prompt collection to create Hololive girls
- Hololive (2): https://rentry.org/q8x5y Another anon's prompt collection to create Hololive girls
- Krea AI prompt database: https://github.com/krea-ai/open-prompts
- Prompt search (1): https://www.ptsearch.info/home/
- Prompt search (2): http://novelai.io/
- 4chan sdg prompt search: https://desuarchive.org/g/search/text/masterpiece/
- 4chan hdg prompt search: https://archived.moe/_/search/text/masterpiece/
- 4chan vt prompt search: https://archive.alice.al/vt/search/text/masterpiece/
- PublicPrompts: https://publicprompts.art/ Database of prompts and dreambooth models
	- Discord: https://discord.com/invite/jvQJFFFx26

### Tips
- Usage of spoken squiggle: https://twitter.com/AI_Illust_000/status/1588838369593032706

### Negatives
- Big negative: https://pastes.io/x9crpin0pq
- Fat negative: https://www.reddit.com/r/WaifuDiffusion/comments/yrpovu/img2img_from_my_own_loose_sketch/
- Big negative prompt that's apparently pretty good: https://files.catbox.moe/gaarzy.png

## Tags
- :cucumber: Danbooru tags: https://danbooru.donmai.us/wiki_pages/tag_groups
- Danbooru artist tags: https://danbooru.donmai.us/artists

### Tag Rankings
- :cucumber: General tag effects on img: https://pastebin.com/GurXf9a4
- Prompt rankings: https://files.catbox.moe/hqs4yf.pdf (reupload from https://docs.google.com/document/d/1Vw-OCUKNJHKZi7chUtjpDEIus112XBVSYHIATKi1q7s/edit?usp=sharing)
- Ranked and classified danbooru tags, sorted by amount of pictures, and ranked by type and quality (WD): https://cdn.discordapp.com/attachments/1029235713989951578/1038585908934483999/Kopi_af_WAIFU_MASTER_PROMPT_DANBOORU_LIST.pdf

### Tag Comparisons
- Emoji/emoticon comparisons: https://docs.google.com/spreadsheets/d/1aTYr4723NSPZul6AVYOX56CVA0YP3qPos8rg4RwVIzA/edit#gid=1453378351
	- Emojis are one character that can portray multiple concepts
	- 🕊💥😱😲😶🙄 leads to https://files.catbox.moe/biy755.png
	- 🌷🕊🗓👋😛👋 leads to https://files.catbox.moe/7khxe0.png
- Class comparison: https://files.catbox.moe/c1yfvf.jpg (MASSIVE IMAGE)
	- Smaller: https://files.catbox.moe/vntwk1.jpg, https://files.catbox.moe/t8teqj.jpg
	- Prompts: https://pastebin.com/SEb876pq
- Clothing comparison: https://files.catbox.moe/z3n66e.jpg
- "Punk" Comparison: https://files.catbox.moe/se3533.png
- NAI tag experiments (has artists): https://zele.st/NovelAI/
- Pre-modern art: https://www.artrenewal.org/Museum/Search#/
- View what SD thinks is a tag: https://dict.latentspace.observer/

## Comparisons:  

### Artists

#### Images:
- :cucumber: Comparison (1): https://imgur.com/a/hTEUmd9
	- Alt: https://i.redd.it/llok0ydfhsu91.jpg (https://reddit.com/r/NovelAi/comments/y879x1/i_made_an_experiment_with_different_artists_here/)
	- Alt: https://files.catbox.moe/9wgqx9.jpg
- Comparison (2): https://files.catbox.moe/kulo8m.jpg
	- OCR to get the artists: https://pastebin.com/JB9QcnLZ
- Comparison (3): https://files.catbox.moe/y6bff0.rar
- Comparison (4) (Stable Diffusion v1.5, Waifu Diffusion v1.3, Trinart): https://imgur.com/a/ADPHh9q
- Comparison (5) (3gb, 90x90 different artist combinations on untampered WD v1.3.)
	- One image: https://mega.nz/file/ACtigCpD#f9zP9h1AU_0_4DPsBnvdhnUYdQmIJMb4pyc6PJ4J-FU
	- Individual images: https://mega.nz/file/YPsT1TDJ#XAayj1jYmRSIyzJ-A1pKB8HyxeDib4a4xuo2lxMx7oA
- Comparison (6) (Berry Mix, Clip 2): https://imgur.com/a/zzXqLPc
- Comparison (7) (Berry Mix, Clip 1): https://imgur.com/a/TDGBAlc
- Comparison (8) of using and not using "by artist [first name] [last name]": https://drive.google.com/drive/folders/1qATxaaOb97fxgm5QY8MXIoMAX3FI6WZ0?usp=sharing 
	- https://www.reddit.com/r/StableDiffusion/comments/yiny15/by_artist_firstname_lastname_really_does_makes_a/
- Comparisons (9) of 421 different artists in different models.
	- Berry Mix: https://mega.nz/file/8OlUkapK#4XpOm4kOcw3LOJZeSuSZbO89tRrAuRO_RSfmu_RqzWA
	- SD v1.5 (CLIP 1): https://mega.nz/file/dDU2WB5B#wFsVS0RUX6YK2IJiOtQ5nI7sMMrWEqZg2r3fZrCQ4OI
	- SD v1.5 (CLIP 2): https://mega.nz/file/lS1iyQCT#zJhV6URsT01QJpYdqbf3Jubhyi09rXn8FFT-HaXvgd0

#### Sites:
- Big Titty Anon's List of Artists (contains some notes): https://rentry.org/anime_and_titties 
- :cucumber: Study (1) (SD 1.4): https://rentry.org/artists_sd-v1-4
	- Anon's analysis of artists: https://rentry.org/oadb5
- Study (2): https://www.urania.ai/top-sd-artists
- Study (3) (SD 1.5): https://docs.google.com/spreadsheets/d/1SRqJ7F_6yHVSOeCi3U82aA448TqEGrUlRrLLZ51abLg/htmlview#
- Study (4): https://sdartists.app/
- Study (5) (has multiple views): https://proximacentaurib.notion.site/e28a4f8d97724f14a784a538b8589e7d?v=ab624266c6a44413b42a6c57a41d828c
- Study (6): https://mpost.io/midjourney-and-dall-e-artist-styles-dump-with-examples-130-famous-ai-painting-techniques/
- Study (7): https://sgreens.notion.site/sgreens/4ca6f4e229e24da6845b6d49e6b08ae7
- Study (8): https://arthive.com/artists
- Study (9): https://artiststostudy.pages.dev/
- Study (10) (414 artists, Berry Mix): https://mega.nz/file/MX00jb6I#sWbvlt8AhH0B2CZTJJVmfz-LTZIB9O0sLYqjoWbvwN0
- Study (11) (558 artists recognized by SD): https://decentralizedcreator.com/list-of-artists-supported-by-stable-diffusion/

## Other Comparisons  
- :cucumber: Anything v3 (all samplers and clip skip, nsfw): https://ikaridevgit.github.io/Clip-skip_sampler-sd-anything-comparison/
- :cucumber: Anythingv3 comparison 2 (all samplers and clip skip, sfw): https://ikaridevgit.github.io/sampler-sd-anything-comparison/
- SD 1.4 vs 1.5: https://postimg.cc/gallery/mhvWsnx
- NAI vs Anything: https://www.bilibili.com/read/cv19603218
- Model merge (1): https://files.catbox.moe/rcxqsi.png
- Model merge (2): https://files.catbox.moe/vgv44j.jpg
- Samplers vs Steps (1): https://files.catbox.moe/csrjt5.jpg
- Samplers vs Steps (2): https://i.redd.it/o440iq04ocy91.jpg (https://www.reddit.com/r/StableDiffusion/comments/ynt7ap/another_new_sampler_steps_comparison/)
- Samplers vs Steps (3): https://i.redd.it/ck4ujoz2k6y91.jpg (https://www.reddit.com/r/StableDiffusion/comments/yn2yp2/automatic1111_added_more_samplers_so_heres_a/)
- Samplers vs Steps (4): https://files.catbox.moe/u2d6mf.png
- Samplers vs Steps (5): https://www.reddit.com/r/StableDiffusion/comments/xmwcrx/a_comparison_between_8_samplers_for_5_different/
- Samplers vs Steps (6): https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/4363
- Samplers: https://files.catbox.moe/5hfl9h.png
- VAEs (none, SD, WD, Anything, NAI): https://i.4cdn.org/g/1669056754991690.png
- Clip Skip comparison for Anything.ckpt (missing)

### Extensions
Some extensions I came across that are probably in the webui extension browser
- :cucumber: Dynamic prompts: https://github.com/adieyal/sd-dynamic-prompts Supercharge your prompting with advanced prompt features
	- Guide: https://www.reddit.com/r/StableDiffusion/comments/ynztiz/how_to_turbocharge_your_prompts_using/
- Wildcard extension: https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards/ Classic wildcard extension
- Artist inspiration extension: https://github.com/yfszzx/stable-diffusion-webui-inspiration
	- https://huggingface.co/datasets/yfszzx/inspiration

### Wildcards  
Collections:  
- Collection (1): https://rentry.org/sdWildcardLists
	- https://desuarchive.org/g/thread/89006003#89007479
- Collection (2): https://cdn.lewd.host/EtbKpD8C.zip
- Collection (3): https://github.com/Lopyter/stable-soup-prompts/tree/main/wildcards
- Collection (4): https://github.com/Lopyter/sd-artists-wildcards 
	- Artist wildcard text files split by category according to Automatic1111's csv file.
- Collection (5): https://github.com/jtkelm2/stable-diffusion-webui-1/tree/master/scripts/wildcards
- :cucumber: Collection (6): https://rentry.org/NAIwildcards
	- Zipped Collection: https://files.catbox.moe/s7expb.7z
- :cucumber: Collection (7): https://files.catbox.moe/ipqljx.zip 483 txt files, huge dump (for Danbooru trained models)
	- old 329 version: https://files.catbox.moe/qy6vaf.zip
	- old 314 version: https://files.catbox.moe/11s1tn.zip
- Collection (8): https://www.mediafire.com/file/iceamfawqhn5kvu/wildcards.zip/file
- Collection (9): https://files.catbox.moe/88s7bf.zip Clothing
- :cucumber: Collection (10): https://files.catbox.moe/qyybik.zip
- Collection (11): https://cdn.lewd.host/4Ql5bhQD.7z
- :cucumber: Collection (12): https://files.catbox.moe/hz5mom.zip Danbooru tag group wildcard dump organized into folders

- wildcardNames.txt generation script: https://files.catbox.moe/c1c4rx.py
- Another script: https://files.catbox.moe/hvly0p.rar
- Script: https://gist.github.com/h-a-te/30f4a51afff2564b0cfbdf1e490e9187
- UMI AI: https://www.patreon.com/posts/umi-ai-official-73544634
	- Check the presets folder for a lot of dumps

Dump:
- faces https://rentry.org/pu8z5
- focus https://rentry.org/rc3dp
- poses https://rentry.org/hkuuk
- times https://rentry.org/izc4u
- views https://rentry.org/pv72o
- Clothing: https://pastebin.com/EyghiB2F
- 316 colors list: https://pastebin.com/s4tqKB8r
- 82 colors list: https://pastebin.com/kiSEViGA
- Backgrounds: https://pastebin.com/FCybuqYW
- More clothing: https://pastebin.com/DrkG1MRw
- Styles: https://pastebin.com/71HTfsML
- Word list (small): https://cdn.lewd.host/EtbKpD8C.zip 
- Emotions/expressions: https://pastebin.com/VVnH2b83
- Clothing: https://pastebin.com/cXxN1fJw
- Cum: https://rentry.org/hoom5
- Locations: https://pastebin.com/R6ugwd2m
- Clothing/outfits: https://pastebin.com/Xhhnyfvj
- Locations: https://pastebin.com/uyDJMnvC
- Clothes: https://pastebin.com/HaL3rW3j
- Color (has nouns): https://pastebin.com/GTAaLLnm
- Artists: https://pastebin.com/1HpNRRJU
- Animals: https://pastebin.com/aM4PJ2YY
- Food: https://pastebin.com/taFkYwt9
- Characters: https://files.catbox.moe/xe9qj7.txt
- Backgrounds: https://pastebin.com/gVue2q8g 
- Outfits: https://files.catbox.moe/y75qda.txt
- Settings + Minerals: https://pastebin.com/9iznuYvQ
- Hairstyles: https://pastebin.com/X39Kzxh7
- Hairstyles 2: https://pastebin.com/bRWu1Xvv
- Danbooru Poses: https://pastebin.com/RgerA8Ry
- Outfits: https://pastebin.com/Z9aHVpEy
- Poses: https://rentry.org/m9dz6
- Clothes: https://pastebin.com/4a0BscGr
- sex positions: https://files.catbox.moe/tzibuf.txt
- Angles: https://pastebin.com/T8w8HEED
- Poses: https://pastebin.com/bgkunjw2
- Hairstyles: https://pastebin.com/GguTseaR
- Actresses: https://raw.githubusercontent.com/Mylakovich/SD-wildcards/main/wildcards/actress.txt
- Punks: https://pastebin.com/rw2fPSHe
- Curated RPG Character classes (based on TTRPG character class names): https://pastebin.com/6ujb7NNe
- Hairstyle: https://pastebin.com/Ux6SdTdp

## Plugins for External Apps
I didn't check the safety of these plugins, but you can check the open-source ones yourself

Photoshop:  
- Defuser: https://internationaltd.github.io/defuser/ Photoshop/Krita, free, features listed inside
	- https://github.com/internationalTD/defuser
- IvyPhotoshopDiffusion: https://github.com/Invary/IvyPhotoshopDiffusion Photoshop, free, features listed inside
- AestusAi: Photoshop, free, closed source (might change later), website wip
	- https://twitter.com/AestusAi
	- https://discord.gg/U6DG9zthvJ
- FlyingDog: https://www.flyingdog.de/sd/ Photoshop, paid, closed source 

Krita:  
- :cucumber: auto-sd-paint-ext: https://github.com/Interpause/auto-sd-paint-ext Free, features listed inside
- FlyingDog: https://www.flyingdog.de/sd/en/ free
	- Github: https://github.com/imperator-maximus/stable-diffusion-krita

GIMP:  
- Gimp Stable Diffusion: https://github.com/blueturtleai/gimp-stable-diffusion free, open source, features listed inside

Blender:  
- Dream Textures: https://github.com/carson-katri/dream-textures Free, Stable Diffusion built-in to the Blender shader editor
- AI Render: https://github.com/benrugg/AI-Render Free, Stable Diffusion in Blender
---
Unsorted but update was pushed 



Prompt word/phrase collection: https://huggingface.co/spaces/Gustavosta/MagicPrompt-Stable-Diffusion/raw/main/ideas.txt


* Anon says that "8k, 4k, (highres:1.1), best quality, (masterpiece:1.3)" leads to nice details

According to an anon, the vae seems to be provide saturation/contrast and some line thickness (vae-ft-ema-56000-ema-pruned, https://huggingface.co/stabilityai/sd-vae-ft-ema-original/blob/main/vae-ft-ema-560000-ema-pruned.ckpt). Example (left with 56k, right with anything vae): https://i.4cdn.org/h/1669086238979897s.jpg


Japanese prompt generator: https://magic-generator.herokuapp.com/
Build your prompt (chinese): https://tags.novelai.dev/
NAI Prompts: https://seesaawiki.jp/nai_ch/d/%c8%c7%b8%a2%a5%ad%a5%e3%a5%e9%ba%c6%b8%bd/%a5%a2%a5%cb%a5%e1%b7%cf
Prompt similarity tester: https://gitlab.com/azamshato/simula

* Apparently a good subwiki: https://seesaawiki.jp/nai_ch/d/%c7%ed%a4%ae%a5%b3%a5%e9%a5%c6%a5%af



Multilingual study: https://jalonso.notion.site/Stable-Diffusion-Language-Comprehension-5209abc77a4f4f999ec6c9b4a48a9ca2

Aesthetic value (imgs used to train SD): https://laion-aesthetic.datasette.io/laion-aesthetic-6pls
Clip retrieval (text to CLIP to search): https://rom1504.github.io/clip-retrieval/

Aesthetic scorer python script: https://github.com/grexzen/SD-Chad
Another scorer: https://github.com/christophschuhmann/improved-aesthetic-predictor
Supposedly another one?: https://developer.huawei.com/consumer/en/hiai/engine/aesthetic-score
Another Aesthetic Scorer: https://github.com/tsngo/stable-diffusion-webui-aesthetic-image-scorer

NAI to webui translator (not 100% accurate): https://seesaawiki.jp/nai_ch/d/%a5%d7%a5%ed%a5%f3%a5%d7%a5%c8%ca%d1%b4%b9

Prompt editing parts of image but without using img2img/inpaint/prompt editing guide by anon: https://files.catbox.moe/fglywg.JPG

Tip Dump: https://rentry.org/robs-novel-ai-tips
Tips: https://github.com/TravelingRobot/NAI_Community_Research/wiki/NAI-Diffusion:-Various-Tips-&-Tricks
Info dump of tips: https://rentry.org/Learnings
Outdated guide: https://rentry.co/8vaaa
Tip for more photorealism: https://www.reddit.com/r/StableDiffusion/comments/yhn6xx/comment/iuf1uxl/
* TLDR: add noise to your img before img2img

NAI prompt tips: https://docs.novelai.net/image/promptmixing.html
NAI tips 2: https://docs.novelai.net/image/uifunctionalities.html

Masterpiece vs no masterpiece: https://desuarchive.org/g/thread/89714899#89715160

DPM-Solver Github: https://github.com/LuChengTHU/dpm-solver

>Prompt: 1girl, pointy ears, white hair, medium hair, ahoge, hair between eyes, green eyes, medium:small breasts, cyberpunk, hair strand, dynamic angle, cute, wide hips, blush, sharp eyes, ear piercing, happy, hair highlights, multicoloured hair, cybersuit, cyber gas mask, spaceship computers, ai core, spaceship interior
>Negative prompt: lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, animal ears, panties
>
>Original image:
>Steps: 50, Sampler: DDIM, CFG scale: 11, Seed: 3563250880, Size: 1024x1024, Model hash: cc024d46, Denoising strength: 0.57, Clip skip: 2, ENSD: 31337, First pass size: 512x512
>NAI/SD mix at 0.25



Deep Danbooru: https://github.com/KichangKim/DeepDanbooru
Demo: https://huggingface.co/spaces/hysts/DeepDanbooru

Embedding tester: https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer

Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

Euler vs. Euler A: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017#discussioncomment-4021588
* Euler: https://cdn.discordapp.com/attachments/1036718343140409354/1036719238607540296/euler.gif
* Euler A: https://cdn.discordapp.com/attachments/1036718343140409354/1036719239018590249/euler_a.gif

According to anon: DPM++ should converge to result much much faster than Euler does. It should still converge to the same result though.

(info by anon) According to https://arxiv.org/pdf/2211.01095.pdf, the M samplers are better than the S samplers

Seed hunting: 
* By nai speedrun asuka imgur anon:
	>made something that might help the highres seed/prompt hunters out there. this mimics the "0x0" firstpass calculation and suggests lowres dimensions based on target higheres size. it also shows data about firstpass cropping as well. it's a single file so you can download and use offline. picrel.
	>https://preyx.github.io/sd-scale-calc/
	>view code and download from
	>https://files.catbox.moe/8ml5et.html
	>for example you can run "firstpass" lowres batches for seed/prompt hunting, then use them in firstpass size to preserve composition when making highres. 

Script for tagging (like in NAI) in AUTOMATIC's webui: https://github.com/DominikDoom/a1111-sd-webui-tagcomplete
Danbooru Tag Exporter: https://sleazyfork.org/en/scripts/452976-danbooru-tags-select-to-export
Another: https://sleazyfork.org/en/scripts/453380-danbooru-tags-select-to-export-edited
Tags (latest vers): https://sleazyfork.org/en/scripts/453304-get-booru-tags-edited
Basic gelbooru scraper: https://pastebin.com/0yB9s338
Scrape danbooru images and tags like fetch.py for e621 for tagging datasets: https://github.com/JetBoom/boorutagparser
UMI AI: https://www.patreon.com/klokinator
* Discord: https://discord.gg/9K7j7DTfG2
* Author is looking for help filling out and improving wildcards
	* Ex: https://cdn.discordapp.com/attachments/1032201089929453578/1034546970179674122/Popular_Female_Characters.txt
	* Author: Klokinator#0278
	* Looking for wildcards with traits and tags of characters
* Code: https://github.com/Klokinator/UnivAICharGen/

Random Prompts: https://rentry.org/randomprompts
Python script of generating random NSFW prompts: https://rentry.org/nsfw-random-prompt-gen
Prompt randomizer: https://github.com/adieyal/sd-dynamic-prompting 
Prompt generator: https://github.com/h-a-te/prompt_generator
* apparently UMI uses these?

http://dalle2-prompt-generator.s3-website-us-west-2.amazonaws.com/
https://randomwordgenerator.com/
funny prompt gen that surprisingly works: https://www.grc.com/passwords.htm
Unprompted extension released: https://github.com/ThereforeGames/unprompted
* HAS ADS

StylePile: https://github.com/some9000/StylePile
script that pulls prompt from Krea.ai and Lexica.art based on search terms: https://github.com/Vetchems/sd-lexikrea
randomize generation params for txt2img, works with other extensions: https://github.com/stysmmaker/stable-diffusion-webui-randomize

Ideas for when you have none: https://pentoprint.org/first-line-generator/
Colors: http://colorcode.is/search?q=pantone

* Image editor for SD for inpainting/outpainting/txt2img/img2img: https://github.com/BlinkDL/Hua
* https://www.painthua.com/ - New GUI focusing on Inpainting and Outpainting
* https://www.reddit.com/r/StableDiffusion/comments/ygp0iv/painthuacom_new_gui_focusing_on_inpainting_and/
* To use it with webui add this to webui-user.bat:  --api --cors-allow-origins=https://www.painthua.com 
* Vid: https://www.bilibili.com/video/BV16e4y1a7ne/

* CLIPSeg (text-based inpainting): https://huggingface.co/spaces/nielsr/text-based-inpainting



External masking for inpainting (no more brush or WIN magnifier): https://github.com/dfaker/stable-diffusion-webui-cv2-external-masking-script
anon: theres a commanda rg for adding basic painting, its '--gradio-img2img-tool'

Script collection: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts
Prompt matrix tutorial: https://gigazine.net/gsc_news/en/20220909-automatic1111-stable-diffusion-webui-prompt-matrix/
Animation Script: https://github.com/amotile/stable-diffusion-studio
Animation script 2: https://github.com/Animator-Anon/Animator
Video Script: https://github.com/memes-forever/Stable-diffusion-webui-video
Masking Script: https://github.com/dfaker/stable-diffusion-webui-cv2-external-masking-script
XYZ Grid Script: https://github.com/xrpgame/xyz_plot_script
Vector Graphics: https://github.com/GeorgLegato/Txt2Vectorgraphics/blob/main/txt2vectorgfx.py
Txt2mask: https://github.com/ThereforeGames/txt2mask
Prompt changing scripts:
* https://github.com/yownas/seed_travel
* https://github.com/feffy380/prompt-morph
* https://github.com/EugeoSynthesisThirtyTwo/prompt-interpolation-script-for-sd-webui
* https://github.com/some9000/StylePile

Interpolation script (img2img + txt2img mix): https://github.com/DiceOwl/StableDiffusionStuff
* https://www.reddit.com/r/StableDiffusion/comments/ycgfgo/interpolate_script/

img2tiles script: https://github.com/arcanite24/img2tiles
Script for outpainting: https://github.com/TKoestlerx/sdexperiments
Img2img animation script: https://github.com/Animator-Anon/Animator/blob/main/animation_v6.py
* Can use in txt2img mode and combine with https://film-net.github.io/ for content aware interpolation

Google's interpolation script: https://github.com/google-research/frame-interpolation

Deforum guide: https://docs.google.com/document/d/1RrQv7FntzOuLg4ohjRZPVL7iptIyBhwwbcEYEW2OfcI/edit
Animation Guide: https://rentry.org/AnimAnon#introduction
Rotoscope guide: https://rentry.org/AnimAnon-Rotoscope
Chroma key after SD (fully prompted?): https://files.catbox.moe/d27xdl.gif 
* Cool mmd vid (20 frames, I think it uses chroma key): https://files.catbox.moe/jtp14x.mp4

Prompt travel: https://github.com/Kahsolt/stable-diffusion-webui-prompt-travel
* Example (30 min, 5k steps, 124 images): https://i.4cdn.org/g/1668879797247188.webm

More animation guide: https://www.reddit.com/r/StableDiffusion/comments/ymwk53/better_frame_consistency/
Animation guide + example for face: https://www.reddit.com/r/StableDiffusion/comments/ys434h/animating_generated_face_test/
Something for aninmation: https://github.com/nicolai256/Few-Shot-Patch-Based-Training

Animating faces by anon: 
* https://github.com/yoyo-nb/Thin-Plate-Spline-Motion-Model
* How to Animate faces from Stable Diffusion!

``` python
workflow looks like this:
>generate square portrait (i use 1024 for this example)
>create or find driving video
>crop driving video to square with ffmpeg, making sure to match the general distance from camera and face position(it does not do well with panning/zooming video or too much head movement)
>run thin-plate-spline-motion-model
>take result.mp4 and put it into Video2x (Waifu2x Caffe)
>put into flowframes for 60fps and webm

>if you don't care about upscaling it makes 256x256 pretty easily
>an extension for webui could probably be made by someone smarter than me, its a bit tedious right now with so many terminals

here is a pastebin of useful commands for my workflow
https://pastebin.com/6Y6ZK8PN
```

Another person who used it: https://www.reddit.com/r/StableDiffusion/comments/ynejta/stable_diffusion_animated_with_thinplate_spline/

Img2img megalist + implementations: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2940

Runway inpaint model: https://huggingface.co/runwayml/stable-diffusion-inpainting
* Tutorial from their github: https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion

Inpainting Tips: https://www.pixiv.net/en/artworks/102083584
Rentry version: https://rentry.org/inpainting-guide-SD

Extensions:
Artist inspiration: https://github.com/yfszzx/stable-diffusion-webui-inspiration
* https://huggingface.co/datasets/yfszzx/inspiration
* delete the 0 bytes folders from their dataset zip or you might get an error extracting it

History: https://github.com/yfszzx/stable-diffusion-webui-images-browser 
Collection + Info: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions
Deforum (video animation): https://github.com/deforum-art/deforum-for-automatic1111-webui
* Math: https://docs.google.com/document/d/1pfW1PwbDIuW0cv-dnuyYj1UzPqe23BlSLTJsqazffXM/edit
	* https://www.desmos.com/calculator/njw3uckjlo
	* https://www.desmos.com/calculator/5nizby2zbn
* Blender camera animations to deforum: https://github.com/micwalk/blender-export-diffusion
* Tutorial: https://www.youtube.com/watch?v=lztn6qLc9UE
* Diffusion_cadence variation value comparison: https://www.reddit.com/r/StableDiffusion/comments/yh3dno/diffusion_cadence_variation_testing_values_to/

Auto-SD-Krita: https://github.com/Interpause/auto-sd-paint-ext

ddetailer (object detection and auto-mask, helpful in fixing faces without manually masking): https://github.com/dustysys/ddetailer
Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients
Autocomplete Tags: https://github.com/DominikDoom/a1111-sd-webui-tagcomplete
Prompt Randomizer: https://github.com/adieyal/sd-dynamic-prompting
Wildcards: https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards/
Wildcard script + collection of wildcards: https://app.radicle.xyz/seeds/pine.radicle.garden/rad:git:hnrkcfpnw9hd5jb45b6qsqbr97eqcffjm7sby
Symmetric image script (latent mirroring): https://github.com/dfaker/SD-latent-mirroring
* Comparisons: 
	* No mirroring - https://files.catbox.moe/blbnwt.png (embed)
	* Alternate Steps - Roll Channels - fraction 0.2 - https://files.catbox.moe/dprlxr.png (embed)
	* Alternate Steps - Roll Channels - fraction 0.3 - https://files.catbox.moe/7az24b.png

macOS Finder right-click menu extension: https://github.com/anastasiuspernat/UnderPillow
Search danbooru for tags directly in AUTOMATIC1111's webui extension: https://github.com/stysmmaker/stable-diffusion-webui-booru-prompt
* Supports post IDs and all the normal Danbooru search syntax

Clip interrogator: https://colab.research.google.com/github/pharmapsychotic/clip-interrogator/blob/main/clip_interrogator.ipynb
2 (apparently better than AUTO webui's interrogate): https://huggingface.co/spaces/pharma/CLIP-Interrogator, https://github.com/pharmapsychotic/clip-interrogator

Enchancement Workflow with SD Upscale and inpainting by anon: https://pastebin.com/8WVyDxt9

Upscaling + detail with SD Upscale: https://www.reddit.com/r/StableDiffusion/comments/xkjjf9/upscale_to_huge_sizes_and_add_detail_with_sd/?context=3

Inpainting a face by anon:
>send the picture to inpaint
>modify the prompt to remove anything related to the background
>add (face) to the prompt
>slap a masking blob over the whole face
>mask blur 10-16 (may have to adjust after), masked content: original, inpaint at full resolution checked, full resolution padding 0, sampling steps ~40-50, sampling method DDIM, width and height set to your original picture's full res
>denoising strength .4-.5 if you want minor adjustments, .6-.7 if you want to really regenerate the entire masked area
>let it rip

* AUTOMATIC1111 webui modification that "compensates for the natural heavy-headedness of sd by adding a line from 0 -> sqrt(2) over the 0 -> 74 token range (anon)" (evens out the token weights with a linear model, helps with the weight reset at 75 tokens (?))
	* https://rentry.org/wkk37

**VAEs**

Tutorial + how to use on ALL models (applies for the NAI vae too): https://www.reddit.com/r/StableDiffusion/comments/yaknek/you_can_use_the_new_vae_on_old_models_as_well_for/

* SD 1.4 Anime styled: https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime.ckpt
	* https://twitter.com/haruu1367/status/1579286947519864833
* Stability AI's VAE: https://huggingface.co/stabilityai 
	* Comparisons: https://huggingface.co/stabilityai/sd-vae-ft-mse-original
	* an anon recommended vae-ft-mse-840k-ema-pruned: https://huggingface.co/stabilityai/sd-vae-ft-mse-original/resolve/main/vae-ft-mse-840000-ema-pruned.ckpt, https://huggingface.co/stabilityai/sd-vae-ft-mse-original/tree/main
* Trinart's vae (the autencoder fix): https://huggingface.co/naclbit/trinart_characters_19.2m_stable_diffusion_v1

**Booru tag scraping:**
* https://sleazyfork.org/en/scripts/451098-get-booru-tags 
	* script to run in browser, hover over pic in Danbooru and Gelbooru
* https://rentry.org/owmmt 
	* another script 
* https://pastecode.io/s/jexs5p9c
	* another script, maybe pickle
	* press tilde on dan, gel, e621 
* https://textedit.tools/
	* if you want an online alternative
* https://github.com/onusai/grab-booru-tags
	* works with e621, dev will try to get it to work with rule34.xxx
	* https://pastecode.io/s/jexs5p9c
* https://pastecode.io/s/61owr7mz
	* Press ] on the page you want the tags from
* Another script: https://pastecode.io/s/q6fpoa8k
* Another: https://pastecode.io/s/t7qg2z67
* Github for scraper: https://github.com/onusai/grab-booru-tags 
* Tag copier: https://greasyfork.org/en/scripts/453443-danbooru-tag-copier


**Creating fake animes:**
* https://rentry.org/animedoesnotexist

* Prompt tag comparisons: https://i.4cdn.org/h/1668114368781212.jpg, https://i.4cdn.org/h/1668119420557795.jpg, https://i.4cdn.org/h/1668126729971806.jpg


Some observations by anon:
1. Removing the spaces after the commas changed nothing
2. Using "best_quality" instead of "best_quality" did change the image. masterpiece,best_quality,akai haato but she is a spider,blonde hair,blue eyes
3. Changing all of the spaces into underscores changed the image somewhat substantially.
4. Replacing those commas with spaces changed the image again.

Reduce bias of dreambooth models: https://www.reddit.com/r/StableDiffusion/comments/ygyq2j/a_simple_method_explained_in_the_comments_to/?utm_source=share&utm_medium=web2x&context=3

Landscape tutorial: https://www.reddit.com/r/StableDiffusion/comments/yivokx/landscape_matte_painting_with_stable_diffusion/
* https://preview.redd.it/18v93697u8x91.jpg?width=1000&format=pjpg&auto=webp&s=d31fb3efae70ec5e7c9f02befa04a94371b1bbf6

Anon's process: 
- Start with a prompt to get the general scenario you have in mind, here I was just looking to seggs the rrat so I used the embed here >>36743515 and described some of her character features to help steer the AI (in this case hair details, sharp teeth, her mouse ears and tail) as well as making her be naked and having vaginal sex
- Generate images at a default resolution size (512 by X pixels) at a relative standard number of steps (30 in this case) and keep going until I find an image thats in a position I like (in this case seed 1920052602 gave me a very nice one to work with, as you can see here https://files.catbox.moe/8z2mua.png (embed))
- Copy the seed of the image and paste it into the Seed field on the Web UI, which will maintain the composition of the image. I then double the resolution I was working with (so here I went from 512 by 768 to 1024 by 1536) and checkmark the "Hires fix option" underneath the width and height sliders. Hires fix is the secret sauce on the Web UI that helps maintain the detail of the image when you are upscaling the resolution of the image, and combined with that Upscale latent space option I mentioned earlier it really enhances the detail. With that done you can generate the upscaled image.
- Play around with the weights of the prompt tags and add things to the negatives to fix little things like hair being too red, tummy too chubby, etc. You have to be careful with adding new tags because that can drastically change the image

Anon's booba process:
    >you can generate a perfect barbie doll anatomy but more accurate chuba in curated
    >then switch to full, img2img it on the same seed after blotching nipples on it like a caveman, and hit generate

Boooba v2: 
1. Generate whatever NSFW proompt you were thinking of using the CURATED model, yes, I know that sounds ridiculous https://files.catbox.moe/b6k6i4.png (embed)
2. Inpaint the naughty bits back in. You REALLY don't have to do a good job of this: https://files.catbox.moe/yegjrw.png (embed)
3. Switch to Full after clicking "Save", set Strength to 0.69, Noise to 0.17, and make sure you copy/paste the same seed # back in. Hit Generate: https://files.catbox.moe/8dag88.png (embed)
Compare that with what you'd get trying to generate the same exact proompt using the Full model purely txt2img on the same seed: https://files.catbox.moe/ytfdv3.png (embed)

Img2img rotoscoping tutorial by anon:
``` python
1. extract image sequence from video
2. testing prompt by using the 1st photo from the batch
3. find the suitable prompt that you want, the pose/sexual acts should be the same as the original to prevent weirdness
4. CFG Scale and Denoising Strength is very important
> Low CFG Scale will make your image less follow your prompt and make it more blurry and messy (i use 9-13)
> Denoising Strength determines the mix between your prompt and your image: 0 = Original input 1 = Only Prompt, nothing resemble of the input except the colors.
the interesting thing that i've noticed from Denoising strength is not linear, its behave more exponential ( my speculation is 0-0.6 = still reminds of the original 0.61-0.76 = starting to change 0.77-1 = change a lot )
5. sampler:
> Euler-a is quite nice, but lack of consistency between the step, adding/lower 1 step can change the entire photo
> Euler is better than euler-a in terms of consistency but requires more steps = longer generation time between each image
> DPM++ 2S a Karras is the best in quality (for me) but it is very slow, good for generate single image
> DDIM is the fastest and very useful for this case, 20-30 steps can produces a nice quality anime image.
6. test prompting into a batch of 4-6 to choosing a seed
7. Batch img2img
8. Assembling the generated images into video, i don't want to use eveyframes so i rendered into 2 frame steps and half the frame rate
9. Use Flowframes to interpolate the inbetween frame to match the original video frame rate.
```
Ex: https://files.catbox.moe/e30szo.mp4

File2prompt (I think it's multiple generations in a row?): https://rentry.org/file2prompt

##  Models, Embeddings, and Hypernetworks

* Open source SD model based on chinese text and images: https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1

!!! Downloads listed as "sus" or "might be pickled" generally mean there were 0 replies and not enough "information" (like training info). or, the replies indicated they were suspicious. I don't think any of the embeds/hypernets have had their code checked so they could all be malicious, but as far as I know no one has gotten pickled yet 

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

### **Models***

Model pruner: https://github.com/harubaru/waifu-diffusion/blob/bc626e8/scripts/prune.py

Collection of potentially dangerous models: https://bt4g.org/search/.ckpt/1
Collection?: https://civitai.com/
Huggingface collection: https://huggingface.co/models?pipeline_tag=text-to-image&sort=downloads

* anything.ckpt (v3 6569e224; v2.1 619c23f0), a Chinese finetune/training continuation of NAI, is released: https://www.bilibili.com/read/cv19603218
	* Huggingface, might be pickled: https://huggingface.co/Linaqruf/anything-v3.0/tree/main
		* Uploader pruned one of the 3.0 models down to 4gb
	* Torrent: https://rentry.org/sdmodels#anything-v30-38c1ebe3-1a7df6b8-6569e224
	* Supposed ddl, I didn't check these for pickles: https://rentry.org/NAI-Anything_v3_0_n_v2_1
	* instructions to download from Baidu from outside China and without SMS or an account and with speeds more than 100KBps: 
		>Download a download manager that allows for a custom user-agent (e.g. IDM)
			>If you need IDM, contact me
		>Go here: https://udown.vip/#/
		>In the "在线解析" section, put 'https://pan.baidu.com/s/1gsk77KWljqPBYRYnuzVfvQ' into the first prompt box and 'hheg' in the second (remove the ')
		>Click the first blue button
		>In the bottom box area, click the folder icon next to NovelAI
		>Open your dl manager and add 'netdisk;11.33.3;' into the user-agent section (remove the ')
		>Click the paperclip icon next to the item you want to download in the bottom box and put it into your download manager
		>
		>To get anything v3 and v2.1: first box:https://pan.baidu.com/s/1r--2XuWV--MVoKKmTftM-g, second box:ANYN
			* another link that has 1 letter changed that could mean it's pickled: https://pan.baidu.com/s/1r--2XuWV--MVoKKmTfyM-g
	* seems to be better (e.g. provide more detailed backgrounds and characters) than NAI, but can overfry some stuff. Try lowering the cfg if that happens
	* Passes AUTOMATIC's pickle tester and https://github.com/zxix/stable-diffusion-pickle-scanner, but there's no guarantee on pickle safety, so it still might be ccp spyware
	* Use the vae or else your outputs will have a grey filter
	* Windows Defender might mark this as a virus, it should be a false positive
	* Supposed torrent from anon on /g/ (don't know if safe)
	
potential magnet that someone gave me
``` python
magnet:?xt=urn:btih:689c0fe075ab4c7b6c08a6f1e633491d41186860&dn=Anything-V3.0.ckpt&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce&tr=udp%3a%2f%2f9.rarbg.com%3a2810%2fannounce&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a6969%2fannounce&tr=udp%3a%2f%2fopentracker.i2p.rocks%3a6969%2fannounce&tr=https%3a%2f%2fopentracker.i2p.rocks%3a443%2fannounce&tr=udp%3a%2f%2ftracker.torrent.eu.org%3a451%2fannounce&tr=udp%3a%2f%2fopen.stealth.si%3a80%2fannounce&tr=http%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce&tr=udp%3a%2f%2fvibe.sleepyinternetfun.xyz%3a1738%2fannounce&tr=udp%3a%2f%2ftracker1.bt.moack.co.kr%3a80%2fannounce&tr=udp%3a%2f%2ftracker.zerobytes.xyz%3a1337%2fannounce&tr=udp%3a%2f%2ftracker.tiny-vps.com%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.theoks.net%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.swateam.org.uk%3a2710%2fannounce&tr=udp%3a%2f%2ftracker.publictracker.xyz%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.monitorit4.me%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.moeking.me%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.encrypted-data.xyz%3a1337%2fannounce&tr=udp%3a%2f%2ftracker.dler.org%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.army%3a6969%2fannounce&tr=http%3a%2f%2ftracker.bt4g.com%3a2095%2fannounce
```

Mag2
``` python
Little update, here's the link with all including VAE (second one)
magnet:?xt=urn:btih:689C0FE075AB4C7B6C08A6F1E633491D41186860&dn=Anything-V3.0.ckpt&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

magnet:?xt=urn:btih:E87B1537A4B5B5F2E23236C55F2F2F0A0BB6EA4A&dn=NAI-Anything&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce
```

Mag3
``` python
magnet:?xt=urn:btih:689c0fe075ab4c7b6c08a6f1e633491d41186860&dn=Anything-V3.0.ckpt&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2810%2Fannounce&tr=udp%3A%2F%2Fopentracker.i2p.rocks%3A6969%2Fannounce&tr=https%3A%2F%2Fopentracker.i2p.rocks%3A443%2Fannounce&tr=udp%3A%2F%2Ftracker.torrent.eu.org%3A451%2Fannounce&tr=udp%3A%2F%2Fopen.stealth.si%3A80%2Fannounce&tr=http%3A%2F%2Ftracker.openbittorrent.com%3A80%2Fannounce&tr=udp%3A%2F%2Fvibe.sleepyinternetfun.xyz%3A1738%2Fannounce&tr=udp%3A%2F%2Ftracker1.bt.moack.co.kr%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.zerobytes.xyz%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.theoks.net%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.swateam.org.uk%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.publictracker.xyz%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.monitorit4.me%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.moeking.me%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.encrypted-data.xyz%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.dler.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.army%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.altrosky.nl%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.bt4g.com%3A2095%2Fannounce
```

from: https://bt4g.org/magnet/689c0fe075ab4c7b6c08a6f1e633491d41186860

another magnet on https://rentry.org/sdmodels from the author

* Mixed SFW/NSFW Pony/Furry V2 from AstraliteHeart: https://mega.nz/file/Va0Q0B4L#QAkbI2v0CnPkjMkK9IIJb2RZTegooQ8s6EpSm1S4CDk

* Mega mixing guide (has a different berry mix): https://rentry.org/lftbl
	* Model showcases from lftbl: https://rentry.co/LFTBL-showcase

* Cafe Unofficial Instagram TEST Model Release
	* Trained on ~140k 640x640 Instagram images made up of primarily Japanese accounts (mix of cosplay, model, and personal accounts)
	* Note: While the model can create some realistic (Japanese) Instagram-esque images on its own, for full potential, it is recommended that it be merged with another model (such as berry or anything)
	* Note: Use CLIP 2 and resolutions greater than 640x640

* Artstation Models (by WD dev): https://huggingface.co/hakurei/artstation-diffusion
	* Prebuilt ckpt (not sure if safe): https://huggingface.co/NoCrypt/artstation-diffusion/tree/main

* Nitro Diffusion (Multi-style model trained on three artstyles, archer style, arcane style, and modern disney style): https://huggingface.co/nitrosocke/Nitro-Diffusion

* High quality anime images (eimisanimediffusion): https://huggingface.co/eimiss/EimisAnimeDiffusion_1.0v

*Hrrzg style 768px: https://huggingface.co/TheLastBen/hrrzg-style-768px

* Ghibli Diffusion (tokens: ghibli style): https://huggingface.co/nitrosocke/Ghibli-Diffusion

* Animus's premium models got leaked (not sure if safe): https://rentry.org/animusmixed

**MODEL MIXES**

Raspberry mix download by anon (not sure if safe): https://pixeldrain.com/u/F2mkQEYp
Strawberry Mix (anon, safety caution): https://pixeldrain.com/u/z5vNbVYc

``` python
magnet:?xt=urn:btih:eb085b3e22310a338e6ea00172cb887c10c54cbc&dn=cafe-instagram-unofficial-test-epoch-9-140k-images-fp32.ckpt&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A80&tr=udp%3A%2F%2Fopentor.org%3A2710&tr=udp%3A%2F%2Ftracker.ccc.de%3A80&tr=udp%3A%2F%2Ftracker.blackunicorn.xyz%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969
```

ThisModel:
1. (Weighted Sum 0.05) Anything3 + SD1.5 = Temp1
2. (Add Difference 1.0) Temp1 + F222 + SD1.5 = Temp2
3. (Weighted Sum 0.2) Temp2 + TrinArt2_115000 = ThisModel

Anon's model for vampires(?):
``` python
My steps

Step 1:
>A : Anything-V3.0
>B : trinart2_step115000.ckpt [f1c7e952]
>C : stable-diffusion-v-1-4-original

A from https://huggingface.co/Linaqruf/anything-v3.0/blob/main/Anything-V3.0-pruned.ckpt
B from https://rentry.org/sdmodels#trinart2_step115000ckpt-f1c7e952
C from https://huggingface.co/CompVis/stable-diffusion-v-1-4-original/blob/main/sd-v1-4.ckpt

and I "Add Difference" at 0.45, and name as part1.ckpt

Step 2:
>A : part1.ckpt (What I made in Step 1)
>B: Cafe Unofficial Instagram TEST Model [50b987ae]

B is from https://rentry.org/sdmodels#cafe-unofficial-instagram-test-model-50b987ae

and I "Weighted Sum" at 0.5, and name it TrinArtMix.ckpt
```

* Samdoesbimbos (sandoesart dreambooth dehydrated from original model and hydrated into thepit bimbo dreambooth): https://mega.nz/file/xpECiaAI#_KeDMAvxAnyOkLlo82IP09BHc1KBZoUfT-0jFaDhF3c
	* One recommended merge: f222@0.12 and sd15wd12@0.2
	* Another is F222 SD15 WD12 SxDv0.8 at low ratios (0.1-0.4)

Antler's Mix (didn't check for pickles)
https://mega.nz/file/nZtz0LZL#ExSHp7icsZedxOH_yRUOKAliPGfKRsWiOYHqULZy9Yo

Alternate mix, apparently? (didn't check for pickles)
>((anything_0.95 + sd-1.5_0.05) + f222 - sd-1.5)_0.75 + trinart2_115000_0.25 

RandoMix2 (didn't check for pickles)
magnet:?xt=urn:btih:AB6A6C3F6AA0858030B9B85D28B243A4FF9F5935&dn=RandoMix2.zip&tr=udp%3A%2F%2Ftracker.torrent.eu.org%3A451%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce

RaptorBerry (didn't check for pickles)
magnet:?xt=urn:btih:166c9caf38801ba4e10912b5c91ccaaec585534c&dn=RaptorBerry%20Final%20Mix.ckpt&tr=http%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce&tr=http%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce&tr=udp%3a%2f%2fopentracker.i2p.rocks%3a6969%2fannounce&tr=udp%3a%2f%2fopen.stealth.si%3a80%2fannounce&tr=udp%3a%2f%2ftracker.torrent.eu.org%3a451%2fannounce

NAI+SD+Trinart characters+Trinart+F222 (weighted sum, values less than 0.3): https://mega.nz/file/JblSFKia#n8JNfYWXaMeeQEstB-1A1Ju5u3m9I-u-n3WcmVpz2lo

```
"Ben Dover Mix"©®™ is my mix
if you're interested
follow this guide https://rentry.org/lftbl#berrymix
The mix is done exactly the same way as berrymix
but with anythingv3 instead of nai
f222 instead of f111
and sd v1.5 instead of sd v1.4
```

AloeVera mix: https://mega.nz/file/4bEzxB6Q#j3QwgNxHiYOmT8Y4OgHP9mlzvFbCkEK1DUepMoIBI50

Nutmeg mix:
``` python
0.05 NAI + SD1.5
0.05 mix + f222
0.05 mix + r34
0.05 mix + SF
0.3 Anything + mix
```

Hyper-versatile SD model: https://huggingface.co/BuniRemo/Redshift-WD12-SD14-NAI-FMD_Checkpoint_Merger_-_Hyper-Versatile_Stable_Diffusion_Model
* Made from Redshift Diffusion, Waifu Diffusion 1.2, Stable Diffusion 1.4, Novel AI, Yiffy, and Zack3D_Kinky-v1; capable of rendering humans, furries, landscapes, backgrounds, buildings, Disney style, painterly styles, and more

Hassan (has a few mixes, not sure if the dls are safe): https://rentry.org/sdhassan
* An anon recommended the Hassan1.3 if you do 3DPD
* 1.4 ex: https://imgur.com/a/TUWkJmh

Anonmix: 
>Weighted Sum @ 0.05 to make tempmodel1
>
>A: Anything.V3, B: SD1.5, C: null
>
>Add Difference @ 1.0 to make tempmodel2
>
>A: tempmodel1, B: Zeipher F222, C: SD1.5
>
>Weighted Sum @ 0.25 to make tempmodel3
>
>A: tempmodel2, B: r34_e4, C: Null
>
>Weighted Sum @ 0.20 to make FINAL MODEL
>
>A: tempmodel3, B: NAI

Big collection of berry mixes: https://rentry.org/dbhhk (https://archived.moe/h/thread/6984678/#q6985842)

Super duper mixing cookbook from hdg (most updated): https://rentry.org/hdgrecipes

### **EveryDream Trainer**

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

Download + info + prompt templates: https://github.com/victorchall/EveryDream-trainer
* by anon: allows you to train multiple subjects quickly via labelling file names but it requires a normalization training set of random labelled images in order to preserve model integrity

* Made in Abyss: https://drive.google.com/drive/u/0/folders/1FxFitSdqMmR-fNrULmTpaQwKEefi4UGI
	* https://old.reddit.com/r/StableDiffusion/comments/ylroyp/made_in_abyss_dreambooth_model_i_am_working_on/
	* Download reply: https://old.reddit.com/r/StableDiffusion/comments/ylroyp/made_in_abyss_dreambooth_model_i_am_working_on/iv3w5b3/

### **Dreambooth Models:**

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

Links:
* https://huggingface.co/waifu-research-department
* https://huggingface.co/jinofcoolnes
	* For preview pics/descriptions:
		* https://www.reddit.com/user/jinofcool/
		* https://www.patreon.com/Rahmel
* https://huggingface.co/nitrosocke
* Toolkit anon: https://huggingface.co/demibit/
* https://rentry.org/sdmodels
* Big collection: https://publicprompts.art/
* Big collection of sex models (Might be a large pickle, so be careful): https://rentry.org/kwai
* Collection: https://cyberes.github.io/stable-diffusion-dreambooth-library/
* /vt/ collection: https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ/folder/L2AmBRZC
* Big collection: https://publicprompts.art/
* Chinese collection of Dreambooth models: https://docs.qq.com/sheet/DTVZEd3VqSWhDTXNY?tab=BB08J2
	* Website: https://aimodel.subrecovery.top/
	* Main download: https://www.aliyundrive.com/s/62ha51rH6Uw
		* Apparently, most of the exes from the aliyundrive site are self-extracting, so it might be a miner, virus, etc.

* Nami: https://mega.nz/file/VlQk0IzC#8MEhKER_IjoS8zj8POFDm3ZVLHddNG5woOcGdz4bNLc
* https://huggingface.co/IShallRiseAgain/StudioGhibli/tree/main
* Jinx: https://huggingface.co/jinofcoolnes/sksjinxmerge/tree/main
	* Another: https://drive.google.com/drive/folders/1-Gz7R9X8tSZV7D8oyxqY0zo-BFcXN1_X
	* https://twitter.com/Rahmeljackson/status/1580244475649007616?s=20&t=PNe7aQsh1k1cXsjVyKSeaQ
* Arcane Vi: https://huggingface.co/jinofcoolnes/VImodel/tree/main
* Lucy (Edgerunners): https://huggingface.co/jinofcoolnes/Lucymodel/tree/main
	* https://www.patreon.com/posts/73414085
	* https://twitter.com/Rahmeljackson/status/1582019346867441666?s=20&t=3K2kJ2zQna4a24-AoVJWpw
* Gundam (full ema, non pruned): https://huggingface.co/Gazoche/stable-diffusion-gundam
* Starsector Portraits: https://huggingface.co/Severian-Void/Starsector-Portraits
* Evangelion style: https://huggingface.co/crumb/eva-fusion-v2
* Robo Diffusion: https://huggingface.co/nousr/robo-diffusion/tree/main/models
* Arcane Diffusion: https://huggingface.co/nitrosocke/Arcane-Diffusion
* Archer: https://huggingface.co/nitrosocke/archer-diffusion
* Wikihow style: https://huggingface.co/jvkape/WikiHowSDModel
	* 60 Images. 2500 Steps. Embedding Aesthetics + 40 Image Embedding options
	* Their patreon: https://www.patreon.com/user?u=81570187
* Lain girl: https://mega.nz/file/VK0U0ALD#YDfGgOu8rquuR5FbFxmzKD5hzxO1iF0YQafN0ipw-Ck
* Wikiart: https://huggingface.co/valhalla/sd-wikiart-v2/tree/main/unet
	* diffusion_pytorch_model.bin, just rename to whatever.ckpt
* Megaman zero: https://huggingface.co/jinofcoolnes/Zeromodel/tree/main
	* https://www.patreon.com/posts/zero-model-73763667?utm_medium=clipboard_copy&utm_source=copyLink&utm_campaign=postshare_creator
	* https://twitter.com/Rahmeljackson/status/1584947512573448197?s=20&t=wVbTLod2aV_uaQdqejNFfg
* Cyberware: https://huggingface.co/Eppinette/Cyberware/tree/main
* taffy (keyword: champi): https://drive.google.com/file/d/1ZKBf63fV1Zm5_-a0bZzYsvwhnO16N6j6/view?usp=sharing
	* https://arca.live/b/hypernetworks/60931350?category=%EA%B3%B5%EC%9C%A0&p=2
* Disney (3d?): https://huggingface.co/nitrosocke/modern-disney-diffusion/
* El Risitas (KEK guy): https://huggingface.co/Fictiverse/ElRisitas
* Cyberpunk Anime Diffusion: https://huggingface.co/DGSpitzer/Cyberpunk-Anime-Diffusion
* Kurzgesagt (called with "kurzgesagt! style"): https://drive.google.com/file/d/1-LRNSU-msR7W1HgjWf8g1UhgD_NfQjJ4/view?usp=sharing
	* SHA-256: d47168677d75045ae1a3efb8ba911f87cfcde4fba38d5c601ef9e008ccc6086a
* Robodiffusion (good outputs for "meh" prompting): https://huggingface.co/nousr/robo-diffusion
* 2D Illustration style: https://huggingface.co/ogkalu/hollie-mengert-artstyle
	* https://www.reddit.com/r/StableDiffusion/comments/yaquby/2d_illustration_styles_are_scarce_on_stable/
* Rebecca (edgerunners, by booru anon, info is in link): https://huggingface.co/demibit/rebecca
* Kiwi (by booru anon): https://huggingface.co/demibit/kiwi
* Ranni (Elden Ring): https://huggingface.co/bitspirit3/SD-Ranni-dreambooth-finetune
* Cloud: https://huggingface.co/jinofcoolnes/cloud/tree/main
	* https://twitter.com/Rahmeljackson/status/1586037466548551681?s=20&t=F9mU9uOFEDGKYTVl00DzUg
	* https://www.patreon.com/posts/73899634?pr=true
* Comics: https://huggingface.co/ogkalu/Comic-Diffusion
* Modern Disney style (modi, mo-di): https://huggingface.co/nitrosocke/mo-di-diffusion/
* Silco: https://huggingface.co/jinofcoolnes/silcomodel/tree/main
	* https://www.patreon.com/posts/silco-model-73477832?utm_medium=clipboard_copy&utm_source=copyLink&utm_campaign=postshare_creator
	* https://twitter.com/Rahmeljackson/status/1582515393381662720?s=20&t=K1tuYmsK4Xo9RBLcqooD-A
* Lara: https://huggingface.co/jinofcoolnes/Oglaramodel/tree/main
	* https://twitter.com/Rahmeljackson/status/1583297706457329664?s=20&t=91YzDUX-fE1dOXehK5Oe-g
	* https://www.patreon.com/posts/73578982
* theofficialpit bimbo (26 pics for 2600 steps, Use "thepit bimbo" in prompt for more effect): https://mega.nz/file/wSdigRxJ#WrF8cw85SDebO8EK35gIjYIl7HYAz6WqOxcA-pWJ_X8
* DCAU (Batman_the_animated_series): https://huggingface.co/IShallRiseAgain/DCAU/blob/main/DCAUV1.ckpt
	* https://www.reddit.com/r/StableDiffusion/comments/yf2qz0/initial_version_of_dcau_model_im_making/
	* hand captioning 782 screencap, 44,000 steps, training set for the regularization images
* NSFW: https://megaupload.nz/N7m7S4E7yf/Magnum_Opus_alpha_22500_steps_mini_version_ckpt
	* Dataset: https://megaupload.nz/wep7S7E0y3/magnum_opus_training_data_set_zip
* Hardcore: https://pixeldrain.com/u/Stk98vyH
	* Trained on 3498 images and around 250K steps
		* porn, sex acts of all sorts: anal sex, anilingus, ass, ass fingering, ball sucking, blowjob, cumshot, cunnilingus, dick, dildo, double penetration, exposed pussy, female masturbation, fingering, full nelson, handjob, large ass, large tits, lesbian kissing, massive ass, massive tits, o-face, sixty-nine, spread pussy, tentacle sex (try also oral/anal tentacle sex and tentacle dp), tit fucking, tit sucking, underboob, vaginal sex, long tongue, tits
	* Example grid from training (single shot batch): https://cdn.discordapp.com/attachments/1010982959525929010/1035236689850941440/samples_gs-995960_e-000046_b000000.png
* disney 2d (classic) animation style: https://huggingface.co/nitrosocke/classic-anim-diffusion
	* https://www.reddit.com/r/StableDiffusion/comments/yhikn3/new_dreambooth_model_classic_animation_styles/
* Kim Jung Gi: https://drive.google.com/drive/folders/1uL-oUUhuHL-g97ydqpDpHRC1m3HVcqBt
	* https://twitter.com/bg_5you/status/1578146498768175105
* Pyro's Blowjob Model: https://rentry.org/pyros-sd-model
	* https://anonfiles.com/6123m6F6y9/pyros-bj-v1-0_ckpt
	* https://mega.nz/file/lLtjCLwb#KgXPDzbTotcb0_quzzBMm6DaDCuSFIaF8CXxw1WsEs8
	* Examples: https://www.reddit.com/gallery/yhuymu
	* Examples: https://old.reddit.com/r/sdnsfw/comments/yhuymu/ill_never_need_any_porn_site_ever_again/
* Pixel Art Sprite Sheet (stardew valley): https://huggingface.co/Onodofthenorth/SD_PixelArt_SpriteSheet_Generator
	* 4 different angles
	* Examples + Reddit post: https://www.reddit.com/r/StableDiffusion/comments/yj1kbi/ive_trained_a_new_model_to_output_pixel_art/
* WLOP: https://huggingface.co/SirVeggie/wlop
* corporate memphis A.I model (infographics): https://huggingface.co/jinofcoolnes/corporate_memphis/tree/main
	* https://twitter.com/Rahmeljackson/status/1588435864769925121?s=20&t=j2jCYpS7HW8WjgK15Hg7BA
	* https://www.patreon.com/posts/74213085?pr=true
* Tron: https://huggingface.co/dallinmackay/Tron-Legacy-diffusion
	* https://www.reddit.com/r/StableDiffusion/comments/yi3nty/my_tronstyle_dreambooth_model_available_to/
* Superhero: https://huggingface.co/ogkalu/Superhero-Diffusion
	* https://www.reddit.com/r/StableDiffusion/comments/yl3ug8/superhero_diffusion_new_dreambooth_model/
* Chicken (trained on images from r/chickens): https://huggingface.co/fake4325634/chkn
	* https://www.reddit.com/r/StableDiffusion/comments/ylmcov/chicken_diffusion_dreambooth_model/
* 1.5 based model created from the Spede images (not too sure if this is Dreambooth): https://mega.nz/file/mdcVARhL#FUq5TL2xp7FuzzgMS4B20sOYYnPZsyPMw93sPMHeQ78
* Redshift Diffusion (High quality 3D renders): https://huggingface.co/nitrosocke/redshift-diffusion
	* https://www.reddit.com/r/StableDiffusion/comments/ynz33f/dreambooth_model_release_redshift_diffusion_high/
* Cats: https://huggingface.co/dallinmackay/Cats-Musical-diffusion
* Van Gogh: https://huggingface.co/dallinmackay/Van-Gogh-diffusion
	* https://www.reddit.com/r/StableDiffusion/comments/ymtud0/my_van_gogh_style_loving_vincent_dreambooth_model/
* Rouge the Bat (44 SFW images of Rouge the Bat for 1600 or 2400 steps, keyword: 'rkugasebz'): https://huggingface.co/ChanseyIsForeverAI/Rouge-the-bat-dreambooth
	* Examples: https://i.imgur.com/X12W59D.png
				https://i.imgur.com/Lpul7Pf.png
				https://i.imgur.com/r0bc6i8.png
				https://i.imgur.com/gkEW0w0.png
				https://i.imgur.com/Zj8PtZC.png
* Made in Abyss (MIA 1-6 V2): https://drive.google.com/drive/folders/1FxFitSdqMmR-fNrULmTpaQwKEefi4UGI?usp=sharing
	* Uploader note: I was hesitant to share this one because I have been having a lot of problems with the new captioning format. With the new format essentially we have much better multiple character flexibility and outfits. You can generate 2 characters in completely separate outfits with a high percentage of no blending. However, my new captioning was causing everything to train significantly slower, so some side characters don't look as good as they did in the original 1-6 model. There is also a strict captioning format I used, so I also uploaded a prompt readme to the folder which contains all the information needed to best use this model 
* Gyokai/onono imoko/@_himehajime: https://mega.nz/folder/HzYT1T7L#H9TWVVYowA0cX8Eh6x_H3g
	* use term 'gyokai' under class '1girl' e.g 'illustration of gyokai 1girl' + optionally 'multicolored hair, halftone, polka dot'
	* Img: https://i.4cdn.org/h/1667881224238388.jpg
* Amano: https://huggingface.co/RayHell/Amano-Diffusion
* Midjourney: https://huggingface.co/prompthero/midjourney-v4-diffusion
* Borderlands (training info in reddit): 
https://www.reddit.com/r/StableDiffusion/comments/yong77/borderlands_model_works_for/
	* https://publicprompts.art/borderlands-dreambooth-model/
* Pixel art model: https://publicprompts.art/all-in-one-pixel-art-dreambooth-model/
	* https://www.reddit.com/r/stablediffusion/comments/yqtm3k
* Satania (has two iterations of the model, 500 step has more flexibility but 1k can look nicer if you want base Satania, link will expire soon): https://i.mmaker.moe/sd/mmkr-greatmosu-satania.7z
* Pokemon: https://huggingface.co/justinpinkney/pokemon-stable-diffusion
* final fantasy tactics: https://huggingface.co/jinofcoolnes/FinalfantasyTactics/tree/main
	* https://twitter.com/Rahmeljackson/status/1590401243641368576
	* https://www.patreon.com/posts/final-fantasy-74440534
* smthdssmth: https://huggingface.co/Marre-Barre/smthdssmth
* A model I found on /vt/, not too sure what it is of: https://drive.google.com/file/d/1iR9wVI1wm4M6ZTJgJR_i3TZPAQBDB0Bk/view?usp=share_link
* Anmi: https://drive.google.com/drive/folders/1YFzJKQNVhCRgu0EnkVYgSQ5v63i_LBa4
* Samdoesart (merged model using the original, chewtoy's model, and Chris(orginalcode)'s model): https://huggingface.co/jinofcoolnes/sammod/tree/main
	* Uploader note: all training credit goes to the 3 model maker this merge made from, thank you to them! 
* CopeSeetheMald (samdoesart) (Both were trained with the same dataset. 204 images @ 20.4k steps, 1e-6 learning rate. It's just the base model that differs):
	* berry-based model: https://mega.nz/folder/1a1xkQQK#4atlB1cJqI35InXxlxyA7A
	* blossom-based model: https://mega.nz/folder/ZG0UnRBJ#jykESWBUCr7hjOoNVTXwLw
	* Comparison: https://i.4cdn.org/g/1668068841516679.png
* CopeSeetheMald v2 (10k CHINAI (anything.ckpt)): https://mega.nz/file/xT9jVToK#Sj1S76kl-PC-zCRwJ2FWen6DS0NHY0IXFFAkXhm03eo
	* Ref: https://i.4cdn.org/g/1668113783214478.png
* SOVLFUL original Xbox/PS2/2006 PC era (jaggy92500): https://mega.nz/file/0SER2YpC#_MRc6p_sG9cSWqihpt33jpOWyMR8bCZrUaVkh4z5kGE
	* Sample: https://i.4cdn.org/g/1668129506591557s.jpg
	* Discord: https://discord.com/channels/1038249716149928046/1038283286046322819/1040413218000097280 (from https://discord.gg/Xz8CBFCT)
* Midna (wip): https://mega.nz/folder/E18R2SwC#jHBFsK7zCSuVemOsU4UZ9Q
	* dreambooth midna training config: https://pastebin.com/5EWnMJEz
	* Tagging tool in "Datasets:" section 
* Pepe (word: pepestyle): https://mega.nz/file/NbUShTDR#bZpcYFlv--VqpqUfgDnU95duQlr3wFhRZ4m26WK-Qts 
* Pepe continued: https://huggingface.co/SpiteAnon/Pepestyle
	* https://mega.nz/file/ECchBQRI#u_ySb56NVvANZGY0y6NsS9-ZYSaF1tQCh78OoBuw3IA
* Gigachad: https://huggingface.co/SpiteAnon/gigachad-diffusion
	* https://mega.nz/file/8ecQGJRD#dHe2Ar9e1AN9-wcNrP1qpBjHqk9UtlgO2UtiXlZJHpQ
* y2k (by JF#8026): https://mega.nz/file/hT0mgTqR#d8g133APl30UtDwsNmzV73_ZESi_kTa5pmQgJoxomn0
	* ykgl.ckpt. It does cgi girls from the y2k era. Trained for 40k steps.
	* You call on them with (ykgl cgi_girl), or (ykgl cgi_girls), or just (ykgl girl), and then maybe with , cgi_artstyle.
* dbmai (model by 火柴人之父L): https://rentry.org/3en6a
	* https://drive.google.com/drive/folders/1MUtM5MTXM35fid5TE3tUSKXAqPP7oysz
	* https://tieba.baidu.com/p/8136937175
* Vulcan (from Star Trek): https://huggingface.co/mitchtech/vulcan-diffusion
* DND: https://huggingface.co/0xJustin/Dungeons-and-Diffusion
* Complex Lineart: https://huggingface.co/Conflictx/Complex-Lineart
* More Abmayo (has model and imgs): https://mega.nz/folder/l5NxwTKa#9fA_tn_OZxWm3kHjdA9TPg
* Yuzuki Yukari: https://mega.nz/folder/8hNEiSSC#fYPUNzazZQ04dSizcjmhcg
* Samdoesartv2: https://huggingface.co/kijaw/samdoesarts_v2
	* Ex: https://imgur.com/a/5StuU4G
* Nadanainone (created and trained on their own art, 1076 images (including flipped copies), 10k steps, 1e-6 learning rate): https://huggingface.co/nadanainone/istolemyownart
* Pop n Music: https://huggingface.co/nadanainone/popnm
* Heaven burns red artstyle: https://gofile.io/d/3q5WO3
	* use hbrs as a prompt
	* highly recommand to use 1girl and portrait as those were trained on those the most
* Samus enjoying tentacles + Dataset: https://mega.nz/folder/ls10yJBK#WsnlUfHkcle4FEc_jXS6eA
* CModel: https://huggingface.co/jinofcoolnes/cmodel/tree/main
	* https://www.patreon.com/posts/cmodel-74660500
	* https://twitter.com/Rahmeljackson/status/1592400206733115393
	* Reported to work with NAI hypernets well
* heavy paint style from the same author of dbmai: https://drive.google.com/drive/folders/1ssyBg5Fw8O80_T6nvTrzcnluXEx0YD0I
	* use lastmodel 
	* source: https://tieba.baidu.com/p/8147386385
* Kurzgesagt (another?): https://huggingface.co/questcoast/SD-Kurzgesagt-style-finetune
* Rei and Liduke (not sure if safe): https://rentry.org/eeayv
	* Rei: https://pixeldrain.com/u/Sruc4DDk
	* Liduke: https://pixeldrain.com/u/4T3oBcRy
* Mikasa + Dataset: https://mega.nz/folder/x9FRkAzC#zPs19Nhx7ASZQwauj0PiyA
	* Note: You have to get a bit creative with the prompt since I didn't clean up the tags, you often need to combine a ton of redundant tags to get the effect you want. Example images included along with a list of all tags for experimentation. If you merge the checkpoint with something else the visuals improve dramatically. The artist tags in the list will guide it towards a particular aesthetic.
* Ranma (replicates late '80s early '90s anime, specifically the Ranma 1/2 anime): https://huggingface.co/tashachan28/ranma_diffusion
* VRass (based on Anytthing V3, trained on free VRoid clothing, good for img2img, supports high denoising (0.6-0.8), token: vrass)
* Hapu: https://mega.nz/file/xWdTAbzI#TVaq9Fgds2V43IWai09NdoLDSJHx6FMy_14UTWL1HEQ
* AISee (made from 3k artworks from some website, more info in the link): https://huggingface.co/grinman/AIsee
* BTD6 monkeys (not sure if dreambooth): https://huggingface.co/Junglerally/Stable-BTD6
* Kobo (kbknr): https://huggingface.co/cntfcknwrtvwls/kbknr
	* Alternate download: https://mega.nz/folder/jUQ20ZwC#15bhNyCG9SjgQYe5X_E5JA

### **Embeddings**
!!! info If an embedding is >80mb, I mislabeled it and it's a hypernetwork

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

You can check .pts here for their training info using a text editor

* Text Tutorial: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Textual-Inversion
	* Make sure to use pictures of your subject in varied areas, it gives more for the AI to work with
* Tutorial 2: https://rentry.org/textard
* Another tutorial: https://imgur.com/a/kXOZeHj
	* https://i.imgur.com/yv3TrrC.jpeg
* Test embeddings: https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer
* Collection: https://huggingface.co/sd-concepts-library
* Collection 2: https://mega.nz/folder/fVhXRLCK#4vRO9xVuME0FGg3N56joMA
* Collection 3: https://cyberes.github.io/stable-diffusion-textual-inversion-models/
* **Korean megacollection:**
	* https://arca.live/b/hypernetworks?category=%EA%B3%B5%EC%9C%A0
		* Link scrape: https://pastebin.com/p0F4k98y
	* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948
	* Original: https://arca.live/b/hypernetworks/60930993
	* **Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw**
* Large Vtuber collection dump (not sure if pickled, even linker anon said to be careful, but a big list anyway): https://rentry.org/EmbedList
* Waifu Diffusion collection: https://gitlab.com/cattoroboto/waifu-diffusion-embeds
* Collection of curated embeds that aren't random junk/test ones from HF's Stable Diffusion Concept library (Updated to Nov 10): https://mega.nz/file/58tRlZDQ#Xbs7kYRC-bot1FIDdkJcz_chJpVrdghrGYMO9POPq9U
	* contains two folders, one for the top liked list and one for the entire library (excluding top liked)

Found on 4chan:
* Embeddings + Artists: https://rentry.org/anime_and_titties (https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A)
* Random embedding I found: https://ufile.io/c3s5xrel
* Embeddings: https://rentry.org/embeddings
* Anon's collection of embeddings: https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A
* Collection: https://gitgud.io/ZeroMun/stable-diffusion-tis/-/tree/master/embedding
* Collection: https://gitgud.io/sn33d/stable-diffusion-embeddings
* Collection from anon's "friend" (might be malicious): https://files.catbox.moe/ilej0r.7z
* Collection from anon: https://files.catbox.moe/22rncc.7z
* Collection: https://gitlab.com/rakurettocorp/stable-diffusion-embeddings/-/tree/main/
* Collection: https://gitlab.com/mwlp/sd 
* Senri Gan: https://files.catbox.moe/8sqmeh.rar
* Collection: https://gitgud.io/viper1/stable-diffusion-embeddings
* Repo for some: https://git.evulid.cc/wasted-raincoat/Textual-Inversion-Embeds/src/branch/master/simonstalenhag
* automatic's secret embedding list: https://gitlab.com/16777216c/stable-diffusion-embeddings
* Collection of /vt/ embeds in 0-Embeds folder: https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ

* Henreader embedding, all 311 imgs on gelbooru, trained on NAI: https://files.catbox.moe/gr3hu7.pt
* Henreader (a different one, made for SD 1.4 or WD 1.2 with a small dataset): https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A/folder/Go9CRRoC
* Kantoku (NAI, 12 vectors, WD 1.3): https://files.catbox.moe/j4acm4.pt
* Asanagi (NAI): https://files.catbox.moe/xks8j7.pt
	* Asanagi trained on 135 images augmented to 502 for 150296 steps on NAI Anime Full Pruned with 16 vectors per token with init word as voluptuous
	* training imgs: https://litter.catbox.moe/2flguc.7z
* DEAD LINK Asanagi (another one): https://litter.catbox.moe/g9nbpx.pt
* Imp midna (NAI, 80k steps): mega.nz/folder/QV9lERIY#Z9FXQIbtXXFX5SjGf1Ba1Q
* imp midna 2 (NAI_80K): mega.nz/file/1UkgWRrD#2-DMrwM0Ph3Ebg-M8Ceoam_YUWhlQWsyo1rcBtuKTcU
* inverted nipples: https://anonfiles.com/300areCby8/invertedNipples-13000_zip (reupload)
	* Dead link: https://litter.catbox.moe/wh0tkl.pt
* Takeda Hiromitsu Embedding 130k steps: https://litter.catbox.moe/a2cpai.pt
* Takeda embedding at 120000 steps: https://filebin.net/caggim3ldjvu56vn
* Nenechi (momosuzu nene) embedding: https://mega.nz/folder/E0lmSCrb#Eaf3wr4ZdhI2oettRW4jtQ
* Touhou Fumo embedding (57 epochs): https://birchlabs.co.uk/share/textual-inversion/fumo.cpu.pt
	* https://twitter.com/Birchlabs/status/1579937213617680385
* Abigail from Great Pretender (24k steps): https://workupload.com/file/z6dQQC8hWzr 
* Naoki Ikushima (40k steps): https://files.catbox.moe/u88qu5.pt
* Abmayo: https://files.catbox.moe/rzep6d.pt
* Gigachad: https://easyupload.io/nlha2m
* Kusada Souta (95k steps): https://files.catbox.moe/k78y65.pt
* Yohan1754: https://files.catbox.moe/3vkg2o.pt
* Niro: https://take-me-to.space/WKRY9IE.pt
* Kaneko Kazuma (Kazuma Kaneko): https://litter.catbox.moe/6glsh1.pt
* Senran Kagura (850 CGs, deepdanbooru tags, 0.005 learning rate, 768x768, 3000 iterations): https://files.catbox.moe/jwiy8u.zip
* Abmayo (miku) (14.7k): https://www.mediafire.com/folder/trxo3wot10j41/abmono
	* https://www.mediafire.com/file/id2uh4gkzvavsbc/abmono-14700.pt/file
	* https://mega.nz/file/u11GTAKK#QKG2uIYd9ccDggC_2YzprsqWvqTVwvYgvbYQ19ouq9M
* Aroma Sensei (86k, "aroma"): https://files.catbox.moe/wlylr6.pt
* Zun (75:25 weighted sum NAI full:WD): https://www.fluffyboys.moe/sd/zunstyle.pt
* Kurisu Mario (20k): https://files.catbox.moe/r7puqx.pt
	* creator anon: "I suggest using him for the first 40% of steps so that the AI draws the body in his style, but it's up to you. Also, put speech_bubble in the negative prompt, since the training data had them"
* ATDAN (33k): https://files.catbox.moe/8qoag3.pt
	* Mirror: https://litter.catbox.moe/6valfk.pt
* Valorant (25k): https://files.catbox.moe/n7i9lq.pt
	* Mirror: https://files.catbox.moe/n7i9lq.pt
* Takifumi (40k, 153 imgs, NAI): https://freeufopictures.com/ai/embeddings/takafumi/
	* for competition swimsuit lovers
* 40hara (228 imgs, 70k, 421 after processing): https://freeufopictures.com/ai/embeddings/40hara/
* Tsurai (160k, NAI): https://mega.nz/file/bBYjjRoY#88o-WcBXOidEwp-QperGzEr1qb8J2UFLHbAAY7bkg4I
* jtveemo (150k): https://a.pomf.cat/kqeogh.pt
	* Creator anon: "I didn't crop out any of the @jtveemo stuff so put twitter username in the negatives."
	* 150k steps, 0.005 LR, art from exhentai collection and processed with mirror and autocrop, deepdanbooru
* Nahida (Genshin Impact): https://files.catbox.moe/nwqx5b.zip
* Arcane (SD 1.4): https://files.catbox.moe/z49k24.pt
	* People say this triggered the pickle warning, so it might be pickled.
* Gothica: https://litter.catbox.moe/yzp91q.pt
* Mordred: https://a.pomf.cat/ytyrvk.pt
* 100k steps tenako (mugu77): https://www.mediafire.com/file/1afk5fm4f33uqoa/tenako-mugu77-100000.pt/file
* erere-26k (fuckass(?)): https://litter.catbox.moe/cxmll4.pt
* Great Mosu (44k): https://files.catbox.moe/6hca0u.pt
* no idea what this embedding is, apparently it's an artist?: https://files.catbox.moe/2733ce.pt
* Dohna Dohna, Rance remakes (305 images (all VN-style full-body standing character CGs). 12000 steps): https://files.catbox.moe/gv9col.pt
	* trained only on dohna dohna's VN sprites
	* Onono imoko
* Raita: https://files.catbox.moe/mhrvmk.pt
* Senri Gan: https://files.catbox.moe/8sqmeh.rar
	* 2 hypernetworks and 5 TI
	* Anon: "For the best results I think using hyper + TI is the way. I'm using TI-6000 and Hyper-8000. It was trained on CLIP 1 Vae off with those rates 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000."
* om_(n2007): https://files.catbox.moe/gntkmf.zip
	* https://files.catbox.moe/x0aueo.pt
* Kenkou Cross: https://mega.nz/folder/ZYAx3ITR#pxjhWOEw0IF-hZjNA8SWoQ
* Baffu (~47500 steps): https://files.catbox.moe/l8hrip.pt
	* Biased toward brown-haired OC girl (Hitoyo)
* Danganronpa: https://files.catbox.moe/3qh6jb.pt
* Hifumi Takimoto: https://files.catbox.moe/wiucep.png 
	* 18500 steps, prompt tag is takimoto_hifumi. Trained on NAI + Trinart2 80/20, but works fine using just NAI
* Power (WIP): https://files.catbox.moe/bzdnzw.7z
* shiki_(psychedelic_g2): https://files.catbox.moe/smeilx.rar
	* https://files.catbox.moe/btxd4r.rar
* Akari: https://files.catbox.moe/b7jdng.pt
* Embeddings using the old version of TI
	* jtveemo: https://www.mediafire.com/file/re9q1l1xwgriscm/jtveemo-style.bin/file
	* kenshin187: https://www.mediafire.com/file/fap4yuiyvqt7dkl/kenshin187.bin/file
* Takeda Hiromitsu reupload: https://www.mediafire.com/file/ljemvmmtz0dqy0y/takeda_hiromitsu.pt/file
* Takeda Hiromitsu (another reupload): https://a.pomf.cat/eabxqt.pt
* Pochi: https://files.catbox.moe/7vegvg.rar
	* Author's notes: Smut version was trained on a lot of doujins and it looks more like her old style from the start of smut version of Ane doujin (compare to chapter 1 and you can see that it worked). 200k version is looking a bit more like her recent style but I can see it isn't going to work the way I hoped. 
	* By accident I started with 70 pics where half of them were doujins to give reference for smut. Complete data is 200 with again those same 35 doujins for smut. I realized that I used half smut instead of full set so I went back to around 40k steps and then gave it complete 200 picture set hoping it would course correct since non smut is more recent art style. Now it looks like it didn't course correct and will never do that. On the other hand recent iterations are less horny.
* Power (Chainsaw Man): https://files.catbox.moe/c1rf8w.pt
* ooyari:
	* 70k (last training): https://litter.catbox.moe/gndvee.pt
	* 20k (last stable loss trend): https://litter.catbox.moe/i7nh3x.pt
	* 60k (lowest loss rate state in trending graph): https://litter.catbox.moe/8wot9a.pt
* Kunaboto (195 images. 16 vectors per token, default learning rate of 0.005): https://files.catbox.moe/uk964z.pt
* Erika (Shadowverse): https://files.catbox.moe/y9cgr0.pt
* Luna (Shadowverse): https://files.catbox.moe/zwq5jz.pt
* Fujisaka Lyric: https://files.catbox.moe/8j6ith.pt
* Hitoyo (maybe WIP?): https://files.catbox.moe/srg90p.pt
* Hitoyo (58k): https://files.catbox.moe/btjsfg.pt
* kunaboto v2 (Same dataset, just a different training rate of 0.005:25000,0.0005:75000,0.00005:-1, 70k): https://files.catbox.moe/v9j3bz.pt
* Hitoyo (another, final vers?) (100k steps, bonnie-esque): https://files.catbox.moe/l9j1f4.pt
* Fatamoru: https://litter.catbox.moe/pn9xep.pt
	* Dead link: https://litter.catbox.moe/xd2ht9.pt
* Zip of Fatamoru, Morgana, and Kaneko Kazuma: https://litter.catbox.moe/9bf77l.zip
* Tekuho (NAI model, Clip Skip 2, VAE unloaded, Learning rate 0.002:2000, 0.0005:5000, 0.0001:9000): https://mega.nz/folder/VB5XyByY#HLvKyIJ6U5nMXx6i3M__VQ
	* manually cropped about 150 images, making sure that all of them have a full body shot, a shot from torso and up, and if applicable a closeup on the face
	* Images not from Danbooru
	* Best results around 4000 steps
* Reine: https://litter.catbox.moe/saav38.zip
* Embed of a girl anon liked (2500 steps, keyword "jma"): https://files.catbox.moe/1qlhjf.pt 
* Carpet Crawler: https://anonfiles.com/i3a2o0E5y0/carpetcrawlerv2-12500_pt
	* Embedding trained on nai-final-pruned at 8 vectors up to 20k steps. Turned into ugly overtrained garbage over 125000 steps so this is the one I'm releasing. Not good for much other than eldritch abominations.
	* https://www.deviantart.com/carpet-crawler/gallery
	* recommend using it in combination with other horror artist embeddings for best results.
* nora higuma (Fuckass, 0.0038, 24k, 1000+ dataset, might be pickle): https://litter.catbox.moe/tkj61z.pt
	* dead link: https://litter.catbox.moe/25n10h.pt
* mdf an (Bitchass train: 0.0038, steps: 48k, loss rate trend: 0.095, dataset: 500+, issue: nsfw majority, will darken sfw images): https://litter.catbox.moe/lxsnyi.pt
	* dead link: https://litter.catbox.moe/4liook.p
* subachi (shitass, train: 0.0038, steps: 48k, loss rate trend: 0.118, dataset: 500+, issue: due to artist's style, it's on sigma male mode; *respecting woman is not an option with this embedding*): https://litter.catbox.moe/6nykny.pt
	* dead link: https://litter.catbox.moe/idskrg.pt
* irys: https://files.catbox.moe/1iwmv1.pt
* DEAD LINK Omaru-polka: https://litter.catbox.moe/qfchu1.pt
* Embed for "veemo" (?), used to make this picture (https://s1.alice.al/vt/image/1665/54/1665544747543.png): https://files.catbox.moe/18bgla.pt
* Lui: https://files.catbox.moe/m54t0p.pt
* Reine:
	* 39,5k steps, pretty high vectors per token: https://files.catbox.moe/s2s5qg.pt
	* smaller clip skip and less steps, trained it to 13k: https://files.catbox.moe/nq126i.pt
* Big reine collection: https://files.catbox.moe/xe139m.zip
* Ilulu (64k steps with a learning rate of 0.001): https://files.catbox.moe/8acmvo.pt
* random embed from furry thread (6500 steps, 10 vectors, 1 placeholder_string, init_word "girl" these four images used): https://files.catbox.moe/4qiy0k.pt
* Cookie (from furry thread, apprently good with inpainting): https://files.catbox.moe/9iq7hh.pt
	* https://mega.nz/file/IABX1QKS#8vsSqlUm-o6QNB2gjSQeJzED1dtKOZVWdE8-By0INlI
* Cutie (cyclops, from furry thread, 8k steps): https://files.catbox.moe/aqs3x3.pt
	* 4.5k: https://files.catbox.moe/mcwxag.pt
* Felino's artstyle (from furry thread, 7 images): https://files.catbox.moe/vp21w4.pt
* Yakov (from mlp thread): https://i.4cdn.org/mlp/1666224881260593.png
* Rebecca (by booru anon, info is in link): https://huggingface.co/demibit/rebecca
* eastern artists combinination: https://mega.nz/file/SlQVmRxR#nLBxMj7_Zstv4XqfuEcF-pgza3T1NPlejCm1KGBbw70
* Elana (Shadowverse): https://files.catbox.moe/vbpo7m.pt
	* Info by anon: I just grab all the good images I can find, tag with BLIP and Deepdanbooru in the preprocessing, and pick a number of vectors based on how many images I have (16 here since not a lot). Other than that, I trained 6500 steps at 1 batch size under the schedule:

		0.02:200, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.00005
* Lina: https://files.catbox.moe/jnfo98.pt
* Power (60k): https://files.catbox.moe/72dfvc.pt
* Takeda, Mogudan Fourchanbal (?, from KR site): https://files.catbox.moe/430rus.pt
* Mikan (30 tokens, 36 images (before flipping/splitting), 5700steps, 5e-02:2000, 5e-03:4000): https://files.catbox.moe/xwdohx.pt
	* creator: I've been getting best results with these tags: (orange hair and (hair tubes:1.2), (dog ears and dog tail and (huge ahoge:1.2):1.2)), green eyes
	* apparently it's not very effective. a hypernetwork is WIP
* Fuurin Rei (6000, 5.5k most): https://files.catbox.moe/s19ub3.7z
* Mutsuki (Blue Archive) embedding (10k step,150 image, no clip skip [set the "stop at last layers of clip model" option at 1 to get good results], 0.02:300, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.0005, vae disabled by renaming): https://files.catbox.moe/6yklfl.pt
* Reine: https://files.catbox.moe/tv1zf4.pt
* as109 (trained with 1000+ dataset, 0.003 learning rate, 0.12 loss rate trend, 25k step snapshot): https://litter.catbox.moe/5iwbi5.pt
* sasamori tomoe (0.92 loss trend, 60k+ steps, 0.003 learning rate. 500+ dataset, pruned pre 2015 images. biased to doujin, weak to certain positions (mostly side)): https://litter.catbox.moe/mybrvu.pt
* egami(500+ dataset, 0.03 learning rate, 0.13 loss trend, 40k steps): https://litter.catbox.moe/dpqp1k.pt
* pink doragon (20k+ steps, 0.0031 learning rate, 0.113 loss trend, 800+ dataset): https://litter.catbox.moe/mml9b9.pt
	* kind of failure: fancy recent artworks are ignored due to dataset bias - will train with 2018+ data.
	* leaning to BIG ASS and BIG TIDDIES.
* Kiwi (by booru anon): https://huggingface.co/demibit/kiwi
* Labiata (8 vectors/token): https://files.catbox.moe/0kri2d.pt
* Akari (another, one I missed): https://files.catbox.moe/dghjhh.pt
* Arona from Blue Archive (I'm pretty sure): https://files.catbox.moe/4cp6rl.pt
* Emma (arcane, 50 vector embedding trained on ~250 pics for ~13500 steps): https://files.catbox.moe/2cd7s3.pt
* blade4649 embedding (10k steps, 352 images,16 vectors,learning rate at 0.005): https://files.catbox.moe/5evrpn.pt
* fechtbuch of Mair: https://files.catbox.moe/vcisig.pt
* Longsword (mainly for img2img): https://files.catbox.moe/r442ma.pt 
* Le Malin (listless Lapin skin, 10k steps with 712 inputs): https://files.catbox.moe/3rhbvq.pt
* minakata hizuru (summertime girl): https://files.catbox.moe/9igh8t.pt
* Roon (Azur Lane) (NAI model, 10k steps but with 83 different inputs): https://files.catbox.moe/9b77mp.pt
* arcane-32500: https://files.catbox.moe/nxe9qr.pt
* mashu003 (https://mashu003.tumblr.com/) (all danbooru images used as dataset): https://files.catbox.moe/kk7v9w.pt
* Takimoto Hifumi (18500 steps, prompt tag is takimoto_hifumi. Trained on NAI + Trinart2 80/20, but works fine using just NAI): https://files.catbox.moe/wiucep.png
* momosuzu nene: https://mega.nz/folder/s8UXSJoZ#2Beh1O4aroLaRbjx2YuAPg
* Harada Takehito (disgaea artist) (78k steps with 150 images): https://files.catbox.moe/e2iatm.pt
* Mda (1700 images and trained for 20k): https://files.catbox.moe/tz37dj.pt
* Polka (NAI, 16 vectors, 5500 steps): https://files.catbox.moe/pmzyhi.png
* Enna: https://files.catbox.moe/7edtp0.pt
* Ghislaine Dedoldia ("dark-skinned female" init word, 12 vectors per token, 0.02:200, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.00005 LR, 10k steps 75 image crop data set) https://mega.nz/folder/JPVSVLbQ#SqGZb7OVKe_UNRvI0R8U8A
	* Notes by uploader: Here is a terrible Ghislaine Dedoldia embedding I made while testing sd-tagging-helper and the new webui dataset tag editor extension. She has no tail because the crops were shit and I only trained on crops made using the helper. Sometimes the eye patch is on the wrong side because of two images where it was on the wrong eye. Stomach scar is sometimes there sort of but probably needed more time in the oven. She doesn't have dark skin because the AI is racist and probably because it was only tagged on half the images.
	* Uploader: Use "dark-skinned female" in your prompt or she will be pale
* Mizuryu-Kei (Mizuryu Kei): https://files.catbox.moe/bcy7vx.pt
* kidmo: https://litter.catbox.moe/44e28e.pt
	* dataset:kidmo
	* dataset:no filter
	* 10 tokens
	* 26k steps
	* 0.129 loss trend
	* 90-ish dataset
	* 0.0028 learning rate
	* issue: generic as shit, irradiated with kpop, potato gaming (you'll know when you try to use this shit with i2i)
* asanugget-16: https://litter.catbox.moe/9r0ixj.pt
	* dataset: asanagi
	* dataset: no pre-2010 artworks
	* 16 tokens
	* 22k steps
	* 0.114 loss trend
	* 500+ dataset (w/ auto focalpoint)
	* 0.0028 learning rate
* Ohisashimono (20k to 144k): https://www.mediafire.com/folder/eslki3wzlmesj/ohi
* Shadman: https://files.catbox.moe/fhwn7m.png
* ratatatat74: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
	* Uploader: Because the source images were prominently lewd in some shape or form, it really likes to give half-naked people.
	* In combination with Puuzaki Puuna, it certainly brings out some interesting humanoid Nanachis.
* WLOP: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA/folder/KWJUSR7T
	* This embedding has 24 vectors, has been trained by a rate of 0.00005 and was completed at the steps of around 35000.
	* The embedding was trained on NovelAI (final-pruned.ckpt).
	* Uploader's Note: This embedding has a HUGE problem in keeping the signature out - feel free to crop out the signature if you wish to redo the embedding. If you do find a way to remove it without recreating the whole embedding - feel free to post it in 4chan/g/ and I may stumble upon it.
	* Note 2: Use inpainting on the face in img2img to create some beautiful faces if they come out distorted initially.
* Asutora style embedding (mainly reflected in coloring and shading, since his faces are very inconsistent): https://mega.nz/folder/nZoECZyI#vkuZJoQyBZN8p66n4DP62A 
	* uploader: satisfactory results over 20k steps
	* Comparisons: https://i.4cdn.org/g/1667701438177228.jpg
* y'shtola: https://files.catbox.moe/5hefsb.pt
	* Uploader: You may need to use square brackets to lower it's impact. Also it likes making cencored pics unless you add penis to the input prompt
* Selentoxx (nai, 16v, 10k): https://files.catbox.moe/0j7ugy.png
* Aki (Goodboy, nai, 16v, 10k): https://files.catbox.moe/1p14ra.png
* Sana (nai, 15v): 
	* 10k: https://files.catbox.moe/g112gm.png
	* 100k: https://files.catbox.moe/3ndubu.png
	* In case these aren't good, use:
	* 10k: https://files.catbox.moe/r5ciho.pt
	* 25k: https://files.catbox.moe/e6aurx.pt
	* 50k: https://files.catbox.moe/lz016k.pt
	* 75k: https://files.catbox.moe/jhdjc9.pt
	* 100k: https://files.catbox.moe/2lvv2z.pt
	* Uploader note: don't use more than 0.8 weighting or else it gets deep fried
* delutaya: https://files.catbox.moe/r6pylz.pt
* Delutaya (another unrelated, 16v, 10k, nai): https://files.catbox.moe/kv2hdd.png
* mano-aloe-v1q (nai, manoaloe,mano aloe): https://files.catbox.moe/0i5qfl.pt
* Fauna (16v, 10k, nai): https://files.catbox.moe/zizgrw.png
* wawa (15v, 10k, nai): https://files.catbox.moe/2vpyi2.png
* Wagashi: https://mega.nz/file/exM21aTT#eawWbqsmajzs-TUCWfrVHvsG2HBEZ3HcYR5cy1AxFPw
* Deadflow: https://mega.nz/file/y41WHIgC#pXtCly7bzjDNJ7RZl7685_Nj1LTliIif_f_1BWMhHSE
* Elira (16v, 3k, nai sfw): https://litter.catbox.moe/4ylbez.png
* Rratatat (NAI, 16v, 10k): https://files.catbox.moe/nrekhk.png
	* Uploader: Works better with "red hair, multicolored hair, twintails"
* WLOP (reupload, retrained WITHOUT signatures - 24 vectors, 0.00005 learning rate, around 19000 steps: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
* ratatatat74 (reupload, retrained WITHOUT VAE - 24 vectors, 0.00005 learning rate, 13500 steps): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
* Wiwa embed steps pre deep frying: https://files.catbox.moe/6lu6od.zip
* Nilou (by anon, not sure if safe or of any training info, NOTE TO MYSELF SEARCH FOR THIS EMBED's DISCORD): https://cdn.discordapp.com/attachments/1019446913268973689/1039909937884713070/nilou.pt
	* https://pastebin.com/AJAuVqCi
* Makima (500s, 4v, NAI): https://i.4cdn.org/h/1668023713496532.png
* Fauna (updated, NAI, 8v, 10k): https://files.catbox.moe/dmu00i.png
* New rrat (8v, 10k, NAI): https://files.catbox.moe/fyqxjf.png
* Weine (8v, 10k, nai): https://files.catbox.moe/b9cn4z.png
* Moona (10k, 8v, nai): https://files.catbox.moe/tuh4nj.png
	* Comparison with Moona 2: https://i.4cdn.org/vt/1668038525258037s.jpg
* Aki (another, Goodboy, nai, 8v, 10k, nai): https://files.catbox.moe/k2cgxj.png
* Delu (another, notaloe, 8v, 10k, nai): https://files.catbox.moe/cvykdm.png
* Moona 2 (another anon, nai, moonmoon, nai, 8v, 10k): https://files.catbox.moe/yh8ora.png
	* Comparison with the Moona 4 links up: https://i.4cdn.org/vt/1668038525258037s.jpg
* Kobogaki (nai, 8v, 10k): https://files.catbox.moe/0r3a8o.png
* Yopi (nai, 8v, 10k): https://files.catbox.moe/hoh865.png
* FreeStyle/Yohan TI by andite#8484 (trained on ALL of his artwork, not only skin): https://cdn.discordapp.com/attachments/1019446913268973689/1038423463314075658/yohanstyle.pt
	* https://twitter.com/yohan1754?lang=en
* Matchach TI by methane#3131: https://cdn.discordapp.com/attachments/1019446913268973689/1040271410217635920/matcha-20000.pt
	* Might need to add cat ears to negative prompt because for some reason it appears
* Elira (8v, 10k, nai): https://files.catbox.moe/ldeg3v.png
	* Linked comparison (Elira default-5500 16v 5500 steps, Wiwa 4v 10000 steps, Elira t8 8v 10000 steps): https://i.4cdn.org/vt/1668135849025419s.jpg
* Reine (35v, 39500s, nai90sd10): https://files.catbox.moe/m0he7i.png
* Kobo (kbknr, 10k, 16v, NAI): https://files.catbox.moe/kphjec.png
* Kaela (Kovalski) (NAI, 4500k, 8v): https://files.catbox.moe/nxp368.png
	* Uploader: Try, eyewear on head, blonde hair, red eyes, fur trim, jacket, white dress, red ribbon behind hair,
	* Dataset?: https://files.catbox.moe/sqci4d.PNG
* Luna (LunaHime, NAI, 8v, 10k): https://files.catbox.moe/45fe4m.png
	* needs heterochromia to force the two eye colors 
* Zeta (Zetanism, 8v, 10k, nai): https://files.catbox.moe/z1u5py.png
* Aki (Goodboy) (NAI, 8v, 10k): https://litter.catbox.moe/vfd9fw.png
* Kobo (KoboGaki) (NAI, 8v, 10k): https://litter.catbox.moe/7hssgl.png
* Delu(?) (NotAloe) (NAI, 8v, 10k): https://litter.catbox.moe/9gdr5t.png
* Yopi (NAI, 8v, 10k): https://litter.catbox.moe/bhd01v.png
* AChan (NAI, 8v, 10k): https://i.4cdn.org/vt/1668274461405432.png
	* https://litter.catbox.moe/k5sifc.png
* Wiwa's alt hair (Elira, NAI, 8v, 10k): https://files.catbox.moe/vxz1yo.png
* miata8674 (45k training steps (4 Colab rounds)): https://mega.nz/folder/nZoECZyI#vkuZJoQyBZN8p66n4DP62A
	* Focuses on faces, the defining features of the style are general sketchiness and the eyes. Strengthened by the mention of eyelashes and eyeshadow
* Asagi Igawa, Edjit, and Rouge the Bat (RealYiffingFar#4510): https://mega.nz/folder/5nIAnJaA#YMClwO8r7tR1zdJJeTfegA
	* Has training info and a tutorial
* NIXEU: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
	* By uploader: 24 vectors, 0.00005 training rate, around 16500 steps and 48 reference images with NovelAI (final-prune.ckpt)
	* From the testings that I have done, it is able to replicate the artstyle quite well with one exception - the primary problem being the eyes - they seem to be slightly overbaked. My suggestion is to use img2img to circumvent that problem.
	* Regardless: I recommend a CFG of around 8.5 and prompts such as 'soft lighting' which would underline the style. Requires a bit of fine tuning regarding prompts seeing that it is rather delicate to the touch,
* frank franzetta: https://huggingface.co/sd-concepts-library/frank-frazetta
* meme50 (WIP, 0.004 LR, 20k): https://litter.catbox.moe/e9v33j.pt
	* https://litter.catbox.moe/a31cuf.pt
* Anya (probably a reupload from a collection, v8, 8500s, NAI): https://files.catbox.moe/b8ghxx.png
* Amelia Watson (amedoko, 8v, 10k, NAI): https://files.catbox.moe/qc3qt2.png
	* Produces yellow eyes, prompt for blue eyes
* Kiara (kiarer, 10k, 5v, NAI): https://files.catbox.moe/87hdj3.png
	* op: tried to get a nice spread of quality images from different outfits and artists. It probably won't get any of her outfits right, but the girl in the output is very clearly a wawa
* NecoArc: https://mega.nz/folder/ToFEARJa#yvSV_Cb5c6KxjM3wXR2_ZA
	* Another anon uploaded a mirror (not sure if safe): https://gofile.io/d/fvz1Tl
* Trixie Lulamoon (100k, 16v, anything 3.0 pruned fp16): https://files.catbox.moe/8ek5o0.png
	* For blue/purple witches
	* The embedding associated the right blue tone with "aqua", as well as the correct purple tone with "purple". It tends to add long eyelashes and eyeshadow, but those can be enhanced with prompts.
	* The correct hairstyle comes from "hair over shoulder" and "asymmetrical hair", but "asymmetrical bangs" helps achieve it.
	* It dislikes clothes and will try to cheat them right off your prompts.
	* As far as I can tell it works decently well on any Nai-based model and at varying Clip Skip levels, but it was trained on Anything v3 with Clip Skip on 1. Going over 1.2 weight on clip skip 1 looks weird sometimes
	* Reupload by anon (not sure if safe): anonfiles.com/1ev4m8Hey1/trixie_lulamoon_pt
* Not sure what this is: https://files.catbox.moe/9l2nrw.pt
	* Ex pic: https://i.4cdn.org/h/1668550663647424s.jpg
* Blannie from Bleague of Blegends (Annie from LOL, 18 tokens large(?)): https://files.catbox.moe/un85e4.pt
	* Ex pic with skin: https://i.4cdn.org/h/1668567424263709s.jpg
* Nahida v2: https://cdn.discordapp.com/attachments/1019446913268973689/1031321278713446540/nahida_v2.zip
	* Nahida (50k, very experimental, not enough images): https://files.catbox.moe/2794ea.pt
* look at the 2nd and 3rd images: https://www.reddit.com/gallery/y4tmzo
* Negative embedding to be used in the negatives (supposedly a quality enhancer, supposedly fixes hands): https://huggingface.co/datasets/Nerfgun3/bad_prompt
	* https://old.reddit.com/r/StableDiffusion/comments/yy2i5a/i_created_a_negative_embedding_textual_inversion/
* Elysia (Honkai Impact): https://mega.nz/file/qnxiDQxR#3g7_gI-8OD83gPEWu-XjcPCedHCsvbjnxzjxW4c8GAo
	* https://www.pixiv.net/en/artworks/102931348
* Koyori (Koyoyo, NAI, 8v, 10k): https://files.catbox.moe/empi4b.png
	* Might need to prompt for the ears and midriff
* Kronii (10k, 8v, NAI): https://files.catbox.moe/vltkov.png
* Choco (ChocoSen, NAI, 8v, 10k): https://files.catbox.moe/1jf119.png
* Calli (Yaboy, NAI, v8, 10k) (https://s1.alice.al/vt/image/1668/53/1668537070785.jpg): https://files.catbox.moe/ilcpnn.png
	* Might need to prompt pink hair
* Ina (Hololive, tag: ina-nai-100, https://s1.alice.al/vt/image/1668/66/1668666743766.jpg): https://files.catbox.moe/lsaydm.pt
* Omega Alpha (NAI, 8v, 10k): https://files.catbox.moe/19tun3.png
* Elira (old): https://files.catbox.moe/6lu6od.zip
* Elira alt (NAI, v8, 10k): https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ/file/jvJwzDhB
* Pomu (ImPomu, NAI, v8, 10k, https://s1.alice.al/vt/image/1668/69/1668692914583.jpg): https://files.catbox.moe/9zdw2f.png
	* Dead: https://litter.catbox.moe/qp32ku.png
	* Try: Blonde hair, fairy wings
	* Might be a good idea to exclude ocean? Dont ask, literally 1 image in dataset out of like 40 I dont understand why. 
* Feesh (NAI, v8, 10k, https://s1.alice.al/vt/image/1668/70/1668703156236.jpg): https://files.catbox.moe/3v7yhj.png
* Suisei (no training info, https://i.4cdn.org/vt/1668897948153665.png): https://files.catbox.moe/9z6ni5.pt
* Rosemi (RosemiSama, NAI, v8, 10k, https://i.4cdn.org/vt/1668897966152847.jpg): https://files.catbox.moe/2oj2qd.png
	* Might be tough to remove her thornyness.
* SelenToxx (NAI, v8, 10k, https://i.4cdn.org/vt/1668897792400569.png): https://files.catbox.moe/obxl01.png
	* Just beware of ember. I need to remove any trace of him from the dataset.
* Anya (from Anya-Petra thread, https://i.4cdn.org/vt/1668969732782744.png): https://files.catbox.moe/h3t0du.pt
* Reiumuwu (NAI, v8, 10k, https://i.4cdn.org/vt/1669075492548084.jpg): https://files.catbox.moe/woxu4q.png
* NinaMommy (NAI, v8, 10k): https://files.catbox.moe/875g3s.png
* Enna (EnnaBird, NAI, v8, 10k, https://i.4cdn.org/vt/1669164314343707.jpg): https://files.catbox.moe/dkwu0d.png
* Ethyria (MillieMilk, NAI, 8v, 7.5k, https://i.4cdn.org/vt/1669158802233887.jpg): https://files.catbox.moe/57vpza.png

### **Hypernetworks:**
!!! info If a hypernetwork is <80mb, I mislabeled it and it's an embedding

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

* anon: "Requires extremely low learning rate, 0.000005 or 0.0000005"
**Good Rentry: https://rentry.co/naihypernetworks**
Hypernetwork Dump: https://gitgud.io/necoma/sd-database
Collection: https://gitlab.com/mwlp/sd 
Another collection: https://www.mediafire.com/folder/bu42ajptjgrsj/hn
Senri Gan: https://files.catbox.moe/8sqmeh.rar
Big dumpy of a lot of hypernets (has slime too): https://mega.nz/folder/kPdBkT5a#5iOXPnrSfVNU7F2puaOx0w
Collection of asanuggy + maybe some more: https://mega.nz/folder/Uf1jFTiT#TZe4d41knlvkO1yg4MYL2A
Collection: https://mega.nz/folder/fVhXRLCK#4vRO9xVuME0FGg3N56joMA
**Mogubro + constant updates: https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ**
* **Korean megacollection:**
	* https://arca.live/b/hypernetworks?category=%EA%B3%B5%EC%9C%A0
		* Link scrape: https://pastebin.com/p0F4k98y
	* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948
	* Original: https://arca.live/b/hypernetworks/60930993
	* **Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw**

**Chinese telegram (uploaded by telegram anon): magnet:?xt=urn:btih:8cea1f404acfa11b5996d1f1a4af9e3ef2946be0&dn=ChatExport%5F2022-10-30&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce**
>I've made a full export of the Chinese Telegram channel.
>
>It's 37 GB (~160 hypernetworks and a bunch of full models).
>If you don't want all that, I would recommend downloading everything but the 'files' folder first (like 26 MB), then opening the html file to decide what you want.
* Dead link: https://t.me/+H4EGgSS-WH8wYzBl

* Big collection: https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing
* https://arca.live/b/aiart/60927159?p=1
* https://arca.live/b/hypernetworks/60927228?category=%EA%B3%B5%EC%9C%A0&p=2
* NAIHypernetwork collection: https://rentry.org/naihypernetworks

Found on 4chan:
* bigrbear: https://files.catbox.moe/wbt30i.pt
* Senran Kagura v3 (850 images, 0.000005 learn rate, 20000 steps, 768x768): https://files.catbox.moe/m6jynp.pt
	* CGs from the Senran Kagura mobile game (NAI model): https://files.catbox.moe/vyjmgw.pt
		* Ran for 19,000 steps with a learning rate of 0.0000005. Source images were 768x576. It seems to only reproduce the art style well if you specify senran kagura, illustration, game cg, in your prompt.
	* Old version (19k steps, learning rate of 0.0000005. Source images were 768x576. NAI model. 850 CGs): https://files.catbox.moe/di476p.pt
	* Senran Kagura again (850, deepdanbooru, 0.000006, 768x576, 7k steps): https://files.catbox.moe/f40el4.pt
* Danganronpa: https://files.catbox.moe/9o5w64.pt
	* Trained on 100 images, up to 12k with 0.000025 rate, then up to 18.5k with 0.000005
	* Also seed 448840911 seems to be great quality for char showcase with just name + base NAI prompts.
* Alexi-trained hypernetwork (22000 steps): https://files.catbox.moe/ukzwlp.pt
	* Reupload by anon: https://files.catbox.moe/slbk3m.pt
	* works best with oppai loli tag
	* https://files.catbox.moe/xgozyz.zip
* Etrian Odyssey Shading hypernetwork (20k steps, WIP, WD 1.3)
* colored drawings by Hass Chagaev (6k steps, NAI): https://files.catbox.moe/3jh1kk.pt
* Morgana: https://litter.catbox.moe/3holmx.pt
* EOa2Nai: https://files.catbox.moe/ex7yow.7z
* EO (WD 1.3): https://files.catbox.moe/h5phfo.7z
* Taran Jobu (oppai loli, WIP, apparently it's kobu not jobu)
	* https://files.catbox.moe/72wjlt.pt
* Higurashi (NAI:SD 50:50): https://litter.catbox.moe/lfg6ik.pt 
	* by op anon: "1girl, [your tags here], looking at viewer, solo, art by higurashi", cfg 7, steps about 40"
* Tatata (15 imgs, 10k steps): https://files.catbox.moe/7hp2es.pt
* Zankuro (0.75 NAI:WD, 51 imgs, 25k+ steps): https://files.catbox.moe/tlurbe.pt
	* Training info + hypernetwork: https://files.catbox.moe/4do43z.zip 
* Test Hypernetwork (350 imgs where half are flipped, danooru tags, 0.00001 learning rate for 3000 steps, 0.000004 until step 7500): https://files.catbox.moe/coux0u.pt
* Kyokucho (40k steps, good at 10-15k, NAI:WD1.2): https://workupload.com/file/TFRuGpdGZZn
* Final Ixy (more detail in discord section): https://mega.nz/folder/yspgEBhQ#GLo7mBc1EH7RK7tQbtC68A
	* Old Ixy (more data, more increments): https://mega.nz/file/z8AyDYSS#zbZFo9YLeJHd8tWcvWiRlYwLz2n4QXTKk04-cKMmlrg
	* Old Ixy (less increments, no training data): https://mega.nz/file/ixxzkR5T#cxxSNxPF1KmszJDqiP4K4Ou8tbl1SFKL6DdQC58k6zE
* Grandblue Fantasy character art (836 images, 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000 learn rate, 20000 steps, 1024x1024): https://files.catbox.moe/2uiyd4.pt
* Bombergirl (Stats: 178 images, 5e-8 learn rate continuing from old Bombergirl, 20000 steps, 768x768): https://files.catbox.moe/9bgew0.pt
	* Old Bombergirl (178 imgs, 0.000005 learning rate, 10k, 768x768): https://files.catbox.moe/4d3df4.pt
* Aki99 (200 images , 512x512, 0.00005, 19K steps, NAI): https://files.catbox.moe/bwff89.pt
* Aki99 (200 images , 512x512, 0.0000005, 112K steps, learning prompt: [filewords], NAI): https://www.mediafire.com/file/sud6u1vb0gvqswu/aki99-112000.7z/filehttps://files.catbox.moe/6hca0u.pt
* Great Mosu: https://files.catbox.moe/mc1l37.pt
	* Reupload: https://mega.nz/file/MlRVGbDJ#hwA868cievybQC_7T1yc3bDouUB54Bor-LsCfs04LEI
* mda starou: https://a.pomf.cat/xcygvk.pt
* Mogudan (12 vectors per token, 221 image dataset, preprocessing: split oversize, flipped mirrors, deepdanbooru auto-tag, 0.00005 learning rate, 62,500 steps): https://mega.nz/file/UtAz1CZK#Y5OSHPkD38untOPSEkNttAVi2tdRLBFEsKVkYCFFaHo
* Onono Imoko: https://files.catbox.moe/amfy2x.pt
	* Dataset: https://files.catbox.moe/dkn85w.zip 
* Etrian Odyssey (training rate 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000,20k steps, 512 x 512 pics): https://files.catbox.moe/94qm83.7z
* Jesterwii: https://files.catbox.moe/hlylo4.zip
* jtveemo (v1): https://mega.nz/folder/ctUXmYzR#_Kscs6m8ccIzYzgbCSupWA
	* 35k max steps, 0.000005 learning rate, 180 images, ran through deepbooru and manually cleaned up the txt files for incorrect/redundant tags.
	* Recommended the 13500.pt, or something near it
	* Recommended: https://files.catbox.moe/zijpip.pt
* Artsyle based on Yuugen (HBR) (Stats: 103 images, 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000 learn rate, 20000 steps, 1024x1024,Trained on NAI model): https://files.catbox.moe/bi2ts0.7z
* Alexi: https://files.catbox.moe/3yj2lz.pt (70000 steps)
	* as usual, works best with oppai loli tag. chibi helps as well
	* changes from original one i noticed during testing:
		-hair shading is more subtle now
		-nipple color transition is also more subtle
		-eyelashes not as thick as before, probably because i used more pre-2022 pictures. actually bit sad about it, but w/e
		-eyes in general look better, i recommend generating on 768×768 with highres fix
		-blonde hair got a pink gradient for some reason
		-tends to hide dicks between the breasts more often, but does it noticeably better
		-likes to add backgrounds, i think i overcooked it a bit so those look more like artifacts, perhaps with other prompts it will look better
		-less hags
		-from my test prompts, it looked like it breaks anatomy less often now, but i mostly tested pov paizuri
		-became kinda worse at non-paizuri pictures, less sharpness. because of that, i'm also including 60000 steps version, which is slightly better at that, but in the end, it's a matter of preference, whether to use newer version or not: https://files.catbox.moe/1zt65u.pt
* Ishikei: https://www.mediafire.com/folder/obbbwkkvt7uhk/ishikemono
* Curss style (slime girls): https://files.catbox.moe/0sixyq.pt 
* WIP Collection of hypernets: https://litter.catbox.moe/xxys2d.7z
* DEAD LINK Mumumu's art: https://mega.nz/folder/tgpikL6C#Mj0sHUnr-O6u4MOMDRTiMQ
* Senri Gan: https://files.catbox.moe/8sqmeh.rar
	* 2 hypernetworks and 5 TI
	* Anon: "For the best results I think using hyper + TI is the way. I'm using TI-6000 and Hyper-8000. It was trained on CLIP 1 Vae off with those rates 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000."
* Ulrich: https://files.catbox.moe/jhgsxw.zip
* akisora: https://files.catbox.moe/gfdidn.pt
* lilandy: https://files.catbox.moe/spzm60.pt
* shadman: https://files.catbox.moe/kc850y.pt
	* anon: "if anyone else wants to try training, can recommend - 0.00005:2000, 0.000005:4000, 0.0000005:6000 learning rate setup (6k steps total with 250~1000 images in dataset)"
* not sure what this is, probably a style: https://files.catbox.moe/lnxwks.pt
* ndc hypernet, muscle milfs: https://files.catbox.moe/hsx4ml.pt
* Asanuggy: https://mega.nz/folder/Uf1jFTiT#TZe4d41knlvkO1yg4MYL2A
* Tomubobu: https://files.catbox.moe/bzotb7.pt
	* Works best with jaggy lines, oekaki, and clothed sex tags.
* satanichia kurumizawa macdowell (around 552 pics in total with 44.5k steps, most of the datasets are fanarts but some of them are from the anime, tagged with deepdanbooru, flipped and manually cropped): https://files.catbox.moe/g519cu.pt
* Imazon v1: https://files.catbox.moe/0e43tq.pt
* Imazon v2: https://files.catbox.moe/86pkaq.pt
* WIP Baffu: https://gofile.io/d/4SNmm5
* Ilulu (74k steps at 0.0005 learning rate, full NAI, init word "art by Ilulu"): https://files.catbox.moe/18ad25.pt
* belko paizuri (86k swish + normalization): https://www.mediafire.com/folder/urirter91ect0/belkomono
	* WIP: training/0.000005/swish/normalization 
* Pinvise (Suzutsuki Kirara) (NAI-Full with 5e-6 for 8000 steps and 5e-7 until 12000 steps on 200 (400 with flipped) images): https://litter.catbox.moe/glk7ni.zip
* Bonnie: https://files.catbox.moe/sc50gl.pt
* Another batch of artists hypernetworks (some are with 1221 structure, so bigger size)
	* https://files.catbox.moe/srhrn6.pt - diathorn
	* https://files.catbox.moe/dytn06.pt - gozaru
	* https://files.catbox.moe/69t1im.pt - Sunahara Wataru
* kunaboto (new swish activation function + dropout using a learning rate of 5e-6:12000, 5e-7:30000): https://files.catbox.moe/lynmxm.pt
	* aesthetic: https://files.catbox.moe/qrka4m.pt
* Reine: https://litter.catbox.moe/1yjgjg.pt
* Om (nk2007): 
	* 250 images (augmented to 380), learning rate: 5e-5:380,5e-6:10000,5e-7:20000, template: [filewords] 
	* 10k step : https://files.catbox.moe/8kqb4c.pt
	* 16k step : https://files.catbox.moe/7vtcgt.pt
	* 20k step (omHyper): https://files.catbox.moe/f8xiz1.pt
* Spacezin: https://mega.nz/folder/Os5iBQDY#42xOYeZq08ZG0j8ds4uL2Q
	* excels at his massive tits, covered nipples, body form, sharp eyes, all that nice stuff
	* no cbt data
	* using the new swish activation method +dropout, works very well, trained at 5e-6 to 14000
	* data it was trained on and cfg test grid included in the folder
	* Hypernetwork trained on 13 handpicked images from spacezin
	* recommend using spacezin in the prompt, using 14000 step hypernetwork, lesser steps are included for testing
	* Aesthetic gradient embedding included
* amagami artstyle (30k,5e-6:12000, 5e-7:30000,swish+dropout): https://files.catbox.moe/3a2cll.7z
* Ken Sugimori (pokemon gen1 and gen2) art: https://files.catbox.moe/uifwt7.pt
* mikozin: https://mega.nz/folder/a0wxgQrR#OnJ0dK_F6_7WZiWscfb5hg
	* Trained a hypernetwork on mikozin's art, using nai full pruned, swish activation method+dropout
	* placing mikozin in the prompt will make it have a stronger effect, as all the training prompts include the [name] at the end.
	* has a number of influences on your output, but mostly gives a very soft, painted style to the output image
	* Aesthetic gradient embedding also included, but not necessary
	* check the training data rar to read the filewords to see if you want to call anything it was specifically trained on
	* Found on Discord (copied from SD Training Labs discord, so grammar mistakes may be present):
* Pippa (trained on NAI 70%full-30%sfw): https://files.catbox.moe/uw1y8g.pt
* reine (WIP): https://files.catbox.moe/od4609.pt
* WiseSpeak/RubbishFox (updated): https://files.catbox.moe/pzix7f.pt
	* Info: Uses 176 Fanbox images that were preprocessed with splitting, flipping and mild touchup to remove text in Paint on about 1/4th of the images. I removed images from the Preprocess folder that did not have discernable character traits. Most images are of Tamamo since that is his waifu. Total images after split, flip, and corrections was 636. Took 13 hours at 0.000005 Rate at 512x512. Seems maybe a bit more touchy than the 61.5K file, but I believe that when body horror isn't present you can match the RubbishFox's style better.
* Style from furry thread: https://files.catbox.moe/vgojsa.pt
* 2bofkatt (from furry thread): https://files.catbox.moe/cw30m8.pt
* Hypernetwork trained on all 126 cards from the first YGO set in North America, 'Legend Of The Blue Eyes White Dragon' released on 03/08/2002: https://mega.nz/folder/ILkwRZLb#UJ03LDIfcMiFTn6-pyNyXQ
* WiseSpeak (Rubbish Fox on Twitter): https://files.catbox.moe/kyllcc.pt
	* Info: Uses 176 images that were preprocessed with splitting, flipping and mild touchup to remove text in Paint on about 1/4th of the images. I removed images from the Preprocess folder that did not have discernable character traits. Most images are of Tamamo since that is his waifu. Total images after split, flip, and corrections was 636. Took 8 hours at 0.000005 Rate at 512x512
	* 93k, less overtrained: https://files.catbox.moe/fluegz.pt
* Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw
* Crunchy: https://files.catbox.moe/tv1zf4.pt
* Obui styled hypernetwork (125k steps): https://files.catbox.moe/6huecu.pt
* KurosugatariAI (2 hypernets, 1 embed, embedding is light at 17 token weight. at 24 or higher creator anon thinks the effect would be better): https://mega.nz/folder/TAggRTYT#fbxf3Ru8PkXz_edIkD2Ttg
* Amagami (Layer structure 1, 1.5 1.5 1; mish; xaviernormal; No layer normalization; Dropout O (appling only at 2nd layer due to bug); LR 8e-06 fixed; 20k done): https://files.catbox.moe/ucziks.7z
* Reine (from VTuber dump, might be pickled): https://files.catbox.moe/uf09mp.pt
* Onono imoko: https://mega.nz/file/67AUDQ4K#8n4bzcxGGUgaAVy7wLXvVib0jhVjt2wPS-jsoCxcCus
	* Info moved to discord section
* Sironora: 
	* 30k: https://files.catbox.moe/oej0si.pt
	* 17k: https://files.catbox.moe/kodsvu.pt
* minakata hizuru (summertime girl): https://files.catbox.moe/gmbnnr.pt
* a1 (4.5k): https://files.catbox.moe/x6zt6u.pt
* 焦茶 / cogecha hypernetwork, trained against NAI (DEAD LINK): https://mega.nz/folder/BLtkVIjC#RO6zQaAYCOIii8GnfT92dw
* 山北東 / northeast_mountain hypernetwork, trained against NAI (DEAD LINK): https://mega.nz/folder/RflGBS7R#88znRpu7YC1J1JYa9N-6_A
* emoting mokou (cursed): https://mega.nz/folder/oPUTQaoR#yAmxD_yqeGqyIGfOYCR4PQ
* Cutesexyrobutts and gram: https://files.catbox.moe/silh2p.7z
* Scott: https://files.catbox.moe/qgqbs7.7z
* zunart (NAI, steps from 20000 to 50000): https://mega.nz/file/T9RmlbCQ#_JPkZqY5f0aaNxVc8MnU3WQHW4bv_yCWzJqOwL8Uz1U
* HBRv3D aka Heaven Burns Red (yuugen) retrained on new dataset of 142 mixed images: https://files.catbox.moe/urjkbm.7z
	* Setting was 1,2,1 relu ,Learning rate: 5e-6:12000, 5e-7:30000
* momosuzu nene: https://mega.nz/folder/s8UXSJoZ#2Beh1O4aroLaRbjx2YuAPg
* TATATA and Alkemanubis: https://mega.nz/folder/zYph3LgT#oP3QYKmwqurwc9ievrl9dQ
	* Tatata: Contains dataset, hypernetworks for steps 10000-19000 with a 1000 steps step, as well as full res sfw and nsfw comparisons.
	* It was created before layer structure option, so it parameters are 1, 2, 1 layer structure, linear activation function.
	* Alkemanubis: Alkemanubis is with elu activation function and normalisation, Alkemanubis4 is with swish and dropout, Alkemanubis5 is with linear and dropout. All have 1, 2, 4, 2, 1 layer structure.
	* dataset and more fullres preview grid are inside too.
* HKSW (wrong eye color because of dataset): https://files.catbox.moe/dykyab.pt
* Nanachi and Puuzaki Puuna (retrained, 4700 steps, sketches are good, VAE turned off): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
* HiRyS: https://mega.nz/file/Mk8jTZ4I#TdlF5Bxwz_gAuQeR0PWa_YUZotcQkA34d6m49I6eUMc
	* Dead link, I think this is the same hypernetwork: https://litter.catbox.moe/rx8uv0.pt
* 4k, 3d, highres images: 4k, 3d, highres images: https://mega.nz/file/UAEHkbhK#R-zdpiIz6Ig2-laa-M9_Hmtq6xgLNJZ0ZwVOiXt3OSc
	* It has a preference for 3d design, large breasts and curves. It also has a preference for applying backgrounds,if none suggested. usually parks, beaches, indoors or cityscapes
	* Comparison: https://i.4cdn.org/h/1667278030582788.png
* Okegom (Funamusea / Deep Sea Prisoner): https://mega.nz/file/XYQF3YoZ#BAvBQduEx-tnUKvyJQ3mH-zOa_cKUKxpc58YpO8h2jc
	* Crashed after 5.3k steps, continued training after when hypernetwork training resuming is broken. Apprently it got better
	* Uploader: Alright, it's done. Maybe it's the small training data or the mediocre tagging but sometimes you get stuff that doesn't resemble their art style. Still releasing the three models I liked though, they work nicely with img2img.
* Funamusea/Okegom/Mogeko (12500 steps): https://mega.nz/file/SBg0zBIa#BU1KkBY1vMvLXpfkDci1RZYi5f8P0yN5oyQzGYXF8q0
	* Notes by uploader:
	>Most results (at least with img2img) will have a chibi style regardless of your prompt.
	>30 steps recommended.
	>Does very well with white skin/pale characters, this is because the hypernetwork is trained mainly on white characters. Not because I wanted to but because it's what she tends to draw the most.
	>Hypernetwork has most of her NSFW art in its data including a fanart which looks like it was drawn by her, just so the AI has a reference. So, yes, it can generate nudity and porn in her style, although I'm not sure about penetration stuff because I haven't tried.
	>"outline" tag is recommended in prompt to have the same thick outlines she often uses in her artwork.
* Sakimichan: https://mega.nz/file/TBJwFDLI#H_bgih8qbWe-EN4ntL_7ur6Ylr2qbcxhDwlC2AfWpnc
	* dead link: https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8
* arnest (109 images, 12000 steps): https://mega.nz/file/HNIhlZ7B#o1hpR04PxBDWTEHDfxLfbRi_9K56HVJ58YgCwDUeRMw
	* uploader: Hypernetwork trained on 109 total images dating from 2015 to 2022, including his deleted NSFW commissions and Fanbox content. Also trained on like two or three pre-2015 images just because why not. Should be able to do Touhou characters (especially Alice and Patchouli) extremely well.
	* I recommend using the white pupils tag for the eyes to look like picrel.
* Zanamaoria (20k steps, 47 imgs, mostly dark-skinned elves, and paizuri/huge tits): https://files.catbox.moe/10iasp.pt
	* 18500 steps: https://files.catbox.moe/xgf1ho.pt
* Pinvise (30k steps, 5e-6 for 8k steps and 5e-7 for the rest): https://files.catbox.moe/dec3h3.pt
	* dead: https://litter.catbox.moe/nrpkuy.pt
* Black Souls II (V2 wasn't uploaded because it was "disappointing"):
	* V1 (Image: 181 augmented to 362,Learning Rate 5e-5:362,5e-6:14000,5e-7:20000, steps: 10k): https://files.catbox.moe/fdoyt9.pt
	* V3 (Image:164 augmented to 328, Learning Rate 5e-5:328,5e-6:14000,5e-7:20000, steps: 10k): https://files.catbox.moe/1r36tp.pt
		* uploader: Unlike V1, I manually edited almost all tags generated with deepdanbooru with the dataset tag editor
	* Uncensored X/Y plots:
		* V3 (strength: 1) : https://files.catbox.moe/tse4kr.png, https://files.catbox.moe/8y91f0.png (no 'sketch')
		* V1 (strength: 0.7): https://files.catbox.moe/pml06i.png ('sketch'), https://files.catbox.moe/18993y.png (without "sketch")
	* Uploader: Those two hypernetwork seem to be more accurate if we put "sketch" in the prompt. V1 break if we set hypernetwork strength to 1 (or anything over 0.8) and 0.7 seem to be the sweet spot. V3 does not seem to have the same problem.
* Hataraki Ari (30k, 50k, and 100k steps): https://mega.nz/folder/TZ5jXYrb#-NXJo8wlmanr8ebbJ5GBBQ
	* Training Info: 
	>Modules: 768, 320, 640, 1280
	>Hypernetwork layer structure: 1, 2, 1
	>Activation function: swish + dropout
	>Layer weights initialization / normalization: none
	>115 images, size 512x512, manually selected from patreon gallery on sadpanda
	>Watermarks + text manually removed or cropped out
	>Deepbooru used for captions
	>Hypernetwork learning rate: 5e-6:12000, 5e-7:30000, 2.5e-7:50000, 1e-7:100000

	* Uploader note: Works best with huge or gigantic breasts. Occasionally has some problems with extra limbs or nipples. Tags like tall female, muscular female or abs may lead to small heads or weirdly proportioned bodies, so I recommend lowering the weighting on those.

* IRyS (not sure if this is a reupload of a previous one): https://files.catbox.moe/qnery5.pt
* Nanachi (reupload, re-retrained WITHOUT sneaky VAE - 0.000005 learning rate, around 16000 steps, around 13000 steps): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
* Puuzaki Puuna (reupload, re-retrained WITHOUT sneaky VAE - 0.000005 learning rate): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
* Sayori (trained on mostly nsfw CGs (30 out of 40 images were nsfw) from nekopara, koikuma + fandisc, and tropical liquor, trained on NAI pruned): https://mega.nz/file/LegFzJxa#Q1Se9fByKcjuXA2DNWt0gCaV3rCP8U-voBKgFjOevF8
* Henreader: https://files.catbox.moe/q6t6vw.pt
	* 104 imgs, mostly from Loli no Himo and some of his recent art, used a grabber to download with gelbooru tags
	* Training settings:
		* layer: 1, 2, 1
		* activation function: linear
		* initialization: Normal
		* Images: 104 (208 with flipped images)
		* dataset: https://files.catbox.moe/e0e3nk.7z (NSFW + loli)
		* resolution: 512x512
		* Learning rate: 5e-5:832,5e-6:14000,5e-7:2000
		* steps: 10000
		* Template: [filewords] 
* Sakimichan (not sure if it's a reupload): https://cdn.discordapp.com/attachments/1041563266041794580/1041563947528093746/sakimichan.pt
* Dohna2 (apparently incorporates backgrounds better (for stuff like tentacles), anon reports underbaked, wip): https://mega.nz/file/y65DwBYQ#1BLmT4IyuUVeUrjYSIjE-oBpmMvkVp4ZSCXVV3jkOb8
	* Password: https://rentry.org/f787o
	* Original dead link: https://litter.catbox.moe/8m4ue9.7z
* Kinjo kuromomo: https://files.catbox.moe/8bgjto.pt
	* Example pic (Prompt: https://rentry.org/e8mhs): https://i.4cdn.org/g/1668467554941924s.jpg
* ruan chen yue (artstyle, rcy3):
	* Example: https://i.4cdn.org/g/1668780254347358s.jpg
	* Based on Anythingv3 (op recommended the anything vae too), set to CFG 9 for best results
	* Example prompt: masterpiece, highest quality, colorful, shiny hair, colored hair shine, ((by ruan chen yue)), rcy3, vibrant, soft face, lips, blush, sparkles, glitter, HDR
	* Negative: nsfw, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, poorly drawn hands, poorly drawn limbs, bad anatomy, deformed, amateur drawing, odd, lowres, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, multiple body parts, two-colored hair, multicolored hair
* chinanago (chinanago7010) (NAI, 10k, all drawings on gelbooru): https://files.catbox.moe/kk1rss.pt
	* Example: https://i.4cdn.org/g/1668823784304863s.jpg
* Dishwasher1910 (also known as dickwasher on /alg/) (NAI): https://files.catbox.moe/7fs8xu.pt
	* Example: https://i.4cdn.org/g/1668824088843108s.jpg
* Muk (monsieur): https://files.catbox.moe/q8jnsd.pt
	* Example: https://i.4cdn.org/g/1668824504567981s.jpg
* Olga Discordia (35k, old version): https://www.dropbox.com/s/fc8bg0ti7uy8qxz/olgadiscordiav6-35000.pt?dl=0
	* make sure you have these prompt to activate her: yellow eyes, intricate eyes, (symmetrical face), (mature female:1.2), pointy ears, elf, earrings, hair over one eye, jewelry, dark elf, breasts, black hair, long hair, dark skin, parted lips, thighhighs, gloves, 1girl, solo, 
	* final-pruned model. mixberry gives good results too. clip set at 2. vae is optional
	* More info by creator: can use final-pruned, berrymix and v3 without any problem. i do not recommend vae with it. clip set at 1 for higher detail. 2 for whatever. to get the prompt working, make sure to included dark elf, dark skinned female, and pointy ears. 
* olga discordia (Kuroinu) (50k steps):
	* https://www.dropbox.com/s/ivz7nr43b0xmbth/olgadiscordiav8-10000-7000%20armor%20-%20Copy.pt?dl=0
	* to activate olga, please use this prompt: 1girl, olga discordia, amber eyes, dark elf and dark skinned female, hair covering one eye.
	* for additional stuff, such as her outfit, you have to use purple armor, purple sleeves and purple thighhighs. for the top acccuracy, use disconnected corset purple armor. weight accordingly too.
	* NOTE: was trained with censored images. make sure to have censored and mosaic censored in the negative. put 1 or 2 emphasis on it. up to you.
	* works with every model too. works best with naileak and all berrymixes. clip at 1 or 2 depends on the model. enjoy
* Mogudan), Mumumu (Three Emu), Satou Shouji, Onomeshin, Bang-You, Aoi Nagisa, Honjou Raita, Amazon : https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ
	* Changelog of new stuff: onomeshin (pic https://i.4cdn.org/h/1669000305326267.png), Bang-You (https://i.4cdn.org/h/1669000350687492.png), Aoi Nagisa (https://i.4cdn.org/h/1669000401417659.png), Honjou Raita (uses new options, comparison between current one and the one mogubro uploaded: https://i.4cdn.org/h/1669000583045601.png), Amazon (https://i.4cdn.org/h/1669114002712582.png): 
	* Has training info, dataset, comparison, and hypernetworks
	* Amazon hypernet does the best on DPM++ 2M a Karras, has deformities on some other samplers
* Albino_Otokuyou (Otokuyou's Shinroi Ko character) (White eyelashes and true albinos): https://files.catbox.moe/k7ftww.rar
	* Good when using with Nerfgun3's new Albino_style
	* ex: https://i.4cdn.org/g/1668896107598228.jpg (Prompt: https://rentry.org/gacnc)
	* Best results: Half-closed eyes at low weight may have some benefits. Using my Albino_Otokuyou Shiroi Ko Hypernet at just 0.2 strength helps with white eyelash cohesion. Use 'parted bangs' and 'swept bangs' and prompts that clear space above the eyes to help consistently generate white eyelashes, experiment as you like.
	* Issues: My 30000step Hypernet has a slight problem squashing images, reducing the strength helps mitigate this quite abit, the AlbinoFix is slightly weaker but may be best used with Nerfgun3's embedding.
* Tatata + Dataset (supposedly trained on CHINAI + 0.45(Trinart115-SD-1.4)): https://mega.nz/folder/sTV0EI6b#hGotLRXpotvmYxqfTb_KMw/folder/8eMylBTK
* Eula Lawrence (old, seemed to be misplaced):  https://mega.nz/file/l9tAHJBD#xdXMf7vulY4GJBigxegFVLSOULONnk4o86qKHYoBZmc
* Kincora (Azur Lane artist): https://files.catbox.moe/enzbw6.pt
	*  Training:
		* >layer: 1, 2, 1
		* >activation function: linear
		* >initialization: Normal
		* >Images: 136 (half of those image are just portrait version of the other half)  or  272 if we count flipped images
		* >Dataset:  https://files.catbox.moe/yc9kkh.7z
		* >Steps: 20k
		* >Learning rate: 5e-5:816,5e-6:10000,5e-7:20000
		* >resolution: 512x512
		* >Template: [filewords] 
	* Example (it's the one on the right): https://i.4cdn.org/g/1669142706465584.jpg
* Tomoko: https://raw.githubusercontent.com/hlky/sd-embeddings/main/tomoko/tomoko.pt

Found on Discord:
* Art style of Rumiko Takahashi 

	>Base:  Novel AI's Final Pruned
	>[126 images, 40000 steps, 0.00005 rate]
	>Tips:  "by Rumiko Takahashi" or "Shampoo from Ranma" etc.
	* LINK: https://cdn.discordapp.com/attachments/1029640494915006504/1031188941245784124/rumikotakahashistyle.pt
* Amamiya Kokoro (天宮こころ) a Vtuber from Njiisanji [NSFW / SFW] (Work on WD / NAI)

	>(Training set: 36 Input images, 21500 Steps, 0.000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with nijisanji-kokoro to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0 
	* LINK: https://files.catbox.moe/032110.pt
* Haru Urara (ハルウララ) from Umamusume ウマ娘 [NSFW / SFW] (Work on WD / NAI)

	>Training set: 42 Input images, 21500 Steps, 0.000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with uma-urara to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0 
	* LINK: https://files.catbox.moe/qixn0m.pt
* Genshin Impact [SFW]

	>992 images, official art including some game assets
	>15k steps trained on nai
	>use "character name genshin impact" or "genshin impact)" for best results
	* LINK: https://files.catbox.moe/t4ooj6.pt 

	* 45k step version: https://files.catbox.moe/newhp6.pt
* Ajitani Hifumi (阿慈谷 ヒフミ) from Blue Archive [NSFW / SFW] (Work on WD / NAI)

	>Training set: 41 Input images, 20055 Steps, 0.000005 Learning rate.
	>Model: NAI-Full-Prunced 
	>Start with ba-hifumi to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0 
	>1.0 Is a little bit overkill I thought about.
	>If you want to go different costume like swimsuit or casual, I think 0.4 to 0.7 is the best ideal rate.
	* LINK: https://files.catbox.moe/ylbekm.7z 
* Higurashi no Nako Koro ni // ryukishi07's artstyle

	>Trained on Higurashi's original VN sprites. Might do Umineko's sprites next, or mix the two together.
	>8k steps, 15k steps, 18k steps included.
	* LINK: https://drive.google.com/file/d/1A8KMQV_0qNHmM8yYFAxLdt8dTWt8GoSo/view?usp=sharing 
	* DATASET: https://cdn.discordapp.com/attachments/1029640494915006504/1030760102493425664/higurashi-datset.7z
* Trained Koharu of Blue Archive. I'm not very good at English, so it's painful to read this describe.

	>Training set: 41 images, 20000 steps, 0.000005 learning rate.
	>Model: WD1.3 merged NAI (3/7 - Sigmoid)
	* LINK: https://files.catbox.moe/b6a6mc.pt
* queencomplexstyle (no training info): https://files.catbox.moe/32s6yb.pt
* Shiroko of Blue Archive. Training set: 14 images at 20000 steps 0.000005 learning rate. The tag is 'ba-shiroko'
	* Link: https://mega.nz/file/sx1DCS4Y#3v4bSaA3iq3V7SuRQx4ppKaYKOgPHBk7x3NJJDkG8ys
* Queen Complex 

	>(https://queencomplex.net/gallery/?avia-element-paging=2) [NSFW]
	>"It's a cool style, and it has nice results.  Don't need to special reference anything, seems to work fine regardless of prompt."
	>Base Model:  Novel AI
	>Training set:  52 images at 4300 steps 0.00005 learning rate (images sourced from link above and cropped) 
	* https://cdn.discordapp.com/attachments/1029640494915006504/1030277229512491038/queencomplexstyle-2-4300.pt
* Raichiyo33 style hypernetwork. Not perfect but seems good enough.

	>Trained with captions from booru tags for compability with model + art by raichiyo33 in the beginning over NAI model.  Use "art by raichiyo33" in the begining of prompt to triggering.
	>Some useful tips: 
	>1) with tag "traditional media" produce more beautiful results
	>2) try to avoid too much negativ promts. I use only "bad anatomy, bad hands, lowres, worst quality, low quality, blurry, bad quality" even that seems too much. With many UC tags (especially with full NAI set of uc) it will produce almost generic NAI result. 
	>3) Use CLIP -2 (because its trained over NAI, ofc) 
	* LINK: https://mega.nz/file/VJ5H3KhL#Hkl8LIHRS5AiDIrytxPpht2ckO9oTpwZVgxbJy-vdcU
* Genshin Impact [SFW]

	>992 images, official art including some game assets
	>15k steps trained on nai
	>use "character name genshin impact" or "genshin impact)" for best results
	* LINK: https://files.catbox.moe/t4ooj6.pt 
* Gyokai-ZEN (aliases: Gyokai / Onono Imoko / shunin)  [NSFW / SFW] (For NAI) 

	>Includes training images
	>Training set: 329 Input images, Various steps included. Main model is 21,000 steps.
	>Training model: NAI-Full-Pruned.
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0. Lower strength is good for the overtrained model.
	>Emphasise the hypernet by using the prompt words "gyokai" or "art by gyokai".
	>
	>Note: the prompt words "color halftone" or "halftone" can be good at adding the little patterns in the shading often seen in onono imoko's style.
	>HOWEVER: This often results in a noise/grain which often can be fixed if you render at a resolution higher than 768x768 (with hi-res fix)
	>Omit these options from your prompt if the noise is too much in the image. Your outputs will be sharper and cleaner, but unfortunately less in the style.
	>
	>gyokai-zen-1.0 is 16k steps at 0.000005, then up to 21k steps at 0.0000005
	>gyokai-zen-1.0-16000 is a bit less trained (16k steps) and sometimes outputs cleaner at full strength.
	>gyokai-zen-1.0-overtrain is at 22k steps all at 0.000005. It can sometimes be a bit baked in.
	* Link: https://mega.nz/file/67AUDQ4K#8n4bzcxGGUgaAVy7wLXvVib0jhVjt2wPS-jsoCxcCus
* yapo (ヤポ) Art Style [NSFW / SFW] (Work on WD / NAI)

	>Training set: 51 Input images, 8000 Steps, 0.0000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with in style of yapo / yapo to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.4 to 0.8 
	>
	* Preview Link: https://imgur.com/a/r2sOV41
	* Download Link: https://anonfiles.com/N6B4d4D7y9/yapo_pt 
* Lycoris recoil chisato

	>Training set: 100 Input images, 21500 Steps, 0.000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with "cr-chisato"
	>Recommend Hypernetwork Strength rate: 0.4 to 0.8. clip skip : 1 Euler
	* Link: https://mega.nz/file/wlchDJpB#9nh5rIYtzRIhfLGvYeMrj6AOG-PcEx9JscTp4wXi-_E
* Liang Xing styled

	>Artstation: https://www.artstation.com/liangxing
	>20,000 steps at varying learning rates down to 0.000005, 449 training images.  Novel AI base.
	>Requires that you mention Liang Xing in some form as that was what I used in the training document.  "in the style of Liang Xing" as an example.
	* Examples: https://cdn.discordapp.com/attachments/1029640494915006504/1031785112246952007/Liang_Zing_D.Va_Outputs.zip
	* Link: https://cdn.discordapp.com/attachments/1029640494915006504/1031688311804276826/liangxingstyle-20000.pt
* アーニャ(anya)(SPY×FAMILY) [NSFW / SFW] (Work on WD / NAI)

	>Training set: 46 Input images, 20500 Steps, 0.00000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with Anya to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 0.9 
	>
	* Preview Link: https://imgur.com/a/ZbmIVRe
	* Download Link: https://anonfiles.com/ZdKej8D5ya/Anya_pt
* cp-lucy

	>Training set: 67 Input images, 21500 Steps, 0.000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with "cp-lucy" / clip skip : 1 
	>Recommend Hypernetwork Strength rate: 0.6 to 0.9
	* Link: https://mega.nz/file/lltzwaDI#_ZoJktJmCdBQZtYFNuuYnbnySIh5cxlOf9rYT73O2ig

* バッチ (azur bache) (アズールレーン) [NSFW / SFW] (Work on WD / NAI)

	>Training set: 55 Input images, 20050 Steps, 0.00000005 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with azur-bache to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0 
	* Link: https://anonfiles.com/Q84dw4D1y4/azur-bache_pt

* Ixy (by ixyanon):

	>Hypernetwork trained on ixy's style from 100 handpicked images from them, using split oversized images.
	>Trained in Nai-full-pruned
	>recommend using white pupils in the prompt, ixy for a greater effect of their style
	>Uses: will generally make your output more flat in shading, very good at frilly stuff, and white pupils of course
	>Grid examples located in the folder.
	* https://mega.nz/folder/yspgEBhQ#GLo7mBc1EH7RK7tQbtC68A 

* Blue Archives Azusa

	>Training set: 28 Input images, 20000 Steps, 5e-6:12000, 5e-7:30000 Learning rate.
	>Training model: NAI-Full-Prunced 
	>Start with ba-azusa to get a good result. 
	>Recommend Hypernetwork Strength rate: 0.6 to 1.0 clip skip : 1
	* Link: https://mega.nz/file/UslRnQbb#A37957mbty2PtnRKZVlikb8y8l0RuOqluebPsRXhFyg

* Makoto Shinkai HN

	>trained on a roughly ~150 images, 1,2,2,1 for 30,000 steps on NAI model, use "art by makotoshinkaiv2" to trigger it (experimental, it might not be that much different from base model but I have noticed that it improved composition when paired with the aesthetic gradient)
	>1007 frames from the entire 5 Centimeter Per Second (Byousoku 5 Centimeter) (2007) animovie by Makoto Shinkai
	* Dataset (for the aesthetic gradient and for general hypernetwork training/finetuning of a model if anyone else wants to attempt to get this style down.):
		* 1: https://cdn.discordapp.com/attachments/1022209206146838599/1033198526714363954/5_Centimeters_Per_Second.7z.001
		* 2: https://cdn.discordapp.com/attachments/1022209206146838599/1033198659321475184/5_Centimeters_Per_Second.7z.002
		* 3: https://cdn.discordapp.com/attachments/1022209206146838599/1033198735657803806/5_Centimeters_Per_Second.7z.003
	* Link: https://cdn.discordapp.com/attachments/1032726084149583965/1033200762085453874/makotoshinkaiv2.pt
	* Aesthetic Gradient: https://cdn.discordapp.com/attachments/1033147620966801609/1033196207478161488/makoto_shinkai.pt

* Hypernetwork based on the following prompts:
	* cervix, urethra, puffy pussy, fat_mons, spread_pussy, gaping_anus, prolapse, gape, gaping

	>This hypernetwork was made by me (IWillRemember) (IWillRemember#1912 on discord) if you have any questions you can find me here on discord!
	>
	>This hyper network was trained for 2000 steps at different learning rates on different batches of images (usually 25 images each batch)
	>
	>I suggest using an HYPERNETWORK STRENGTH OF 0,5 or maybe up to 0,8 since it's really strong ; it is compatible with almost all anime like models and it performs great even with semi realistic ones.
	>

	>The examples are made using the Nai model , but it works with ally , and any other anime based model if strength is adjusted acccordingly , also it COULD work with f111 and other models with the right prompts , to get really fat labia majora/minora , and/or gaping
	>
	* Link: https://mega.nz/file/pSN3mYoS#Q7e8tJWPSYGxdsyJMwhhtE5Jj8-A5e-sYZHhzbi3QAg
	* Examples: https://cdn.discordapp.com/attachments/1018623945739616346/1033541564603039845/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033542053444988938/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033544232310411284/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033550933151469688/unknown.png

* (reupload from the 4chan section) Hypernetwork trained on spacezin's art, 13 handpicked images flipped and used oversized crop, data is the rar in the link
	>by ixyanon
	>Trained in Nai-full-pruned, using swish activation method with dropout, 5e-6 training rate
	>recommend using spacezin in the prompt, lesser steps are included for testing and usage if 20k is too much
	>Uses: booba with covered nipples, sharp eyes and all that stuff you'd expect from him.
	>Aesthetic gradient embedding included, helps a lot to use, nails the style significantly further if you can find good settings...
	* Link: https://mega.nz/folder/Os5iBQDY#42xOYeZq08ZG0j8ds4uL2Q
* Hypernetwork trained on mikozin's art (reupload from 4chan section)
	>Trained in Nai-full-pruned, using swish activation method with dropout, 5e-6 training rate
	>placing mikozin in the prompt will make it have a stronger effect
	>has a number of effects, but mostly gives a very soft, painted style to the output image
	>Aesthetic gradient embedding included, not necessary but could be neat!
	>Data it was trained on included in the mega link, if you want something specific from the data it was trained on it'll help looking at the fileword txts
	* Download: https://mega.nz/folder/a0wxgQrR#OnJ0dK_F6_7WZiWscfb5hg

* yabuki_kentarou(1,1_relu_5e-5)-8750
	>Source image count: 75 (white-bg, hi-res, and hi-qual)
	>Dataset image count: 154 (split, 512x512)
	>Dataset stress test: excellent (LR 0.0005, 2000 steps)
	>Model: NAI [925997e9]
	>Layer: 1, 1
	>Learning rate: 0.00005
	>Steps: 8750
	* Download: https://anonfiles.com/H7RajcFby6/yabuki_kentarou_1_1_relu_5e-5_-8750_pt 

* namori(1,1_relu_5e-5)-9000.pt
	>Source image count: 50 (white-bg, hi-res, and hi-qual)
	>Dataset image count: 98 (split, 512x512)
	>Dataset stress test: excellent (LR 0.0005, 2000 steps)
	>Model: NAI [925997e9]
	>Layer: 1, 1
	>Learning rate: 0.00005
	>Steps: 9000
	>Preview: https://i.imgur.com/MEmvDCS.jpg
	>Download: https://anonfiles.com/n2W8rdF7y5/namori_1_1_relu_5e-5_-9000_pt

* Yordles:

	>Hey everyone , these hypernetworks were released by me (IWillRemember) (IWillRemember#1912 on discord) if you have any questions you can find me on discord!
	>
	>These hyper networks were trained for roughly 30000 steps at different learning rates on 80 images
	>
	>Yordles = to be use with an HYPERNETWORK STRENGHT OF 0,7
	>Yordles-FullSTR = to be useed with an HYPERNETWORK STRENGHT OF 1
	>
	>I suggest experimenting alot with prompts since they both give roughly the same results but i included both since some people might like the stronger version better.
	>
	>They were trained with NAI but they work best with Arena's Gape60 (i highly suggest using it)
	>
	>They are trained on the following tags: Yordle, tristana, lulu_(league_oflegends), poppy(league_oflegends), vex(league_oflegends), shortstack
	>I don't know why but discord modifies the tags for lulu, vex and poppy so read the readme txt !! 
	>
	>I highly suggest building around a specific character but you can make your own yordles too! try using different prompts to amplify the chances of getting a specific character .
	>
	>Example for Poppy : masterpiece, highest quality, digital art, colored skin, blue skin, white skin, 1girl, (yordle:1.1), purple eyes, (poppy(league_of_legends):1.1), shortstack, twintails, fang, red scarf, white armor, thighs, sitting, night, gradient background , grass , blonde hair , on back, :d
	>
	>I suggest not using negative prompts or use only the conditional ones like : monochrome, letterbox, ecc ecc
	>
	>Thank you for reading ! and happy yordle prompting !
	>
	>https://mega.nz/file/FCdiSIbI#ekOnlvox0ksEe1zzOQCFXgMJPkClEFPJFfGaAXv4rYc
	>
	>Examples:
	>https://cdn.discordapp.com/attachments/1023082871822503966/1037513553386684527/poppy.png
	>https://cdn.discordapp.com/attachments/1023082871822503966/1037513571355066448/lulu.png 
	>I don't know why but discord modifies the tags for lulu, vex and poppy so read the readme txt !!
	
Colored eyes:

	>Hey everyone , this hypernetwork was released by me (IWillRemember) (IWillRemember#1912 on discord) if you have any questions you can find me on discord!
	>
	>Did the Hn as a commission for a friend 😄
	>
	>I'm releasing an Hn to do better animation like glowing eyes, and a more slender face/upper body.
	>
	>The tags are : 
	>detailed eyes, 
	>(color) eyes  = ex: white eyes, blue eyes, etc etc
	>collarbone
	>
	>Trained for 12k steps on a 80 ish images dataset
	>
	>You can use the Hn with a str of 1 without any problem.
	>
	>Happy prompting!
	>
	>Example: https://media.discordapp.net/attachments/1023082871822503966/1038115846222008392/00162-3940698197-masterpiece_highest_quality_digital_art_1girl_on_back_detailed_eyes_perfect_face_detailed_face_breasts_white_hair_yell.png?width=648&height=702
	>
	>https://mega.nz/file/dHFwmaxS#NQhMPjT4TElPXX_YAZhTsFrQ36PDJhpWFm9BcHU_BO4 


### **Aesthetic Gradients**
Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

* Pussy improvements (Called an aesthetic embed, not sure if it's supposed to be here or in embeds): 
https://files.catbox.moe/l7gclr.pt

### **Polar Resources**
* Scat (??): https://files.catbox.moe/8hklc5.pt
* Horse (?): https://files.catbox.moe/idm0vf.pt
* MLP nsfw f16 f32 (might be pickled): https://drive.google.com/drive/folders/14JyQE36wYABH-0TSV_HBEsBJ3r8ZITrS?usp=sharing

### DEAD/MISSING
If you have one of these, please get it to me

Apparently there's a Google drive collection of downloads? (might be the korean site but mistyped)

Dreambooth:
* Anya Taylor-Joy: https://drive.google.com/drive/mobile/folders/1f0FI2Vtr0dNfxyCzsNkNau20JT9Kmgn-
	* https://www.reddit.com/r/StableDiffusion/comments/xx8p1p/anya_taylorjoy_model_link_in_comments/
* Fujimoto: https://huggingface.co/demibit/fujimoto_temp/tree/main
* Nardack: https://huggingface.co/Alice2O3/Nardack_dreambooth
	* Trained on artworks of Nardack on dreambooth with 60000 and 80000 steps
	* Dataset: https://huggingface.co/datasets/Alice2O3/Nardack_sd_Dataset

Embed:
* Omaru-polka: https://litter.catbox.moe/qfchu1.pt
* Sakimichan: https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8
* Deadflow (190k, "bitchass"(?)): https://litter.catbox.moe/03lqr6.pt
* Wagashi (12k, shitass(?)), no associated pic or replies so might be pickled: https://litter.catbox.moe/ktch8r.pt
* ex-penis-50000.pt and ex-penis-35000.pt
* Elira default-5500 16v 5500 steps
* Wiwa 4v 10000 steps

Hypernetworks:
* Chinese telegram (dead link): https://t.me/+H4EGgSS-WH8wYzBl
* HiRyS: https://litter.catbox.moe/rx8uv0.pt
* Huge training from KR site: https://mega.nz/folder/wKVAybab#oh42CNeYpnqr2s8IsUFtuQ
	* https://arca.live/b/aiart/60758880
* 焦茶 / cogecha hypernetwork, trained against NAI: https://mega.nz/folder/BLtkVIjC#RO6zQaAYCOIii8GnfT92dw
* 山北東 / northeast_mountain hypernetwork, trained against NAI: https://mega.nz/folder/RflGBS7R#88znRpu7YC1J1JYa9N-6_A
* Sayori (not sure if it's just a reupload of the one in the rentry): https://mega.nz/file/ArR0jRAS#3Q4mBmSd-kqFNVapkr52XMbDoSEBM2ko_-cDsWqXUbU

Datasets:
* expanded ie_(raarami) dataset: https://litter.catbox.moe/j4mpde.zip
* Toplessness: https://litter.catbox.moe/mttar5.zip
* https://gofile.io/d/R74OtT
* thanukiart (colored): https://www.dropbox.com/sh/mtf094lb5o61uvu/AABb2A83y4ws4-Rlc0lbbyHSa?dl=0

## Training
* Training guide for textual inversion/embedding and hypernetworks: https://pastebin.com/dqHZBpyA
* Hypernetwork Training by ixynetworkanon: https://rentry.org/hypernetwork4dumdums
* Training with e621 content: https://rentry.org/sd-e621-textual-inversion 
* Informal Model Training Guide: https://rentry.org/informal-training-guide
* Anon's guide: https://rentry.org/stmam
* Anon2's guide: https://rentry.org/983k3
	* Full Textual Inversion folder: https://files.catbox.moe/c6502c.7z
* Wiki: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Textual-Inversion
* Wiki 2: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#textual-inversion
>Use pics where:
>* Character doesn't blend with background and isn't overlapped by random stuff
>* Character is in different poses, angles, and backgrounds
>* Resolution is 512x512 (crop if it's not)
* Manually tagging the pictures allows for faster convergence than auto-tagging. More work is needed to see if deepdanbooru autotagging helps convergence
* Dreambooth on 8gb: https://github.com/huggingface/diffusers/tree/main/examples/dreambooth#training-on-a-8-gb-gpu
* Finetune diffusion: https://github.com/YaYaB/finetune-diffusion
	* Can train models locally
* Training guide: https://pastebin.com/xcFpp9Mr
* Reddit guide: https://www.reddit.com/r/StableDiffusion/comments/xzbc2h/guide_for_dreambooth_with_8gb_vram_under_windows/
* Reddit guide (2): https://www.reddit.com/r/StableDiffusion/comments/y389a5/how_do_you_train_dreambooth_locally/
* Dreambooth (8gb of vram if you have 25gb+ of ram and Windows 11): https://pastebin.com/0NHA5YTP
* Another 8gb Dreambooth: https://github.com/Ttl/diffusers/tree/dreambooth_deepspeed/examples/dreambooth#training-on-a-8-gb-gpu
* Dreambooth: https://rentry.org/dreambooth-shitguide
* Dreambooth: https://rentry.org/simple-db-elinas
* Dreambooth (Reddit): https://www.reddit.com/r/StableDiffusion/comments/ybxv7h/good_dreambooth_formula/
* Very in depth Hypernetworks guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670
* Runpod guide: https://rentry.org/runpod4dumdums
* Small guide written on hypernetwork activation functions.: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-3999660
* Dataset tag manager that can also load loss.: https://github.com/starik222/BooruDatasetTagManager
* Tips on hypernetwork layer structure: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-4010316
* Prompt template + info: https://github.com/victorchall/EveryDream-trainer
	* by anon: allows you to train multiple subjects quickly via labelling file names but it requires a normalization training set of random labelled images in order to preserve model integrity
* github + some documentation: https://github.com/cafeai/stable-textual-inversion-cafe
* Documentation: https://www.reddit.com/r/StableDiffusion/comments/wvzr7s/tutorial_fine_tuning_stable_diffusion_using_only/
* Guide on dreambooth training in comments: https://www.reddit.com/r/StableDiffusion/comments/yo05gy/cyberpunk_character_concepts/
* Dreambooth on 12gb no WSL: https://gist.github.com/geocine/e51fcc8511c91e4e3b257a0ebee938d0
* Very good beginner Twitter tutorial (read replies): https://twitter.com/divamgupta/status/1587452063721693185
* Japanese finetuning guide (?): https://note.com/kohya_ss/n/nbf7ce8d80f29
* Guide: https://github.com/nitrosocke/dreambooth-training-guide
* TI Guide: https://bennycheung.github.io/stable-diffusion-training-for-embeddings
* Faunanon guide: https://files.catbox.moe/vv8gwa.png
* Discussion about editing the training scripts for Hypernetworks: https://archived.moe/h/thread/6984678/#6984825
* Good training info: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-4022968
* TI Tutorial: https://lambdalabs.com/blog/how-to-fine-tune-stable-diffusion-how-we-made-the-text-to-pokemon-model-at-lambda
* Dreambooth info by Huggingface: https://huggingface.co/blog/dreambooth
* Dreambooth on 3080Ti 12g: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/4436

Train stable diffusion model with Diffusers, Hivemind and Pytorch Lightning: https://github.com/Mikubill/naifu-diffusion

Official pytoch implementation of one shot text to image generation via contrastive prompt-tuning AKA 1 image embedding training: https://github.com/7eu7d7/DreamArtist-stable-diffusion
Extension: https://github.com/7eu7d7/DreamArtist-sd-webui-extension
DreamArtist extension changes ui.py code in the modules directory, which might not be safe

* Site where you can train: https://www.astria.ai/
* Colab: https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb
* Colab 2: https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb
* Colab 3: https://github.com/XavierXiao/Dreambooth-Stable-Diffusion
* Colab 4 (fast): https://github.com/TheLastBen/fast-stable-diffusion
* colab 5: https://colab.research.google.com/drive/1Iy-xW9t1-OQWhb0hNxueGij8phCyluOh
* site?: drawanyone.com
* Colab for TI: https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb#scrollTo=Yl3r7A_3ASxm

Dreambooth colab with custom model (old, so might be outdated): https://desuarchive.org/g/thread/89140837/#89140895

Dreambooth thing in Japanese: https://note.com/kohya_ss/n/nee3ed1649fb6
* "Has aspect ratio bucketing, saving in fp16, etc."

GPU seems to determine training results (--low/med vram arg too)

Extension: https://github.com/d8ahazard/sd_dreambooth_extension
* Based on https://github.com/ShivamShrirao/diffusers/tree/main/examples/dreambooth

* Original dreambooth: https://github.com/JoePenna/Dreambooth-Stable-Diffusion

* Dreambooth gui: https://github.com/smy20011/dreambooth-gui
	* the app automatically chooses the best settings for your current VRAM

* **GUI helper for manual tagging and cropping: https://github.com/arenatemp/sd-tagging-helper/**

* Waifu Diffusion 1.4 Tagger (you can use to tag datasets): 
https://github.com/toriato/stable-diffusion-webui-wd14-tagger
https://mega.nz/file/ptA2jSSB#G4INKHQG2x2pGAVQBn-yd_U5dMgevGF8YYM9CR_R1SY

Image tagger helper: https://github.com/nub2927/image_tagger/

- subject filewords: https://pastebin.com/XRFhwXj8
- subject filewords but less emphasis on filewords: https://pastebin.com/LxZGkzj1
- subject filewords v3: https://pastebin.com/hL4nzEDW
- Character training text template: https://files.catbox.moe/wbat5x.txt

* Training on multiple people at once comparison: https://www.reddit.com/r/StableDiffusion/comments/yjd5y5/more_dreambooth_experiments_training_on_several/

* Extract keyframes from a video to use for training: https://github.com/Maurdekye/training-picker

* Huge collection of regularization images: https://huggingface.co/datasets/ProGamerGov/StableDiffusion-v1-5-Regularization-Images

* Embed vector, clip skip, and vae comparison: https://desuarchive.org/g/thread/89392239#89392432

* Hypernet comparison discussion: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2284

* Comparison of linear vs relu activation function on a number of different prompts, 12K steps at 5e-6.
	* https://files.catbox.moe/q8h8o3.png

* Clip skip comparison: https://files.catbox.moe/f94fhe.jpg

* Hypernetwork comparison: https://files.catbox.moe/q8h8o3.png

anything.ckpt comparisons
Old final-pruned: https://files.catbox.moe/i2zu0b.png (embed)
v3-pruned-fp16: https://files.catbox.moe/k1tvgy.png (embed)
v3-pruned-fp32: https://files.catbox.moe/cfmpu3.png (embed)
v3 full or whatever: https://files.catbox.moe/t9jn7y.png (embed)

* VAE: https://huggingface.co/stabilityai

* Image Scraper: https://github.com/mikf/gallery-dl
* Img scraper 2: https://github.com/Bionus/imgbrd-grabber

* Bulk resizer: https://www.birme.net/?target_width=512&target_height=512

* Model merging math: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/c250cb289c97fe303cef69064bf45899406f6a40#comments
* Old model merging: https://github.com/eyriewow/merge-models/
* Can use ckpt_merge script from https://github.com/bmaltais/dehydrate
	* python3 merge.py <path to model 1> <path to model2> --alpha <value between 0.0 and 1.0> --output <output filename>
From anon: For sigmoid/inverse sigmoid interpolation between modesl, add this code starting with line 38 of merge.py:
``` python
for key in tqdm(theta_0.keys(), desc="Stage 1/2"):
    if "model" in key and key in theta_1:
        # sigmoid
        alpha = alpha * alpha * (3 - (2 * alpha))
        theta_0[key] = theta_0[key] + ((theta_1[key] - theta_0[key]) * alpha)

        # inverse sigmoid
        #alpha = 0.5 - math.sin(math.asin(1.0 - 2.0 * alpha) / 3.0)
        #theta_0[key] = theta_0[key] + ((theta_1[key] - theta_0[key]) * alpha)

        # Weighted sum
        #theta_0[key] = ((1 - alpha) * theta_0[key]) + (alpha * theta_1[key])
```
	
* Model merge guide: https://rentry.org/lftbl
	* anon: The Checkpoint Merger tab in webui works well. It uses standard RAM not VRAM. As a general guide, you need 2x as much RAM as the total combined size of the models you need to load. 
* Supposedly empty ckpt to help with memory issues, might be pickled: https://easyupload.io/ggfxvc
* batch checkpoint merger: https://github.com/lodimasq/batch-checkpoint-merger

Supposedly how to append model data without merging by anon:
>x = (Final Dreambooth Model) - (Original Model)
>filter x for x >= (Some Threshold)
>out = (Model You Want To Merge It With) * (1 - M) + x * M

Model merging method that preserves weights: https://github.com/samuela/git-re-basin

Alternate model merging using https://github.com/bmaltais/dehydrate by anon:
>Dehydrate a model
>Hydrate it back into a dreambooth
>Merge with other stuff
>run `python ckpt_subtract.py dreamboothmodel.ckpt basemode.ckpt --output dreambooth_only` to dehydrate
>run 'python ckpt_add.py dreambooth_only target_model.ckpt --output output_model.ckpt' to hydrate it into another model.

3rd party git re basin: 
https://github.com/ogkalu2/Merge-Stable-Diffusion-models-without-distortion

Git rebasin pytorch: https://github.com/themrzmaster/git-re-basin-pytorch

* Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients

* Image aesthetic rating (?): https://github.com/waifu-diffusion/aesthetic

* 1 img TI: https://huggingface.co/lambdalabs/sd-image-variations-diffusers

* You can set a learning rate of "0.1:500, 0.01:1000, 0.001:10000" in textual inversion and it will follow the schedule

* Tip: combining natural language sentences and tags can create a better training

* Dreambooth on 2080ti 11GB (anon's guide): https://rentry.org/tfp6h

* Training a TI on 6gb (not sure if safe or even works, instructions by uploader anon): https://pastebin.com/iFwvy5Gy
	* Have xformers enabled.
	> This diff does 2 things.
	> 1. enables cross attention optimizations during TI training. Voldy disabled the optimizations during training because he said it gave him bad results. However, if you use the InvokeAI optimization or xformers after the xformers fix it does not give you bad results anymore.
	>This saves around 1.5GB vram with xformers
>
	>2. unloads vae from VRAM during training. This is done in hypernetworks, and idk why it wasn't in the code for TI. It doesn't break anything and doesn't make anything worse.
	>This saves around .2 GB VRAM
	>
	>After you apply this, turn on Move VAE and CLIP to RAM and Use cross attention optimizations while training

* By anon: 
>No idea if someone else will have a use for this but I needed to make it for myself since I can't get a hypernetwork trained regardless of what I do.
>
>https://mega.nz/file/LDwi1bab#xrGkqJ9m-IsqsTQNixVkeWrGw2HvmAr_fx9FxNhrrbY
>
>That link above is a spreadsheet where you paste the hypernetwork_loss.csv data into A1 cell (A2 is where numbers should start). Then you can use M1 to set how many epochs of the most recent data you want to use for the red trendline (green is the same length but starting before red). Outlayer % is if you want to filter out extreme points 100% means all points are considered for trendline 95% filters out top and bottom 5 etc. Basically you can use this to see where the training started fucking up. 

* Anon's best: 
>Creation:
>1,2,1
>Normalized Layers
>Dropout Enabled
>Swish
>XavierNormal (Not sure yet on this one. Normal or XavierUniform might be better)

Training:
>Rate: 5e-5:1000, 5e-6:5000, 5e-7:20000, 5e-8:100000
>Max Steps: 100,000

* Anon's Guide: https://rentry.org/zcspm

Vector guide by anon: https://rentry.org/dah4f

* Another training guide: https://www.reddit.com/r/stablediffusion/comments/y91luo

* Super simple embed guide by anon: Grab the high quality images, run them through the processor. Create an embedding called `art by {artist}. Then train that same embedding with your processed images and set the learning rate to the following: `0.1:500,0.05:1000,0.025:1500,0.001:2000,1e-5` Run it for 10k steps and you'll be good. No need for an entire hypernetwork.

* Has training info and a tutorial for Asagi Igawa, Edjit, and Rouge the Bat embeds (RealYiffingFar#4510): https://mega.nz/folder/5nIAnJaA#YMClwO8r7tR1zdJJeTfegA

* Anon's dreambooth guide:
for a character, steps ~1500-2000
checkpoint every 500 if you have the VRAM for it, else 99999 (ie: at the end), previews are shit don't even bother, 99999
learning rate: 0.000001-0.000005, I don't have a reason for it, default is probably fine.
instance prompt: [filewords], class prompt: 1girl, 20x regularisation images than training images, style matters, if you want anime get anime regularisation stuff.
advanced: auto-adjust, batch size: 2, 8bit adam, fp16, don't cache latents (noticeable speedup if you do cache), train text, train EMA, gradient checkpointing, 2 gradient accumulation

none of this is concrete stuff I do every time, I just roll whatever works. the single most important stuff is to ensure you never tag anything that isn't in an image after cropping.
reduce the tags as much as humanly possible, ie:

legwear, black thighhighs, long socks, long thighhighs, pantyhose, stockings, etc.

to just:

thighhighs

try add images that both do and do not use all of your tags. if you have a pic with thighhighs, include at least one without, otherwise the tag is meaningless
if your training cannot establish a positive and negative for each tag it's gonna struggle to recall those features
have makima with yellow eyes? include some girl with similar features but red or blue eyes, or just an entirely different girl that's been accurately tagged with the negatives you need
in this way you can distinguish between features and emphasise stuff.

### Datasets:
* ie_(raarami): https://mega.nz/folder/4GkVQCpL#Bg0wAxqXtHThtNDaz2c90w
	* Expanded (DEAD LINK): https://litter.catbox.moe/j4mpde.zip
* Toplessness: https://litter.catbox.moe/mttar5.zip
* Reine: https://files.catbox.moe/zv6n6q.zip
* Power: https://files.catbox.moe/wcpcbu.7z
* Baffu: https://files.catbox.moe/ejh5sg.7z
* tatsuki fujimoto: https://litter.catbox.moe/k09588.zip
* Butcha-U and Hypnosis: https://files.catbox.moe/9dv0cy.7z
* (By midnanon) tagged data sets with minimal effort and you're comfortable with C# (not sure if safe): https://pastebin.com/JmZFWCUK
	* Take whatever that produces and throw it into a duplicate detector.
	* Take whatever remains, filter out stuff you don't like or otherwise deviates too much.
	* I built up the midna dataset in about 10 minutes or so end to end.
	* You can customise tags on line 248.
* Anya: https://litter.catbox.moe/o5efml.zip
* Amelia Watson: https://files.catbox.moe/vrr2sl.zip
* Henreader (NSFW + loli): https://files.catbox.moe/e0e3nk.7z
* olga discordia from kuroinu: https://www.dropbox.com/s/wir30k9oj3uvnay/process%202.rar?dl=0
* Olga (another?): https://tstorage.info/a70vikp8waeg
* LeMat and Radom (guns): https://files.catbox.moe/zen22z.zip
* AK and SCAR (gun families): https://files.catbox.moe/7vo31t.zip
* Alkemanubis, Siina You Honzuki, Tatata: https://mega.nz/folder/sTV0EI6b#hGotLRXpotvmYxqfTb_KMw
* Onono imoko (NSFW + SFW, 300 cropped images): https://files.catbox.moe/dkn85w.zip
* Moona: https://files.catbox.moe/mmrf0v.rar
* Au'ra, a playable race from Final Fantasy (~100 imgs): https://mega.nz/folder/ZWcXCYpB#Zo-dHbp_u30iIz-LxLUGyA

Training dataset with aesthetic ratings: https://github.com/JD-P/simulacra-aesthetic-captions

## FAQ

Check out https://rentry.org/sdupdates and https://rentry.org/sdupdates2 for other questions
https://rentry.org/sdg_FAQ

**What's all the new stuff?**
>Check here to see if your question is answered: 
* https://scribe.froth.zone/m/global-identity?redirectUrl=https%3A%2F%2Fblog.novelai.net%2Fnovelai-improvements-on-stable-diffusion-e10d38db82ac
* https://blog.novelai.net/novelai-improvements-on-stable-diffusion-e10d38db82ac
* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki
* https://www.reddit.com/r/StableDiffusion
* https://github.com/AUTOMATIC1111/stable-diffusion-webui/search

**How do I set this up?**
>Refer to https://rentry.org/nai-speedrun (has the "Asuka test")
>Paperspace: https://rentry.org/865dy

**What's the "Hello Asuka" test?**
>It's a basic test to see if you're able to get a 1:1 recreation with NAI and have everything set up properly. Coined after asuka anon and his efforts to recreate 1:1 NAI before all the updates.

>Refer to
>* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
>* Very easy Asuka 1:1 Euler A: https://boards.4chan.org/h/thread/6893903#p6894236
>	

**What is pickling/getting pickled?**
>ckpt files and python files can execute code. Getting pickled is when these files execute malicious code that infect your computer with malware. It's a memey/funny way of saying you got hacked.
* Automatic1111's webui should unpickle the files for you, but that is only 1 line of defense: https://github.com/AUTOMATIC1111/stable-diffusion-webui/search?q=pickle&type=commits
* anon: there are checks but they can be disabled and you can still bypass with nested things
* https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle
* Pickle toolkit to extract the pickle information: https://docs.python.org/3/library/pickletools.html

* anon:
	pickle is a format that can load code objects
	originally the objects weren't sanitized, so remote code could run
	>by implementing __reduce__ in a class which instances we are going to pickle, we can give the pickling process a callable plus some arguments to run
	now __reduce__ is restricted (anything not NN related), the joke lives on as a meme

**I want to run this, but my computer is too bad. Is there any other way?**
Check out one of these (I did not used most of these, so they might be unsafe to use):
* (used and safe) Free online browser SD: https://huggingface.co/spaces/stabilityai/stable-diffusion
* https://promptart.labml.ai/playground
* https://novelai.manana.kr/
* https://boards.4channel.org/g/thread/89199040
* https://www.mage.space/
* (used and safe) https://github.com/TheLastBen/fast-stable-diffusion
	* https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb
* (used and safe) https://github.com/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb
* visualise.ai
	* Account required
	* Free unlimited 512x512/64 step runs
* img2img with stable horde: https://tinybots.net/artbot
* Free, GPU-less, powered by Stable Horde: https://dbzer0.itch.io/lucid-creations
* Free crowdsourced distributed cluster for Stable Diffusion (not sure how safe this is because of p2p): https://stablehorde.net/
* https://creator.nightcafe.studio/
* Artificy.com
* https://www.craiyon.com/
	* DALL·E mini
* http://aiart.house
* HF demo list: https://pastebin.com/9X1BPf8S
* Automatic1111 webui on SageMaker Studio Lab (free): https://github.com/Miraculix200/StableDiffusionUI_SageMakerSL/blob/main/StableDiffusionUI_SageMakerSL.ipynb
* notebook for running Dreambooth on SageMaker Studio Lab: https://github.com/Miraculix200/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion_SageMakerSL.ipynb
* anything.ckpt: https://colab.research.google.com/drive/1CkIPJrtXa3hlRsVk4NgpM637gmE3Ly5v
* Google Colab webui with 1.5/1.5 inpainting/VAE/waifu division (?): https://colab.research.google.com/drive/1VYmKX7eayuI8iTaCFKVHw9uxSkLo8Mde
* Site (didn't test): https://ai-images.net/
* SD 1.5: https://colab.research.google.com/drive/1kw3egmSn-KgWsikYvOMjJkVDsPLjEMzl
* https://dreamlike.art/
* https://pixelz.ai/
* Anything v3 + Gigachad models + a lot of other models + simple sd webui launcher that doesn't require an account/tokens: https://colab.research.google.com/github/Miraculix200/StableDiffusionUI_Colab/blob/main/StableDiffusionUI_Colab.ipynb#scrollTo=R-xAdMA5wxXd
* Paperspace (has a free plan): https://www.paperspace.com/pricing
* Old WD demo model: https://huggingface.co/spaces/hakurei/waifu-diffusion-demo
* Site, needs account, not free forever: https://getimg.ai/
* Deforum: https://colab.research.google.com/github/deforum-art/deforum-stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb

* Some gpu rental sites:
	* has free plan: https://colab.research.google.com/
	* https://vast.ai/
	* https://www.runpod.io/

**I have decided to get a new GPU for stable diffusion, are there any benchmarks for the relative performance of the GPUs
>Tom's Hardware recently released benchmarks for various GPUs https://www.tomshardware.com/news/stable-diffusion-gpu-benchmarks, note that if you plan to do fine-tuning of the models you may want to consider sticking to an NVIDIA GPU that has at least 16GB VRAM.
	
**How do I directly check AUTOMATIC1111's webui updates?**
>For a complete list of updates, go here: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commits/master

**What do I do if a new updates bricks/breaks my AUTOMATIC1111 webui installation?**
>Go to https://github.com/AUTOMATIC1111/stable-diffusion-webui/commits/master
>See when the change happened that broke your install
>Get the blue number on the right before the change
>Open a command line/git bash to where you usually git pull (the root of your install)
>'git checkout <blue number without these angled brackets>'
>to reset your install, use 'git checkout master'

> `git checkout .` will clean any changes you do

> Another Guide: https://rentry.org/git_retard

**What is...? (by anon)**
>What is a VAE?
Variational autoencoder, basically a "compressor" that can turn images into a smaller representation and then "decompress" them back to their original size. This is needed so you don't need tons of VRAM and processing power since the "diffusion" part is done in the smaller representation (I think). The newer SD 1.5 VAEs have been trained more and they can recreate some smaller details better.
>What is pruning?
Removing unnecessary data (anything that isn't needed for image generation) from the model so that it takes less disk space and fits more easily into your VRAM
>What is a pickle, not referring to the python file format? What is the meme surrounding this?
When the NAI model leaked people were scared that it might contain malicious code that could be executed when the model is loaded. People started making pickle memes because of the file format.
>Why is some stuff tagged as being 'dangerous', and why does the StableDiffusion WebUI have a 'safe-unpickle' flag? -- I'm stuck on pytorch 1.11 so I have to disable this
Safe unpickling checks the pickle's code library imports against an approved list. If it tried to import something that isn't on the list it won't load it. This doesn't necessarily mean it's dangerous but you should be cautious. Some stuff might be able to slip through and execute arbitrary code on your computer.
>Is the rentry stuff all written by one person or many?
There are many people maintaining different rentries.


**What's the difference between embeds, hypernetworks, and dreambooths? What should I train?**
Anon:
>I've tested a lot of the model modifications and here are my thoughts on them:
>embeds: these are tiny files which find the best representation of whatever you're training them on in the base model. By far the most flexible option and will have very good results if the goal is to group or emphasize things the model already understands
>hypernetworks: there are like instructions that slightly modify the result of the base model after each sampling step. They are quite powerful and work decently for everything I've tried (subjects, styles, compositions). The cons are they can't be easily combined like embeds. They are also harder to train because good parameters seem to vary wildly so a lot of experimentation is needed each time
>dreambooth: modifies part of the model itself and is the only method which actually teaches it something new. Fast and accurate results but the weights for generating adjacent stuff will get trashed. These are gigantic and have the same cons as embeds

## Misc


## Archives

[SDupdates 1](https://rentry.org/sdupdates) for v1 of sdupdates  
[SDupdates 2](https://rentry.org/sdupdates2) for v2 of sdupdates  
[SDump 1](https://rentry.org/sdump1) for stuff that's unsorted and/or I have no idea where to sort them  
[Soutdated 1](https://rentry.org/soutdated1) for stuff that's outdated
