<template>
    <div class="info-container" id="info">
        <div class="text-container-left">
                <p>A goldsmith originating from Lapland, Finland.</p>
                <br>

                <p>Here I will describe my thoughts about jewelry.</p>
                
                <br>
                <p>You can read more about my work and my life from my bio.</p>
        </div>
        <div class="text-container-right">
            <p>Keep scrolling to view my work. My contact information can be found from my bio. I also post images of
            my work on my instagram account, check it by clicking the icon below.</p>

            <a href="http://www.instagram.com/mattimikaeli/" target="_blank" id="insta-icon"><img src="/insta-icon.svg" alt="instagram-icon"></a>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.info-container {
    display: flex;
    flex: 1;
}

.info-container, .text-container p {
    font-size: 1.2em;
    letter-spacing: 0.1em;
}

.text-container-left {
    display: flex;
    flex-direction: column;
    text-align: left;
    align-self: center;
    align-items: flex-start;
    width: 50%;
    height: 60vh;
    /* padding: 0px 10px 0px 20px; */
    padding: 2em;
}

.text-container-right {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-self: center;
    text-align: center;
    align-items: flex-end;
    width: 50%;
    height: 80vh;
    /* padding: 0px 20px 0px 10px; */
    padding: 2em;
}

#insta-icon {
    align-self: center;
    padding: 40px 5px 0px 5px;
}

</style>
