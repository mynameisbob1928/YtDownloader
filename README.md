# YtDownloader
Hi,
This is just a small project that I decided to do to automate the process of downloading many youtube videos at once.

### How it works 
Ok so this uses a program called [yt-dlp](https://github.com/yt-dlp/yt-dlp "yt-dlp"), its a command prompt .exe file that allows easy download of youtube videos. I will go through how to get it and how to make it work later. There is also ffmpeg which I think changes file formats. 
The download command that it uses for yt-dlp with all the arguments is very long but it does what we need it to do

    yt-dlp --write-description --write-info-json --write-playlist-metafiles --write-comments --write-thumbnail --write-link --write-url-link --write-webloc-link --merge-output-format mkv --write-subs --no-write-auto-subs --sub-format srt --embed-subs --embed-thumbnail --embed-metadata --embed-chapters --embed-info-json --convert-thumbnails jpg

The other main thing that it will do is log events to a discord server. Again I'll go over how to sort this out later. If you don't want this and only want the downloader I put it up on another repository [here](https://github.com/mynameisbob1928/YtDownloaderNoBot).

### Requirements
- Node.js v18.x.x (I may release a version that doesn't require it sometime)
- discord.js (instructions later)
- A discord: Server, Bot and Account (if you need instructions on how to get any of these then go watch a youtube video on it)
- yt-dlp and ffmpeg 
- and of course the files from here 

### Installation
Ok so here is probably the hardest part 
#### Node.js, yt-dlp and ffmpeg:
1. Go to the [nodejs download page](https://nodejs.org/dist/v18.18.0/). I am using v18.18.0 for this project. Some newer versions do not have some functions that is in v18. For windows there is the .msi for x64 and x86 pcs. Download that and run it and follow all the instructions there. On other OS's i have no clue how to install so good luck.
2. Go to the [yt-dlp releases page](https://github.com/yt-dlp/yt-dlp/releases/latest) and downlado the yt-dlp.exe file there.
3. Downloading ffmpeg is a little harder. The actual download for it is difficult to find so the direct download link will be linked [here](https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-essentials.7z) however for those untrusting users when you find it we only need the essentials version the full one is not required. Once its downloaded you need to use 7-zip for winrar or some other extracting program (the default windows one doesn't support .7z files). Once you have that there should be 3 .exe files contained. 
4. Now, make a folder anywhere on your pc, doesn't matter where, and place yt-dlp.exe, ffmpeg.exe, ffplay.exe and ffprobe.exe all in the same folder. Copy the folder path to your clipboard we're going to need that later.
5. Open up the windows search thing, and type 'path'. Hopefully one of the options should say 'Edit the system enviroment variables'. CLick on that to open it. It should look something the image below 
![envvars](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/27d90a88-c1bc-4d55-96f0-98b66496f879)
6. On there click on the 'Enviroment variables...' at the bottom. This should show up.
![nextenvvars](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/ea0319fc-03fd-426a-90c4-310fc1b82456)
7. Click on 'Path' and then 'Edit...' as shown in the image above. Make sure to use the top one not the bottom one.
8. On the final window that shows, click 'New...' and then paste in the folder path that you copied earlier. 
![usingenvvars](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/825267b3-27c7-4e82-81f1-3bf27c8126f4)
9. Now on each window that came up just click on at the bottom to apply changes.
#### Discord.js
Open up a command prompt by typing cmd in the address bar/folder path (whatever you want to call it) **in the same folder as the main.js file**. And don't just move the main.js file either, it'll break if you do. In there you got to type 'npm i discord.js'. This should take about 10 seconds maybe to install depending on your pc power and wifi speed.
#### Repository files
Either use the git command or download the zip from the clearly green button at the top of this github page with the word 'code' written on it. On there will be the downlaod zip option. download that, extract it using whatever and now you're almost ready to go.
### Configuration
Once you got the repository files downloaded, in the videos folder there is already a folder there labelled 1, you dont need that so you can delete it if you want.

Now you should be left with:
- an empty folder named 'videos' (do not delete this)
- links.txt (should also be empty)
- main.js
- package.json
- yos.json
- 
(The .json, .js and .txt may not show if is not enabled in your pc settings)

In yos.json, you need to fill in 3 options. First one is the bot token (go watch youtube vid on hwo to get it if you're not sure). Second is your user id (again find a yt video), and finally the channel id where the logs are going to be sent (I'm not even gonna say it).
### Running the script
One more thing, in the links.txt file you should place all your video links you want to download. Make sure they are all seperated by **only a space**. Anything else will break it, I think.

Now that you got everthing ready you can open command prompt again and simply type 'node .' and it will begin to download your videos.

### Other stuff
I'm just going to add some images of what the discord logs look like.

![start](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/24e31c55-9690-401e-a493-aefbae23aaca)

![downloadedvid](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/d0711f8a-2b6f-4823-aca9-85c6222ce310)

![finished](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/d5037d3f-94c9-4055-adc3-4ddf4071c695)

![errexit](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/4c47c7c4-05a7-44bf-a113-ad997028cbbc)

### Some helpful tools
###### context
So I made this so I could download the videos in someone channel, I could do it without this script by typing it all manually. But their channels are absolutely huge with years of content. So this was made. But then I needed to get all the video urls, so I found a another script that can get all the video urls in a channel. So here is some code to help with that.

This code is executed in your browser's console. Open the console by pressing ctrl + shift + i 

![ytconsole](https://github.com/mynameisbob1928/YtDownloader/assets/129603125/8f4936b6-4353-4968-8ff1-44ffeaa56762)

If any red/orange stuff show, don't worry about it.

Now find the input box thing and paste in this code

```js
var scroll = setInterval(function(){ window.scrollBy(0, 1000)}, 1000);
```
This will cause your screen to constantly scroll down so that every video is loaded on the webpage. Once that is done you can put in this code which will stop the scrolling
```js
window.clearInterval(scroll);
```
Now there is one more code block to enter. This one will fetch everything and put all the videos in an array.
```js
var urls = document.querySelectorAll('a');
var uniqueLinks = new Set();

urls.forEach(function (v) {
    if (v.classList.contains("yt-simple-endpoint") && v.hasAttribute('href')) {
        var href = v.getAttribute('href');
        if (href.startsWith('/watch?v=')) {
            uniqueLinks.add(href);
        }
    }
});
var all = []
uniqueLinks.forEach(function (link) {
    all.push(`https://www.youtube.com${link}`)
});
console.log(all)
```
Once you have done that you can right click the large string that shows up and click 'Copy object`

