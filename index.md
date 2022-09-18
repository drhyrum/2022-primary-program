## 2022 Primary Program Playlist

### Play audio in browser

<style>
    #playlist{
        list-style: none;
    }
    #playlist li a{
        color:black;
        text-decoration: none;
    }
    #playlist .current-song a{
        color:blue;
    }
</style>

<audio src="" controls id="audioPlayer">
    Sorry, your browser doesn't support HTML 5!
</audio>


<ul id="playlist">

<li class="current-song"><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/ILivedInHeaven.mp3">I Lived in Heaven</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/IWillFollowGodsPlanForMe.mp3">I Will Follow God's Plan For Me</a></li>
    
<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/HeSentHisSon.mp3
">He Sent His Son</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/FollowTheProphet.mp3">Follow the Prophet - verses 1 (Adam), 3 (Noah), 5 (Moses) and 9 (today)</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/IWillBeValiant.mp3">I Will Be Valiant</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/ImTryingToBeLikeJesus.mp3
">I'm Trying To Be Like Jesus</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/SearchPonderAndPray.mp3">Search, Ponder and Pray</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/ILoveToSeeTheTemple.mp3">I Love To See the Temple</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/MyRedeemerLives.mp3">My Redeemer Lives</a></li>

<li><a href="https://github.com/drhyrum/2022-primary-program/raw/main/list/IWillWalkWithJesus.mp3">I Will Walk With Jesus</a></li>  
</ul>
    
<script src="https://code.jquery.com/jquery-2.2.0.js"></script>
<script>
    // loads the audio player
    audioPlayer();

       function audioPlayer(){
            var currentSong = 0;
            $("#audioPlayer")[0].src = $("#playlist li a")[0];
            $("#audioPlayer")[0].play();
            $("#playlist li a").click(function(e){
               e.preventDefault(); 
               $("#audioPlayer")[0].src = this;
               $("#audioPlayer")[0].play();
               $("#playlist li").removeClass("current-song");
                currentSong = $(this).parent().index();
                $(this).parent().addClass("current-song");
            });
            
            $("#audioPlayer")[0].addEventListener("ended", function(){
               currentSong++;
                if(currentSong == $("#playlist li a").length)
                    currentSong = 0;
                $("#playlist li").removeClass("current-song");
                $("#playlist li:eq("+currentSong+")").addClass("current-song");
                $("#audioPlayer")[0].src = $("#playlist li a")[currentSong].href;
                $("#audioPlayer")[0].play();
            });
        }    
</script>


### Download a playlist

<a href="2022-primary-program-playlist.m3u" target="_blank" download type="audio/x-mpegurl">Download the playlist.</a>

<!-- ### QR Code to website

<img src="https://github.com/drhyrum/2022-primary-program/raw/gh-pages/primary_program_qr_code.png"> -->


