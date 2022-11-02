# SD RESOURCE GOLDMINE 2

->Version 2 of https://www.rentry.org/sdupdates. If something you want isn't here, it's probably in the other rentry<-

!!! danger Warnings: 

	1. Ckpts/hypernetworks/embeddings are ==not== interently safe as of right now. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet.

	2. Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps.

!!! Links are dying. If you happen to have a file listed in https://rentry.org/sdupdates#deadmissing or that's not on this list, please get it to me.

!!! note Changelog: added news and embeds+hypernets

!!! info There is now a github for this rentry: https://github.com/questianon/sdupdates. This should allow you to see changes across the different updates. There is also a WIP embedding directory here: https://github.com/questianon/sdupdates/blob/main/Embeddings.md

!!! note If you know how to do stuff in markdown and html/can make a webpage easily/want to contribute in any way, contact me 

### Quicklinks: 
* News: https://rentry.org/sdupdates2#newsfeed
* Prompting: https://rentry.org/sdupdates2#prompting
* Models, Embeddings, and Hypernetworks: https://rentry.org/sdupdates2#models-embeddings-and-hypernetworks
	* Models: https://rentry.org/sdupdates2#models
	* Dreambooth Models: https://rentry.org/sdupdates2#dreambooth-models
	* Embeddings: https://rentry.org/sdupdates2#embeddings
	* Hypernetworks: https://rentry.org/sdupdates2#hypernetworks
	* Aesthetic Gradients: https://rentry.org/sdupdates2#aesthetic-gradients
	* Models, embeds, and hypernetworks that might be sus: https://rentry.org/sdupdates2#polar-resources
	* DEAD/MISSING: https://rentry.org/sdupdates2#deadmissing
* Training: https://rentry.org/sdupdates2#training
	* Datasets: https://rentry.org/sdupdates2#datasets
* FAQ: https://rentry.org/sdupdates2#common-questions-ctrlcmd-f
* Link Dump: https://rentry.org/sdupdates2#rentrys-link-dump-will-sort
* Hall of Fame: https://rentry.org/sdupdates2#hall-of-fame
* Miscellaneous: https://rentry.org/sdupdates2#misc
* Github: https://github.com/questianon/sdupdates/
* Contact: https://rentry.org/sdupdates2#contact

## NEWSFEED
!!! note Don't forget to git pull to get a lot of new optimizations + updates, if SD breaks go backward in commits until it starts working again
	Instructions:
	* If on Windows:
		1. go to the webui directory
		2. ```git pull```
		3. ```pip -r install requirements.txt```
	* If on Linux: 
		1. go to the webui directory
		2. ```source ./venv/bin/activate```
			a. if this doesn't work, run ```python -m venv venv``` beforehand
		3. ```git pull```
		4. ```pip -r install requirements.txt```

>11/1
* SD Upscale broken on latest git pull: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/4104
	* Seems to affect some other parts of webui too
* PR for hypernetwork resume fix: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3975
* Dreambooth will probably not be integrated into AUTOMATIC1111's webui normally. It's likely to be turned into an extension: https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/3995#issuecomment-1298741868
* MMD + NAI showcase (not sure what UC 3d is): https://twitter.com/8co28/status/1587238661090791424?t=KJmJhfkG6GPcxS5P6fADgw&s=19 
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

## Prompting
Google Docs with a prompt list/ranking/general info for waifu creation: 
https://docs.google.com/document/d/1Vw-OCUKNJHKZi7chUtjpDEIus112XBVSYHIATKi1q7s/edit?usp=sharing
Anon's prompt collection: https://mega.nz/folder/VHwF1Yga#sJhxeTuPKODgpN5h1ALTQg
Tag effects on img: https://pastebin.com/GurXf9a4
* Anon says that "8k, 4k, (highres:1.1), best quality, (masterpiece:1.3)" leads to nice details

Japanese prompt collection: http://yaraon-blog.com/archives/225884
GREAT CHINESE TOME OF PROMPTING KNOWLEDGE AND WISDOM 101 GUIDE: https://docs.qq.com/doc/DWHl3am5Zb05QbGVs
* Site: https://aiguidebook.top/
* Backup: https://www105.zippyshare.com/v/lUYn1pXB/file.html
* translated + download: https://mega.nz/folder/MssgiRoT#enJklumlGk1KDEY_2o-ViA
* another backup? https://note.com/sa1p/n/ne71c846326ac

GREAT CHINESE SCROLLS OF PROMPTING ON 1.5: HEIGHTENED LEVELS OF KNOWLEDGE AND WISDOM 101: https://docs.qq.com/doc/DWGh4QnZBVlJYRkly
GREAT CHINESE ENCYCLOPEDIA OF PROMPTING ON GENERAL KNOWLEDGE: SPOOKY EDITION: https://docs.qq.com/doc/DWEpNdERNbnBRZWNL
GREAT JAPANESE TOME OF MASTERMINDING ANIME PROMPTS AND IMAGINATIVE AI MACHINATIONS 101 GUIDE https://p1atdev.notion.site/021f27001f37435aacf3c84f2bc093b5?p=f9d8c61c4ed8471a9ca0d701d80f9e28
* author: https://twitter.com/p1atdev_art/
Japenese wiki: https://seesaawiki.jp/nai_ch/d/

Database of prompts: https://publicprompts.art/
* Discord: https://discord.com/invite/jvQJFFFx26

Krea AI prompt database: https://github.com/krea-ai/open-prompts
Prompt search: https://www.ptsearch.info/home/
Another search: http://novelai.io/
4chan prompt search: https://desuarchive.org/g/search/text/masterpiece%20high%20quality/

Japanese prompt generator: https://magic-generator.herokuapp.com/
Build your prompt (chinese): https://tags.novelai.dev/
NAI Prompts: https://seesaawiki.jp/nai_ch/d/%c8%c7%b8%a2%a5%ad%a5%e3%a5%e9%ba%c6%b8%bd/%a5%a2%a5%cb%a5%e1%b7%cf

Japanese wiki: https://seesaawiki.jp/nai_ch/
Korean wiki: https://arca.live/b/aiart/60392904
Korean wiki 2: https://arca.live/b/aiart/60466181

Multilingual info by anon: 
>CLIP can't really understand Chinese (or anything other than english). (maybe some of the characters are bond to certain concept for the reason I don't know)
>But some of emoji and Chinese/Japanese character is meaningful for CLIP. Like イカ, which means squid in Japanese. You will get something like squid if you put these character in prompt. 
>anon2: yeah，because the CLIP can not understand Chinese , so here the “natural language” I should translate some depiction to English.
Multilingual study: https://jalonso.notion.site/Stable-Diffusion-Language-Comprehension-5209abc77a4f4f999ec6c9b4a48a9ca2

NAI to webui translator (not 100% accurate): https://seesaawiki.jp/nai_ch/d/%a5%d7%a5%ed%a5%f3%a5%d7%a5%c8%ca%d1%b4%b9

Tip Dump: https://rentry.org/robs-novel-ai-tips
Tips: https://github.com/TravelingRobot/NAI_Community_Research/wiki/NAI-Diffusion:-Various-Tips-&-Tricks
Info dump of tips: https://rentry.org/Learnings
Outdated guide: https://rentry.co/8vaaa
Tip for more photorealism: https://www.reddit.com/r/StableDiffusion/comments/yhn6xx/comment/iuf1uxl/
* TLDR: add noise to your img before img2img

SD 1.4 vs 1.5: https://postimg.cc/gallery/mhvWsnx
Model merge comparisons: https://files.catbox.moe/rcxqsi.png
Some sampler comparisons: https://www.reddit.com/r/StableDiffusion/comments/xmwcrx/a_comparison_between_8_samplers_for_5_different/

Deep Danbooru: https://github.com/KichangKim/DeepDanbooru
Demo: https://huggingface.co/spaces/hysts/DeepDanbooru

Embedding tester: https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer

Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

Euler vs. Euler A: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017#discussioncomment-4021588
* Euler: https://cdn.discordapp.com/attachments/1036718343140409354/1036719238607540296/euler.gif
* Euler A: https://cdn.discordapp.com/attachments/1036718343140409354/1036719239018590249/euler_a.gif

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
UMI AI:
* free
* SFW and NSFW
* Goal: ultimate char-gen 
* Tutorial: https://www.patreon.com/posts/umi-ai-official-73544634
* Why you should use it: https://www.patreon.com/posts/umi-ai-ultimate-73560593
* Examples: 
	* Straddling Sluts random prompt:
	> https://i.imgur.com/eDpRdjj.png
	> https://i.imgur.com/1mZ0u6q.png
	> https://i.imgur.com/cOjwAMm.png
	* Cocksucking Cunts prompt.
	> https://i.imgur.com/GdVCZuV.png
	> https://i.imgur.com/i5WTTB5.png
	> https://i.imgur.com/xj3mp8V.png
	* Bedded Bitches prompt.
	> https://i.imgur.com/urwxn6S.png
	> https://i.imgur.com/5gfC1oP.png
	* Oneshot H-Manga prompt.
	> https://i.imgur.com/oBec2uO.jpeg
	> https://i.imgur.com/UiWYTgr.jpeg
	> https://i.imgur.com/GuhU0Kz.jpeg
* Discord: https://discord.gg/9K7j7DTfG2
* Author is looking for help filling out and improving wildcards
	* Ex: https://cdn.discordapp.com/attachments/1032201089929453578/1034546970179674122/Popular_Female_Characters.txt
	* Author: Klokinator#0278
	* Looking for wildcards with traits and tags of characters
* Planned updates
	* Code will get cleaned up
	* the 'species' are rudimentary rn but stuff like 'superior slimegirls' are the direction I want to head with species moving forward 
	* the genders are still unigender, but I'll be separating m/f very soon
	* and finally, I just need to add shitloads more content and scenarios
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
* Wildcards on steroids
* Powerful scripting language 
* Can create templates out of booru tags
* Can make shortcodes
* "You can pull text from files, set up your own variables, process text through conditional functions, and so much more "

Ideas for when you have none: https://pentoprint.org/first-line-generator/

PaintHua.com - New GUI focusing on Inpainting and Outpainting
* https://www.reddit.com/r/StableDiffusion/comments/ygp0iv/painthuacom_new_gui_focusing_on_inpainting_and/

I didn't check the safety of these plugins, but they're open source, so you can check them yourself
Photoshop/Krita plugin (free): https://internationaltd.github.io/defuser/ (kinda new and currently only 2 stars on github)
* https://github.com/internationalTD/defuser

Photoshop: https://github.com/Invary/IvyPhotoshopDiffusion
Photoshop plugin (paid, not open source): https://www.flyingdog.de/sd/
Krita plugins (free): 
* https://github.com/sddebz/stable-diffusion-krita-plugin (listed in the OP, outdated? dead?)
* https://github.com/Interpause/auto-sd-krita (a fork from above, more improvement)
* https://www.flyingdog.de/sd/en/ (https://github.com/imperator-maximus/stable-diffusion-krita)

GIMP:
https://github.com/blueturtleai/gimp-stable-diffusion

Blender:
https://github.com/carson-katri/dream-textures
https://github.com/benrugg/AI-Render


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

Giffusion tutorial:
``` python 
>git clone https://github.com/megvii-research/ECCV2022-RIFE
this is my git diff on requirements.txt to work alone side webui python environment
>-torch==1.6.0
>+torch==1.11.0
>-torchvision==0.7.0
>+torchvision==0.12.0
pip3 install -r requirements.txt
the most important part
>download the pretrained HD models and copy them into the same folder as inference_video.py
get ffmpeg for your OS (if you dont have ffmpeg it is good to have besides this app)
>https://ffmpeg.org/download.html
after this need to make sure ffmpeg.exe is in your PATH variable
then i typed
>python inference_video.py --exp=1 --video=1666410530347641.mp4 --fps=60
and it created the mp4 you see (i converted it into webm with this command)
>ffmpeg.exe -i 1666410530347641.mp4 1666410530347641.webm
Example: https://i.4cdn.org/h/1666414810239191.webm
```

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

Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients
Aesthetic Scorer: https://github.com/tsngo/stable-diffusion-webui-aesthetic-image-scorer
Autocomplete Tags: https://github.com/DominikDoom/a1111-sd-webui-tagcomplete
Prompt Randomizer: https://github.com/adieyal/sd-dynamic-prompting
Wildcards: https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards/
Wildcard script + collection of wildcards: https://app.radicle.xyz/seeds/pine.radicle.garden/rad:git:hnrkcfpnw9hd5jb45b6qsqbr97eqcffjm7sby

Clip interrogator: https://colab.research.google.com/github/pharmapsychotic/clip-interrogator/blob/main/clip_interrogator.ipynb
2: https://github.com/pharmapsychotic/clip-interrogator

**VAEs**

Tutorial + how to use on ALL models (applies for the NAI vae too): https://www.reddit.com/r/StableDiffusion/comments/yaknek/you_can_use_the_new_vae_on_old_models_as_well_for/

* SD 1.4 Anime styled: https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime.ckpt
	* https://twitter.com/haruu1367/status/1579286947519864833
* Stability AI: https://huggingface.co/stabilityai

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

Wildcards: 
* Huge collection that works: https://danbooru.donmai.us/wiki_pages/tag_groups
* https://desuarchive.org/g/thread/89006003#89007479
* https://rentry.org/sdWildcardLists
* Guide (ish): https://is2.4chan.org/h/1665343016289442.png 
* A few wildcards: https://cdn.lewd.host/EtbKpD8C.zip
* https://github.com/Lopyter/stable-soup-prompts/tree/main/wildcards
* https://github.com/Lopyter/sd-artists-wildcards 
	* Allows you to split up the artists.csv from Automatic by category
* Another wildcard script: https://raw.githubusercontent.com/adieyal/sd-dynamic-prompting/main/dynamic_prompting.py
* wildcardNames.txt generation script: https://files.catbox.moe/c1c4rx.py
* Another script: https://files.catbox.moe/hvly0p.rar
* Script: https://gist.github.com/h-a-te/30f4a51afff2564b0cfbdf1e490e9187
* UMI AI: https://www.patreon.com/posts/umi-ai-official-73544634

* Dump: 
	* faces https://rentry.org/pu8z5
	* focus https://rentry.org/rc3dp
	* poses https://rentry.org/hkuuk
	* times https://rentry.org/izc4u
	* views https://rentry.org/pv72o
	* Clothing: https://pastebin.com/EyghiB2F
* Another dump: https://github.com/jtkelm2/stable-diffusion-webui-1/tree/master/scripts/wildcards
	* info by creator: https://github.com/jtkelm2/stable-diffusion-webui-1/blob/main/scripts/wildcards.py
* Big NAI Wildcard List: https://rentry.org/NAIwildcards
* 316 colors list: https://pastebin.com/s4tqKB8r
* 82 colors list: https://pastebin.com/kiSEViGA
* Backgrounds: https://pastebin.com/FCybuqYW
* More clothing: https://pastebin.com/DrkG1MRw
* Dump: https://www.dropbox.com/s/oa451lozzgo7sbl/wildcards.zip?dl=1
* 483 txt files, huge dump (for Danbooru trained models): https://files.catbox.moe/ipqljx.zip
	* old 329 version: https://files.catbox.moe/qy6vaf.zip
	* old 314 version: https://files.catbox.moe/11s1tn.zip
* Styles: https://pastebin.com/71HTfsML
* Word list (small): https://cdn.lewd.host/EtbKpD8C.zip 
* Emotions/expressions: https://pastebin.com/VVnH2b83
* Clothing: https://pastebin.com/cXxN1fJw
* More clothing: https://files.catbox.moe/88s7bf.zip
* Cum: https://rentry.org/hoom5
* Dump: https://www.mediafire.com/file/iceamfawqhn5kvu/wildcards.zip/file
* Locations: https://pastebin.com/R6ugwd2m
* Clothing/outfits: https://pastebin.com/Xhhnyfvj
* Locations: https://pastebin.com/uyDJMnvC
* Clothes: https://pastebin.com/HaL3rW3j
* Color (has nouns): https://pastebin.com/GTAaLLnm
* Dump: https://files.catbox.moe/qyybik.zip
* Artists: https://pastebin.com/1HpNRRJU
* Animals: https://pastebin.com/aM4PJ2YY
* Food: https://pastebin.com/taFkYwt9
* Characters: https://files.catbox.moe/xe9qj7.txt
* Backgrounds: https://pastebin.com/gVue2q8g 
* WIP random h-manga scene generator: https://files.catbox.moe/ukah7u.jpg
* Collection from https://rentry.org/NAIwildcards: https://files.catbox.moe/s7expb.7z
* Outfits: https://files.catbox.moe/y75qda.txt
* Collection: https://cdn.lewd.host/4Ql5bhQD.7z
* Settings + Minerals: https://pastebin.com/9iznuYvQ
* Hairstyles: https://pastebin.com/X39Kzxh7
* Hairstyles 2: https://pastebin.com/bRWu1Xvv
* subject filewords: https://pastebin.com/XRFhwXj8
* subject filewords but less emphasis on filewords: https://pastebin.com/LxZGkzj1
* subject filewords v3: https://pastebin.com/hL4nzEDW
* Danbooru Poses: https://pastebin.com/RgerA8Ry
* Character training text template: https://files.catbox.moe/wbat5x.txt
* Outfits: https://pastebin.com/Z9aHVpEy
* Danbooru tag group wildcard dump organized into folders: https://files.catbox.moe/hz5mom.zip
	* by uploader anon: "I recommend using Dynamic Prompting rather than the normal Wildcards extension. It does everything the Wildcards extension does and then some, * being a thing is especially great and so is |"
* Poses: https://rentry.org/m9dz6

Wildcard extension: https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards/

**Artist Comparisons (may or may not work with NAI):**
* SD 1.5 artists (might lag your pc): https://docs.google.com/spreadsheets/d/1SRqJ7F_6yHVSOeCi3U82aA448TqEGrUlRrLLZ51abLg/htmlview#
* pre-modern art: https://www.artrenewal.org/Museum/Search#/
* SD 1.4 artists: https://rentry.org/artists_sd-v1-4
* Link list: https://pastebin.com/HD7D6pnh
* Artist comparison grids: https://files.catbox.moe/y6bff0.rar
* Artist Comparison: https://reddit.com/r/NovelAi/comments/y879x1/i_made_an_experiment_with_different_artists_here/
* Site: https://sdartists.app/
* Comparison: https://imgur.com/a/hTEUmd9
* Comparison: https://proximacentaurib.notion.site/e28a4f8d97724f14a784a538b8589e7d?v=ab624266c6a44413b42a6c57a41d828c
* Comparison: https://imgur.com/a/ADPHh9q
* List: https://mpost.io/midjourney-and-dall-e-artist-styles-dump-with-examples-130-famous-ai-painting-techniques/
* List: https://arthive.com/artists
* Extension: https://github.com/yfszzx/stable-diffusion-webui-inspiration
	* https://huggingface.co/datasets/yfszzx/inspiration

* Huge comparison of artists (3gb, 90x90 different artist combinations on untampered WD v1.3.)
	* big image: https://mega.nz/file/ACtigCpD#f9zP9h1AU_0_4DPsBnvdhnUYdQmIJMb4pyc6PJ4J-FU
	* individual images: https://mega.nz/file/YPsT1TDJ#XAayj1jYmRSIyzJ-A1pKB8HyxeDib4a4xuo2lxMx7oA

* Huge tested list: https://proximacentaurib.notion.site/e28a4f8d97724f14a784a538b8589e7d?v=42948fd8f45c4d47a0edfc4b78937474
* artists and themes: https://dict.latentspace.observer/
* SD 1.5 artist study: https://docs.google.com/spreadsheets/d/1SRqJ7F_6yHVSOeCi3U82aA448TqEGrUlRrLLZ51abLg/edit#gid=2005893444
* Artist comparisons for NAI: https://www.reddit.com/r/NovelAi/comments/y879x1/i_made_an_experiment_with_different_artists_here/
	* https://preview.redd.it/llok0ydfhsu91.jpg?width=640&crop=smart&auto=webp&s=e0ae2e38f9b97d10604a5c72e8c111cb184068e6

* Artist rankings: https://www.urania.ai/top-sd-artists
* Some comparisons:
	* https://imgur.com/a/ADPHh9q
	* https://imgur.com/a/zzXqLPc
	* https://imgur.com/a/TDGBAlc

Anon's list of comparisons:
* Stable Diffusion v1.5, Waifu Diffusion v1.3, Trinart it4
> https://imgur.com/a/ADPHh9q

* Berry Mix, CLIP 2:
> https://imgur.com/a/zzXqLPc

* Berry Mix, CLIP 1:
> https://imgur.com/a/TDGBAlc

* Artist + Artist, WD v1.3 (incomplete):
> https://mega.nz/file/ACtigCpD#f9zP9h1AU_0_4DPsBnvdhnUYdQmIJMb4pyc6PJ4J-FU

**Creating fake animes:**
* https://rentry.org/animedoesnotexist

##  Models, Embeddings, and Hypernetworks

### **Models***

**Berrymix Recipe**
Rentry: https://rentry.org/berrymix
>Make sure you have all the models needed, Novel Ai, Stable Diffusion 1.4, Zeipher F111, and r34_e4. All but Novel Ai can be downloaded from HERE
>Open the Checkpoint Merger tab in the web ui
>Set the Primary Model (A) to Novel Ai
>Set the Secondary Model (B) to Zeipher F111
>Set the Tertiary Model (C) to Stable Diffusion 1.4
>Enter in a name that you will recognize
>Set the Multiplier (M) slider all the way to the right, at "1"
>Select "Add Difference"
>Click "Run" and wait for the process to complete
>Now set the Primary Model (A) to the new checkpoint you just made (Close the cmd and restart the webui, then refresh the web page if you have issues with the new checkpoint not being an option in the drop down)
>Set the Secondary Model (B) to r34_e4
>Ignore Tertiary Model (C) (I've tested it, it wont change anything)
>Enter in the name of the final mix, something like "Berry's Mix" ;)
>Set Multiplier (M) to "0.25"
>Select "Weighted Sum"
>Click "Run" and wait for the process to complete
>Restart the Web Ui and reload the page just to be safe
>At the top left of the web page click the "Stable Diffusion Checkpoint" drop down and select the Berry's Mix.ckpt (or whatever you named it) it should have the hash "[c7d3154b]"

* Berry + Novelai VAE (Might be malicious): https://mega.nz/folder/8HUikarD#epAOm3l2hltC_s_oiSC9dg
* Another berry + vae: https://anonfiles.com/Rdq7j7F0ye/Berry_zip
	* https://pastebin.com/h4gY7tGB

* Dump of ckpt merges, might be pickled, uploader anon says to download at your own risk, could also be a fed bait or something: https://droptext.cc/bfxwb

**Fruit Salad Mix (might not be worth it to make)**
>Fruit Salad Guide
>
>Recipe for the "Fruit Salad" checkpoint:
>Make sure you have all the models needed, Novel Ai, Stable Diffusion 1.5, Trinart-11500, Zeipher F111, r34_e4, Gape_60 and Yiffy.
>Open the Checkpoint Merger tab in the web ui
>Set the Primary Model (A) to Novel Ai
>Set the Secondary Model (B) to Yiffy e18
>Set the Tertiary Model (C) to Stable Diffusion 1.4
>Enter in a name that you will recognize
>Set the Multiplier (M) slider to the left, at "0.1698765"
>Select "Add Difference"
>Click "Run" and wait for the process to complete
>Now set the Primary Model (A) to the new checkpoint you just made (Close the cmd and restart the webui, then refresh the web page if you have issues with the new checkpoint not being an option in the drop down)
>Set the Secondary Model (B) to r34_e4
>Set the Tertiary Model (C) to Zeipher F111 (I've tested it, it changes EVERYTHING)
>Set Multiplier (M) to "0.56565656"
>Select "Weighted Sum"
>Click "Run" and wait for the process to complete
>Restart the Web Ui and reload the page just to be safe
>Now download a previous version of WebUI, which still contains the "Inverse Sigmoid" option for checkpoint merger.
>Now set the Primary Model (A) to the new checkpoint you just made
>Set the Secondary Model (B) to Trinart-11500
>Set Multiplier (M) to "0.768932"
>Select "Inverse Sigmoid"(this is kind of like Sigmoid but inverted)
>Click "Run" and wait for the process to complete
>Restart the Web Ui and reload the page just to be safe
>Now set the Primary Model (A) to the new checkpoint you just made.
>Set the Secondary Model (B) to SD 1.5
>Set the Tertiary Model (C) to Gape_60
>Set the name of the final mix to something you will remember, like "Fruit's Salad" ;)
>Set Multiplier (M) to "1"
>Select "Weighted Sum"
>Click "Run" and wait for the process to complete
>Restart the Web Ui and reload the page just to be safe
>At the top left of the web page click the "Stable Diffusion Checkpoint" drop down and select the Fruit's Salad.ckpt (or whatever you named it) 
* Older files you need uploaded by anon (which means it might be pickled): https://codeload.github.com/AUTOMATIC1111/stable-diffusion-webui/zip/f7c787eb7c295c27439f4fbdf78c26b8389560be

* NAI + hypernetworks (uploaded by UMI AI dev, I didn't audit the files myself for changes/pickles): 
	* DL 1: https://anonfiles.com/U5Acl7F0y2/Novel_AI_Hypernetworks_zip
	* DL 2: https://pixeldrain.com/u/FMJ4TQbM
	* https://cdn.discordapp.com/attachments/1034551880220672181/1036386279597822082/unknown.png
	* https://cdn.discordapp.com/attachments/1034551880220672181/1036386279207731262/unknown.png
	* https://cdn.discordapp.com/attachments/1034551880220672181/1036386278813474857/unknown.png

* Scarlett's Mix (good at cute witches): https://rentry.org/scarlett_mix

* Mega mixing guide (has a different berry mix): https://rentry.org/lftbl

### **Dreambooth Models:**
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
* Modern Disney style (modi, mo-di): https://huggingface.co/nitrosocke/mo-di-diffusion
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
* Pixel Art Sprite Sheet: https://huggingface.co/Onodofthenorth/SD_PixelArt_SpriteSheet_Generator
	* 4 different angles
	* Examples + Reddit post: https://www.reddit.com/r/StableDiffusion/comments/yj1kbi/ive_trained_a_new_model_to_output_pixel_art/

### **Embeddings**
!!! info If an embedding is >80mb, I mislabeled it and it's a hypernetwork

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

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
	* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948
	* Original: https://arca.live/b/hypernetworks/60930993
	* **Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw**
* Large Vtuber collection dump (not sure if pickled, even linker anon said to be careful, but a big list anyway): https://rentry.org/EmbedList
* Waifu Diffusion collection: https://gitlab.com/cattoroboto/waifu-diffusion-embeds

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

* Henreader embedding, all 311 imgs on gelbooru, trained on NAI: https://files.catbox.moe/gr3hu7.pt
	* https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A/folder/Go9CRRoC
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
* Nenechi embedding: https://mega.nz/folder/E0lmSCrb#Eaf3wr4ZdhI2oettRW4jtQ
* Touhou Fumo embedding (57 epochs): https://birchlabs.co.uk/share/textual-inversion/fumo.cpu.pt
	* https://twitter.com/Birchlabs/status/1579937213617680385
* Abigail from Great Pretender (24k steps): https://workupload.com/file/z6dQQC8hWzr 
* Naoki Ikushima (40k steps): https://files.catbox.moe/u88qu5.pt
* Abmayo: https://files.catbox.moe/rzep6d.pt
* Gigachad: https://easyupload.io/nlha2m
* Kusada Souta (95k steps): https://files.catbox.moe/k78y65.pt
* Yohan1754: https://files.catbox.moe/3vkg2o.pt
* Repo for some: https://git.evulid.cc/wasted-raincoat/Textual-Inversion-Embeds/src/branch/master/simonstalenhag
* automatic's secret embedding list: https://gitlab.com/16777216c/stable-diffusion-embeddings
* Niro: https://take-me-to.space/WKRY9IE.pt
* Kaneko Kazuma (Kazuma Kaneko): https://litter.catbox.moe/6glsh1.pt
* Senran Kagura (850 CGs, deepdanbooru tags, 0.005 learning rate, 768x768, 3000 iterations): https://files.catbox.moe/jwiy8u.zip
* Abmono (14.7k): https://www.mediafire.com/file/id2uh4gkzvavsbc/abmono-14700.pt/file
* DEAD LINK Deadflow (190k, "bitchass"(?)): https://litter.catbox.moe/03lqr6.pt
* Aroma Sensei (86k, "aroma"): https://files.catbox.moe/wlylr6.pt
* Zun (75:25 weighted sum NAI full:WD): https://www.fluffyboys.moe/sd/zunstyle.pt
* Kurisu Mario (20k): https://files.catbox.moe/r7puqx.pt
	* creator anon: "I suggest using him for the first 40% of steps so that the AI draws the body in his style, but it's up to you. Also, put speech_bubble in the negative prompt, since the training data had them"
* ATDAN (33k): https://files.catbox.moe/8qoag3.pt
	* Mirror: https://litter.catbox.moe/6valfk.pt
* Valorant (25k): https://files.catbox.moe/n7i9lq.pt
	* Mirror: https://files.catbox.moe/n7i9lq.pt
* Takifumi (40k, 153 imgs): https://freeufopictures.com/ai/embeddings/takafumi/
* 40hara (228 imgs, 70k, 421 after processing): https://freeufopictures.com/ai/embeddings/40hara/
* Tsurai (160k, NAI): https://mega.nz/file/bBYjjRoY#88o-WcBXOidEwp-QperGzEr1qb8J2UFLHbAAY7bkg4I
* Wagashi (12k, shitass(?)), no associated pic or replies so might be pickled: https://litter.catbox.moe/ktch8r.pt
* jtveemo (150k): https://a.pomf.cat/kqeogh.pt
	* Creator anon: "I didn't crop out any of the @jtveemo stuff so put twitter username in the negatives."
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
* meme50 (WIP, 0.004 LR, 20k): https://litter.catbox.moe/a31cuf.pt
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
* Sakimichan (DEAD LINK): https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8
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
* Asutora style embedding (mainly reflected in coloring and shading, since his faces are very inconsistent): https://mega.nz/folder/nZoECZyI#vkuZJoQyBZN8p66n4DP62A 
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

Found on Discord:
* Nahida v2: https://cdn.discordapp.com/attachments/1019446913268973689/1031321278713446540/nahida_v2.zip
	* Nahida (50k, very experimental, not enough images): https://files.catbox.moe/2794ea.pt

Found on Reddit:
* look at the 2nd and 3rd images: https://www.reddit.com/gallery/y4tmzo

### **Hypernetworks:**
!!! info If a hypernetwork is <80mb, I mislabeled it and it's an embedding

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

* anon: "Requires extremely low learning rate, 0.000005 or 0.0000005"
**Good Rentry: https://rentry.co/naihypernetworks**
Hypernetwork Dump: https://gitgud.io/necoma/sd-database
Collection: https://gitlab.com/mwlp/sd 
Another collection: https://www.mediafire.com/folder/bu42ajptjgrsj/hn
Senri Gan: https://files.catbox.moe/8sqmeh.rar
Big dumpy of a lot of hypernets (has slime too): https://mega.nz/folder/kPdBkT5a#5iOXPnrSfVNU7F2puaOx0w
Collection of asanuggy + maybe some more: https://mega.nz/folder/Uf1jFTiT#TZe4d41knlvkO1yg4MYL2A
Collection: https://mega.nz/folder/fVhXRLCK#4vRO9xVuME0FGg3N56joMA
**Mogudan, Mumumu (Three Emu), Satou Shouji + constant updates: https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ**
**Korean megacollection:**
* https://arca.live/b/hypernetworks?category=%EA%B3%B5%EC%9C%A0
* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948?category=%EA%B3%B5%EC%9C%A0&p=1

**Chinese telegram (uploaded by telegram anon): magnet:?xt=urn:btih:8cea1f404acfa11b5996d1f1a4af9e3ef2946be0&dn=ChatExport%5F2022-10-30&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce**
>I've made a full export of the Chinese Telegram channel.
>
>It's 37 GB (~160 hypernetworks and a bunch of full models).
>If you don't want all that, I would recommend downloading everything but the 'files' folder first (like 26 MB), then opening the html file to decide what you want.
* Dead link: https://t.me/+H4EGgSS-WH8wYzBl

 Big collection: https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing
* https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing
* https://arca.live/b/aiart/60927159?p=1
* https://arca.live/b/hypernetworks/60927228?category=%EA%B3%B5%EC%9C%A0&p=2

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
* Mogudan, Mumumu (Three Emu), Satou Shouji: https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ
	* creator anon: "this will be the future folder where I will be uploading all my textual inversions. Mumumu hypernetwork is training now, Satou  Shouji dataset has been prepped, now to scrape Onomeshin's art from Gelbooru"
	* Mumumu: 109 images, 75k steps
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
* Nanachi (retrained, 4700 steps, sketches are good, VAE turned off): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA
	* Included is: Nanachi and Puuzaki Puuna (VAE was turned on during training)
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

Found on Korean Site of Wisdom (WIP):
* Terada Tera: https://drive.google.com/file/d/1APwInBROTUdyeoW92yHFn_zBh7rY7b7I/view?usp=sharing
* Kyokai (Ono no Imoto, from KR site): https://kioskloud.xyz/d/634d88968d286fc0ffdf3408-YFISZ3XFW4RXUSTONJEHIM2YNUXGILTU
	* Pass: hulhwa1018
	* https://arca.live/b/hypernetworks/60878934?category=%EA%B3%B5%EC%9C%A0&p=2
* musouduki (KR, 50K): https://mega.nz/file/81JUUbTB#NKz4SI-_oc_2Gx4bgwpVUzRndZhmYe8ugMbsXr-Uolc
	* https://arca.live/b/hypernetworks/60879557?category=%EA%B3%B5%EC%9C%A0&p=2
* Molu: https://drive.google.com/drive/folders/10OxPPHtoCgMoHsUZvT2xWfoU4R2omAEu
	* https://arca.live/b/hypernetworks/60883324?category=%EA%B3%B5%EC%9C%A0&p=2
* oekakizuki 
	* https://drive.google.com/file/d/1VeqnN_rXU2QB0GFhHEfnR6JvqBHn05Ha/view
	* https://arca.live/b/hypernetworks/60885442?category=%EA%B3%B5%EC%9C%A0&p=2
* kyokucho (40k, works best at 10k-15k)
	* https://mega.nz/file/pChGELaI#xy1bBgsphDIQ0Quh36TcD8-MjHLHW245w_Cmj3lRe4k
	* https://arca.live/b/hypernetworks/60920131?category=%EA%B3%B5%EC%9C%A0&p=2
* Big collection: https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing
	* https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing
	* https://arca.live/b/aiart/60927159?p=1
	* https://arca.live/b/hypernetworks/60927228?category=%EA%B3%B5%EC%9C%A0&p=2
* dohna dohna
	* https://drive.google.com/drive/folders/1mQzA21UBxbyDZAAp2SPBBvdKNv_iFU5O
	* https://arca.live/b/hypernetworks/60939821?category=%EA%B3%B5%EC%9C%A0&p=2
* Ashiomi Masato
	* https://mega.nz/file/oo1RhJRb#57bLfYtl0aqe-AZisI3iN0ogYYkj210mrgOfAV0VBS0
	* https://arca.live/b/hypernetworks/60952481?category=%EA%B3%B5%EC%9C%A0&p=2#comment
* Migonon: 
	* https://mega.nz/folder/Ee8WCAoa#NpV9mpfkpnHscCu66L0vWw
* Eula Lawrence (95000): https://mega.nz/file/l9tAHJBD#xdXMf7vulY4GJBigxegFVLSOULONnk4o86qKHYoBZmc
	* (Training info) https://arca.live/b/hypernetworks/61954545?category=%EA%B3%B5%EC%9C%A0&p=1
	* Model loaded at training time full-model-latest

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

### **Aesthetic Gradients**
Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

### **Polar Resources**
* Scat (??): https://files.catbox.moe/8hklc5.pt
* Horse (?): https://files.catbox.moe/idm0vf.pt
* MLP nsfw f16 f32 (might be pickled): https://drive.google.com/drive/folders/14JyQE36wYABH-0TSV_HBEsBJ3r8ZITrS?usp=sharing

### DEAD/MISSING
If you have one of these, please get it to me

Dreambooth:
Anya Taylor-Joy: https://drive.google.com/drive/mobile/folders/1f0FI2Vtr0dNfxyCzsNkNau20JT9Kmgn-
* https://www.reddit.com/r/StableDiffusion/comments/xx8p1p/anya_taylorjoy_model_link_in_comments/

Embed:
* Omaru-polka: https://litter.catbox.moe/qfchu1.pt
* Sakimichan: https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8

Hypernetworks:
* Chinese telegram (dead link): https://t.me/+H4EGgSS-WH8wYzBl
* HiRyS: https://litter.catbox.moe/rx8uv0.pt
* Huge training from KR site: https://mega.nz/folder/wKVAybab#oh42CNeYpnqr2s8IsUFtuQ
	* https://arca.live/b/aiart/60758880
* 焦茶 / cogecha hypernetwork, trained against NAI: https://mega.nz/folder/BLtkVIjC#RO6zQaAYCOIii8GnfT92dw
* 山北東 / northeast_mountain hypernetwork, trained against NAI: https://mega.nz/folder/RflGBS7R#88znRpu7YC1J1JYa9N-6_A

* not sure if this is a hypernet: https://mega.nz/file/l9tAHJBD#xdXMf7vulY4GBigxegFVLSOULONnk4o86qKHYoBZmc
	* probably a mis copy paste of Eula Lawrence: https://mega.nz/file/l9tAHJBD#xdXMf7vulY4GJBigxegFVLSOULONnk4o86qKHYoBZmc

Datasets:
* expanded ie_(raarami) dataset: https://litter.catbox.moe/j4mpde.zip
* Toplessness: https://litter.catbox.moe/mttar5.zip
* https://gofile.io/d/R74OtT
* Onono imoko (NSFW + SFW, 300 cropped images): https://files.catbox.moe/dkn85w.zip
* thanukiart (colored): https://www.dropbox.com/sh/mtf094lb5o61uvu/AABb2A83y4ws4-Rlc0lbbyHSa?dl=0



## Training
* Training guide for textual inversion/embedding and hypernetworks: https://pastebin.com/dqHZBpyA
* Hypernetwork Training by ixynetworkanon: https://rentry.org/hypernetwork4dumdums
* Training with e621 content: https://rentry.org/sd-e621-textual-inversion 
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
* Hypernetworks: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670
* Runpod guide: https://rentry.org/runpod4dumdums
* Small guide written on hypernetwork activation functions.: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-3999660
* Dataset tag manager that can also load loss.: https://github.com/starik222/BooruDatasetTagManager
* Tips on hypernetwork layer structure: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-4010316
* Prompt template + info: https://github.com/victorchall/EveryDream-trainer
* github + some documentation: https://github.com/cafeai/stable-textual-inversion-cafe
* Documentation: https://www.reddit.com/r/StableDiffusion/comments/wvzr7s/tutorial_fine_tuning_stable_diffusion_using_only/

* Site where you can train: https://www.astria.ai/
* Colab: https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb
* Colab 2: https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb
* Colab 3: https://github.com/XavierXiao/Dreambooth-Stable-Diffusion
* Colab 4 (fast): https://github.com/TheLastBen/fast-stable-diffusion

* Dreambooth gui: https://github.com/smy20011/dreambooth-gui
	* the app automatically chooses the best settings for your current VRAM

* **GUI helper for manual tagging and cropping: https://github.com/arenatemp/sd-tagging-helper/**

* Embed vector, clip skip, and vae comparison: https://desuarchive.org/g/thread/89392239#89392432

* Hypernet comparison discussion: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2284

* Comparison of linear vs relu activation function on a number of different prompts, 12K steps at 5e-6.
	* https://files.catbox.moe/q8h8o3.png

* Clip skip comparison: https://files.catbox.moe/f94fhe.jpg

* Hypernetwork comparison: https://files.catbox.moe/q8h8o3.png

* FIND COMPARISON OF ALL MODELS (self note)

* VAE: https://huggingface.co/stabilityai

* Image Scraper: https://github.com/mikf/gallery-dl

* Bulk resizer: https://www.birme.net/?target_width=512&target_height=512

* Model merging math: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/c250cb289c97fe303cef69064bf45899406f6a40#comments
* Old model merging: https://github.com/eyriewow/merge-models
* Model merge guide: https://rentry.org/lftbl
* Supposedly empty ckpt to help with memory issues, might be pickled: https://easyupload.io/ggfxvc


* Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients

* 1 img TI: https://huggingface.co/lambdalabs/sd-image-variations-diffusers

* You can set a learning rate of "0.1:500, 0.01:1000, 0.001:10000" in textual inversion and it will follow the schedule

* Tip: combining natural language sentences and tags can create a better training

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

* Anon's Guide: 
1. Having good text tags on the images is rather important. This means laboriously going through and adding tags to the BLIP tags and editing the BLIP tags as well, and often manually describing the image. Fortunately my dataset had only like...30 images total, so I was able to knock it out pretty quick, but I can imagine it being completely obnoxious for a 500 image gallery. Although I guess you could argue that strict prompt accuracy becomes less important as you have more training examples. Again, if they would just add an automatic deepdanbooru option alongside the BLIP for preprocessing that would take away 99% of the work.

2. Vectors. Honestly I started out making my embedding at 8, it was shit. 16, still shit but better. 20, pretty good, and I was like fuck it let's go to 50 and that was even better still. IDK. I don't think you can go much higher though if you want to use your tag anyway where but the very beginning of a 75 token block. I had heard that having more tokens = needing more images and also overfitting but I did not find this to be the case.

3. The other major thing I needed to do is make a character.txt for textual inversion. For whatever reason, the textual inversion templates literally have NO character/costume template. The closest thing is subject which is very far off and very bad. Thus, I had to write my own: https://files.catbox.moe/wbat5x.txt

4. Yeah for whatever reason the VAE completely fries and fucks up any embedding training and you can only find this from reading comments on 4chan or in the issues list of the github. The unload VAE when training DOES NOT WORK for textual embedding. Again, I don't know why. Thus it is absolutely 100% stone cold essential to rename or move your vae then relaunch everything before you do any textual inversion training. Don't forget to put it back afterwards (and relaunch again) because without the VAE everything is a blurry mess and faces and like sloth from the goonies.

So all told, this is the process:

1. Get a dataset of images together. Use the preprocess tab and the BLIP and the split and flip and all that.

2. Laboriously go through EVERY SINGLE IMAGE YOU JUST MADE while simultaneously looking at their text file BLIP descriptions and updating them with the booru tags or deepdanbooru tags (which you have to have manually gotten ahead of time if you want them), and making sure the BLIP caption is at least roughly correct, and deleting any image which doesn't feature your character after the cropping operation if it was too big. EVERY. SINGLE. IMAGE. OAJRPIOANJROPIanrpianfrpianra

3. Now that the hard parts over, just make your embedding using the make embedding page. Choose some vector amount (I mean I did good with 50 whatever), set girl as your initialization or whatever's appropriate.

4. Go to train page and get training. Everything on the page is pretty self explanatory. I used 5e-02:2000, 5e-03:4000, 5e-04:6000, 5e-05 for the learning rate schedule but you can fool around. Make sure the prompt template file is pointed at an appropriate template file for what you're trying to do like the character one I made, and then just train. Honestly, it shouldn't take more than 10k steps which goes by pretty quick even with batch size 1.

OH and btw, obviously use https://github.com/mikf/gallery-dl to scrape your image dataset from whichever boorus you like. Don't forget the --write-tags flag!

Vector guide by anon:
Think of vectors per token as the number of individual traits the ai will associate with your embedding. For something like "coffee cup", this is going to be pretty low generally, like 1-4. For something more like an artist's style, you're going to want it to be higher, like 12-24. You could go for more, but you're really eating into your token budget on prompts then.

Its also worth noting, the higher the count, the more images and more varied images you're going to want.

You want the ai to find things that are consistent thematics in your image. If you use a small sample size, and all your images just happen to have girls in a bikini, or all with blonde hair, that trait might get attributed to your prompt, and suddenly "coffee cup" always turns out blonde girls in bikinis too.

### Datasets
* ie_(raarami): https://mega.nz/folder/4GkVQCpL#Bg0wAxqXtHThtNDaz2c90w
	* Expanded (DEAD LINK): https://litter.catbox.moe/j4mpde.zip
* Toplessness: https://litter.catbox.moe/mttar5.zip
* Reine: https://files.catbox.moe/zv6n6q.zip
* Power: https://files.catbox.moe/wcpcbu.7z
* Baffu: https://files.catbox.moe/ejh5sg.7z
* tatsuki fujimoto: https://litter.catbox.moe/k09588.zip

## FAQ

Check out https://rentry.org/sdupdates for other questions

**What's all the new stuff?**
>Check here to see if your question is answered: 
* https://scribe.froth.zone/m/global-identity?redirectUrl=https%3A%2F%2Fblog.novelai.net%2Fnovelai-improvements-on-stable-diffusion-e10d38db82ac
* https://blog.novelai.net/novelai-improvements-on-stable-diffusion-e10d38db82ac
* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki

**How do I set this up?**
>Refer to https://rentry.org/nai-speedrun (has the "Asuka test")
>Easy guide: https://rentry.org/3okso
>Standard guide: https://rentry.org/voldy
>Detailed guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
>Paperspace: https://rentry.org/865dy

>AMD Guide: https://rentry.org/sdamd
>* After setting stuff up using this guide, refer back to https://rentry.org/nai-speedrun for settings

**What's the "Hello Asuka" test?**
>It's a basic test to see if you're able to get a 1:1 recreation with NAI and have everything set up properly. Coined after asuka anon and his efforts to recreate 1:1 NAI before all the updates.

>Refer to
>* https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
>* Very easy Asuka 1:1 Euler A: https://boards.4chan.org/h/thread/6893903#p6894236
>	 * Asuka Euler guide: https://imgur.com/a/DCYJCSX
>	* Asuka Euler a guide: https://imgur.com/a/s3llTE5

**What is pickling/getting pickled?**
>ckpt files and python files can execute code. Getting pickled is when these files execute malicious code that infect your computer with malware. It's a memey/funny way of saying you got hacked.
* Automatic1111's webui should unpickle the files for you: https://github.com/AUTOMATIC1111/stable-diffusion-webui/search?q=pickle&type=commits
* https://docs.python.org/3/library/pickle.html

**I want to run this, but my computer is too bad. Is there any other way?**
Check out one of these:
* Free online browser SD: https://huggingface.co/spaces/stabilityai/stable-diffusion
* https://promptart.labml.ai/playground
* https://novelai.manana.kr/
* https://boards.4channel.org/g/thread/89199040
* https://www.mage.space/
* https://github.com/TheLastBen/fast-stable-diffusion
* https://github.com/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb
* visualise.ai
	* Account required
	* Free unlimited 512x512/64 step runs
* img2img with stable horde: https://tinybots.net/artbot
* Free, GPU-less, powered by Stable Horde: https://dbzer0.itch.io/lucid-creations
* Free crowdsourced distributed cluster for Stable Diffusion: https://stablehorde.net/
* https://creator.nightcafe.studio/
* Service of free image generation: Artificy.com
	* Free for personal use
	* We use all most fresh, models for example
	* Different aspect ratios, predefined styles
	* Fast and simple interface
	* Social network features: make & share!
	* Work in progress every day
* https://www.craiyon.com/
	* DALL·E mini
* http://aiart.house
* HF demo list: https://pastebin.com/9X1BPf8S

**How do I run NSFW models in colab?**
Info by anon, I'm not sure if it works:

>!gdown https://huggingface.co/Daswer123/asdasdadsa/resolve/main/novelai_full.ckpt -O /content/stable-diffusion-webui/models/Stable-diffusion/nai.ckpt
>!gdown https://huggingface.co/Daswer123/asdasdadsa/resolve/main/animevae.pt -O /content/stable-diffusion-webui/models/Stable-diffusion/nai.vae.pt
>!gdown https://huggingface.co/Daswer123/asdasdadsa/raw/main/nai.yaml -O /content/stable-diffusion-webui/models/Stable-diffusion/nai.yaml
>!gdown https://huggingface.co/Daswer123/asdasdadsa/resolve/main/v2.pt -O /content/stable-diffusion-webui/v2.pt
>!gdown https://huggingface.co/Daswer123/asdasdadsa/raw/main/v2enable.py -O /content/stable-diffusion-webui/scripts/v2enable.py
>
>!wget https://pastebin.com/raw/ukEFznTb (embed) -O /content/stable-diffusion-webui/ui-config.json
>
>now paste that above in a codeblock and excute it or use this colab https://colab.research.google.com/drive/1zN99ZouzlYObQaPfzwbgwJr6ZqcpYK5-?usp=sharing#scrollTo=SSP9suJcjlWs and select nai in the model dropdown

## Link Dump will sort

**Info:**
* Detailed 1:1 setup NAI + current news: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
* Very easy Asuka 1:1 Euler A: https://boards.4chan.org/h/thread/6893903#p6894236
	* Asuka Euler guide: https://imgur.com/a/DCYJCSX
	* Asuka Euler a guide: https://imgur.com/a/s3llTE5
* Beginner's Guide: https://rentry.org/nai-speedrun
* SD NAI FAQ: https://rentry.org/sdg_FAQ
* general wiki: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki
* general wiki 2: https://wiki.installgentoo.com/wiki/Stable_Diffusion
* general wiki 3: https://github.com/Maks-s/sd-akashic
* general wiki 4: https://github.com/awesome-stable-diffusion/awesome-stable-diffusion
* setup guide: https://rentry.org/voldy
* Easy to setup Standard Diffusion: https://nmkd.itch.io/t2i-gui
* Another easy to setup SD: https://github.com/cmdr2/stable-diffusion-ui
* Models: https://rentry.org/sdmodels
* Japanese 4chan: https://may.2chan.net/b/
* Japanese 4chan 2: https://find.5ch.net/search?q=JNVA%E9%83%A8
* Japanese 4chan 3: http://nozomi.2ch.sc/test/read.cgi/liveuranus/1666357371/355-
* General info: https://rentry.org/sd-nativeisekaitoo
* Guide: https://github.com/Engineer-of-Stuff/stable-diffusion-paperspace/blob/main/docs/archives/VOLDEMORT'S%20GUI%20GUIDE%20FOR%20THE%20MENTALLY%20DEFICIENT.pdf
* NAI info: https://pastebin.com/cExyWkgy
* GPU buying guide: https://rentry.org/stablediffgpubuy
	* Spreadsheet: https://docs.google.com/spreadsheets/d/1Zlv4UFiciSgmJZncCujuXKHwc4BcxbjbSBg71-SdeNk/edit#gid=0
	* Basic guide: https://docs.google.com/document/u/0/d/1lF9_5MIhALo7xCxKpQCZNL_jrJdUHYgJ3prET5yC1rI/mobilebasic
* CSP SD: https://github.com/mika-f/nekodraw
* Link collection: https://github.com/pomee4/SD-LinkList
* debug guide: https://rentry.org/pf98i

**Boorus:**
* Danbooru: danbooru.donmai.us/
* Gelbooru: https://gelbooru.com/
* AIBooru: https://aibooru.online/
* Booru Site: https://infinibooru.moe/
* Local (classic): hydrusnetwork.github.io/
* AI art here: https://e-hentai.org/g/2343153/b4ce2a4b0b
* Easy to setup booru/image gallery by anon, highly recommended: https://github.com/demibit/stable-toolkit
* Simple: https://www.irfanview.com
* SFW: https://nastyprompts.com/
* Infinibooru: https://infinibooru.moe/posts
* Betabooru: https://betabooru.donmai.us
* Japanese pixiv for ai art: https://www.chichi-pui.com/
* discord anon (allows for generation?, runs NovelAI model): https://pixai.art/
* nsfw: https://pornpen.ai/
* /vt/ collection, updated: https://mega.nz/folder/j2AgSB6Y#3Kcq-xms0fWU4na-aaTFhA/folder/unw2EIBI

**Upscalers:**
* Big list: https://upscale.wiki/wiki/Model_Database
* anon recommended this: https://arc.tencent.com/en/ai-demos/imgRestore
* Anime: https://github.com/bloc97/Anime4K
* https://github.com/nihui/waifu2x-ncnn-vulkan
* Some: https://mega.nz/folder/3Jo2AAAa#4CGEwUM0dKu3kkaJa-qUIA
* online: https://replicate.com/xinntao/realesrgan
* anime: https://files.catbox.moe/c6ogfl.pth
* ultrasharp: https://mega.nz/folder/qZRBmaIY#nIG8KyWFcGNTuMX_XNbJ_g
	* https://drive.google.com/file/d/1lELx_WiA25_S8rYINm_DyMNpFOhfZAzt/view
* Waifu2x: https://github.com/nagadomi/waifu2x
* Gigapixel AI: https://www.topazlabs.com/gigapixel-ai

RunwayML: https://github.com/runwayml/stable-diffusion

GPU comparison: https://docs.google.com/spreadsheets/d/1Zlv4UFiciSgmJZncCujuXKHwc4BcxbjbSBg71-SdeNk/edit#gid=0

Undervolt guide: https://www.reddit.com/r/nvidia/comments/tw8j6r/there_are_two_methods_people_follow_when/

frames to video: https://github.com/jamriska/ebsynth

Paperspace guide: https://rentry.org/865dy

More twitter anons: 
https://twitter.com/knshtyk/media

Sigmoid math: https://github.com/AUTOMATIC1111/stable-diffusion-webui/issues/2658

maybe you can edit this to allow 8gb DB training: https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb

## Hall of Fame
automatic1111

## Miscellaneous

Guide to installing NAI by anon:
``` paython
Guide for locally installing NovelAI:

DOWNLOADING:
get NovelAI from magnet:?xt=urn:btih:5bde442da86265b670a3e5ea3163afad2c6f8ecc&dn=novelaileak
---or from picrel >>35097470 (Dead)
get MinGW/Git from https://git-scm.com/download/win (or direct download: https://github.com/git-for-windows/git/releases/download/v2.37.3.windows.1/Git-2.37.3-64-bit.exe
---When installing Git, make sure to select "Git Bash here".
get Python from https://www.python.org/downloads/windows/ (or direct download: https://www.python.org/ftp/python/3.10.6/python-3.10.6-amd64.exe
---When installing Python, make sure to select "add to Path".

Start Git, and type "git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui";
When you do this, it will create a folder called \stable-diffusion-webui\ (by default, in C:\Users\Username\)

When you download the torrent:
1. In \stableckpt\animefull-final-pruned\ rename 'model.ckpt' to 'final-pruned.ckpt'
---Note: the 'animefull' model is the best overall, but struggles at recognizing and outputting VTuber characters in particular. For a better model in that regard, use the 'SFW' model instead; despite the name, it is not SFW-limited.
2. Move 'final-prunded.ckpt' (the file you just renamed) and animevae.pt from \stableckpt\ to \stable-diffusion-webui\models\Stable-diffusion
3. Rename 'animevae.pt' (the file you just moved) to 'final-pruned.vae.pt'
4. Create a new folder \stable-diffusion-webui\models\hypernetworks\ and move all of the modules (which end in .pt) from \stableckpt\modules\modules\ (in the NovelAI)

Whenever you want to run NovelAI from your computer, run webui-user.bat. The first time will initialize, which may cause some errors.
If there are no errors, it will give you a web address (usually http://127.0.0.1:7860/ ). This is the WebUI, from which you run NovelAI using your computer's disk.
The usual errors will require you to edit the .bat--do this in Notepad or n++.
There will be a line of code beginning with "COMMANDLINE_ARGS=". Add "--precision full --no-half" directly after this, on the same line.
If you get an error about "--skip-torch-cuda-test", add it as well (making the line "--skip-torch-cuda-test --precision full --no-half").

After you started the .bat and got the WebUI loaded, go to Settings and scroll to Stable Diffusion. Set the checkpoint to final-pruned and the hypernetwork of your choice.
```

## Contact

If you have information/files (e.g. embed) not on this list or you have questions, please contact me with details. 

Socials: 
Trip: questianon !!YbTGdICxQOw 
Discord: malt#6065
Reddit: u/questianon
Github: https://github.com/questianon
Twitter: https://twitter.com/questianon)
