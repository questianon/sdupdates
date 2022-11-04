```
Note: Don't forget to git pull to get a lot of new optimizations + updates. If SD breaks go backward in commits until it starts working again  

Instructions:  
>If on Windows:
1. Navigate to the webui directory through command prompt or git bash  
	a. Git bash: right click > git bash here  
	b. Command prompt: click the spot in the "url" between the folder and the down arrow and type "command prompt".  
	c. If you don't know how to do this, open command prompt, type `cd [path to stable-diffusion-webui]` (you can get this by right clicking the folder in the "url" or holding shift + right clicking the stable-diffusion-webui folder)  
2. `git pull`  
3. `pip install -r requirements.txt`  
>If on Linux:  
1. go to the webui directory
2. `source ./venv/bin/activate`  
	a. if this doesn't work, run `python -m venv venv` beforehand
3. `git pull`
4. `pip install -r requirements.txt`
```

>11/3
* More hypernetwork changes
* Unofficial MagicMix implementation with Stable Diffusion in PyTorch: https://github.com/cloneofsimo/magicmix
	* Good img2img with "geometric coherency and semantical layouts"
* Convert any model to Safetensors and open a PR (public repository?)
	* Safetensors are the unpicklable format
	* https://huggingface.co/spaces/safetensors/convert
	* https://github.com/huggingface/safetensors
* Zeipher AI f222 model release: https://ai.zeipher.com/#tabs-2
	* torrent: magnet:?xt=urn:btih:GR3IGMJDPJPW3B4WRT5B7SAN7CEBHWSZ&dn=f222&tr=http%3A%2F%2Ftracker.openbittorrent.com%2Fannounce
* NVIDIA new paper detailing a better model than imagen: https://deepimagination.cc/eDiffi/
	* You can "paint with words" (select part of the prompt and put it in the image)
	* conditioned on the T5 XXL text embeddings (higher quality, incorrect objects), CLIP image embeddings (style + inspiration) and CLIP text embeddings (correct objects, less detail)
	* has style transfer (control the style of the genreated sample using a reference style image)
	* has better text in the final image (look through paper)
	* issue would be running on consumer hardware since the T5 XXL embedding is 45 gb
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
