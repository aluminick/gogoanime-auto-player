# gogoanime-auto-player
*Tired of clicking to the next episode?* Say no more...

Install this script that autoplays your favorite anime on [gogoanime.tv](http://gogoanime.tv/).

**Google Chrome** only.
#How to use
  * Install google chrome plugin (*cjs*):
  
   Get it here --> https://chrome.google.com/webstore/detail/custom-javascript-for-web/poakhlngfciodnhlhhgnaaelnpjljija?hl=en
  * Add this script to **cjs**
  ```javascript
// Here You can type your custom JavaScript...
  var video = document.getElementById('my_video_1_html5_api'),
    ads = document.getElementsByClassName('add_ads')[0],
    play_button = document.getElementsByClassName('vjs-big-play-button')[0],
    quality = document.getElementById('selectQuality'),
    selectedIndex = 1,
    selectedQuality = quality.getElementsByTagName('option')[selectedIndex].value,
    next = document.getElementsByClassName('anime_video_body_episodes_r')[0].getElementsByTagName('a')[0].getAttribute('href');

    ads.style.display = "none";
    play_button.style.display = "none";
    video.src = selectedQuality;
    video.load();
    video.onloadedmetadata = function(){
        quality.selectedIndex = selectedIndex;
        video.play();
    }
    video.onended = function(){
        window.location = next+"#"+video.getAttribute('id');
    }
    console.log('listening');
  ```
##Option
  Changing the quality:
  
    **Note:** If the video has `1080p`, `0` = `1080p`, `1` = `720p`, and `2` = `360p`.
  
    `0` = `720p`
    
    `1` = `360p`
    
    
    Change this line -> selectedIndex = `1`;
  
  *Enjoy*!
