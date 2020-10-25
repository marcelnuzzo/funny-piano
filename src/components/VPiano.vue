<template>
    <div class="content">
        <div class="container">
            <img src="@/assets/logo.png" alt="Digits logo" class="imglogo">
            <hr class="hr">
            <div id="note"  class="touches enligne">
                <button v-for="note in notes" :key="note.name" :class="note.color" @mouseenter="setUrl(note.src)" @click="play()"  @keyup="keymonitor">{{note.name}}</button>
                <audio ref="audioElm" :src="currentSound" preload="none"></audio>
            </div>
            <div classe="enligne emoji">
                <img :src="gif" alt="">
            </div>
        </div>
    </div>
   
</template>

<script>
import { GiphyFetch } from '@giphy/js-fetch-api'
const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
export default {
    data() {
        return {
            gif:"",
            currentSound: null,
            notes: [
                {
                    name: "do",
                    src: "/assets/sounds/C.mp3",
                    color: "blanc",
                },
                {
                    name: "do#",
                    src: "/assets/sounds/C#.mp3",
                    color: "noir",
                },
                {
                    name: "re",
                    src: "/assets/sounds/D.mp3",
                    color: "blanc"
                },
                {
                    name: "re#",
                    src: "/assets/sounds/D#.mp3",
                    color: "noir"
                },
                {
                    name: "mi",
                    src: "/assets/sounds/E.mp3",
                    color: "blanc"
                },
                {
                    name: "fa",
                    src: "/assets/sounds/F.mp3",
                    color: "blanc"
                },
                {
                    name: "fa#",
                    src: "/assets/sounds/F#.mp3",
                    color: "noir"
                },
                {
                    name: "sol",
                    src: "/assets/sounds/G.mp3",
                    color: "blanc"
                },
                {
                    name: "sol#",
                    src: "/assets/sounds/G#.mp3",
                    color: "noir"
                },
                {
                    name: "la",
                    src: "/assets/sounds/A.mp3",
                    color: "blanc"
                },
                {
                    name: "la#",
                    src: "/assets/sounds/A#.mp3",
                    color: "noir"
                },
                {
                    name: "si",
                    src: "/assets/sounds/B.mp3",
                    color: "blanc"
                },
            ]
        }

    },
    methods: {
        async emoji() {
            const { data: gif } = await gf.random()
            //console.log(gif)
            this.gif = gif.images.fixed_width.webp
        },
        setUrl(src) {
            this.currentSound = encodeURIComponent(src)
        },
        play() {
            //console.log(this.currentSound)
            this.$refs.audioElm.currentTime = 0
            this.$refs.audioElm.play()
            this.emoji()
        },
        keymonitor(event) {
            if(event.key == "q")
            {   
                this.currentSound = encodeURIComponent("/assets/sounds/C.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "s")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/C#.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "d")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/D.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "f")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/D#.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "g")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/E.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "h")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/F.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "j")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/F#.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "k")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/G.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "l")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/G#.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "m")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/A.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "w")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/A#.mp3")
                console.log(this.currentSound)
            }
            if(event.key == "x")
            {
                this.currentSound = encodeURIComponent("/assets/sounds/B.mp3")
                console.log(this.currentSound)
            }
            setTimeout(function(){}, 200);
            this.play()
            
        },
      
    },
}

</script>

<style lang="postcss" scoped>
.container {
    //margin-left: auto;
    //margin-right: auto;
}

.couleur {
    display: inline; 
    width: 50px;
    height: 100px;
    padding: 5px;
    border: 1px solid grey;  
}

.blanc {
    display: inline; 
    width: 50px;
    height: 100px;
    padding: 5px;
    border: 1px solid grey;  
    background-color: wheat; 
}

.noir {
    display: inline; 
    width: 50px;
    height: 100px;
    padding: 5px;
    border: 1px solid grey;  
    background-color: black; 
    color: white;
}

.imglogo {
    display: block;
    margin-left: auto;
    margin-right: auto 
}

.touches {
    margin-left: 20px;
    //margin-right: 20%;
}

.hr {
    margin-bottom: 20px;
}

#note {
    margin-top: 40px;
    margin-bottom: 10px;
}

.enligne {
    //display: inline-block;
}

.emoji {
   
    margin-top: 10px;
    margin-left: 20px;
}

</style>