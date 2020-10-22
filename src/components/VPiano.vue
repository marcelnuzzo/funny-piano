<template>
    <div class="content">
        <div class="container">
            <img src="@/assets/logo.png" alt="Digits logo">
            <hr class="hr">
            <div id="note"  class="touches">
            
                <button v-for="note in notes" :key="note.name" :class="note.color" @mouseenter="setUrl(note.src)" @click="play()"  v-on:keyup="keymonitor">{{note.name}}</button>
                <audio ref="audioElm" :src="currentSound"></audio>
            
                <!--
                <div v-if="notes.name.substr(2) === '#'">
                    <button v-for="note in notes" :key="note.name" @mouseenter="setUrl(note.src)" @click="play()" class="blanc">{{note.name}}</button>
                    <audio ref="audioElm" :src="currentSound"></audio>
                </div>
                <div v-else>
                    <button v-for="note in notes" :key="note.name" @mouseenter="setUrl(note.src)" @click="play()" class="noir">{{note.name}}</button>
                    <audio ref="audioElm" :src="currentSound"></audio>
                </div>
                -->
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            currentSound: null,
            notes: [
                {
                    name: "do",
                    src: "/assets/sounds/C.mp3",
                    color: "blanc"
                },
                {
                    name: "do#",
                    src: "/assets/sounds/C#.mp3",
                    color: "noir"
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
        setUrl(src) {
            this.currentSound = encodeURIComponent(src)
        },
        play() {
            //console.log(this.currentSound)
            this.$refs.audioElm.currentTime = 0
            this.$refs.audioElm.play();
        },
        keymonitor: function(event) {
        console.log(event.key);
            if(event.key == "q")
            {
                
                this.note.src = "/assets/sounds/C.mp3"
                console.log(this.note.src);
            }
        },
    },
}

</script>

<style lang="postcss" scoped>
.container {
    margin-left: auto;
    margin-right: auto;
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

img {
    display: block;
    margin-left: auto;
    margin-right: auto 
}

.touches {
    margin-left: 20%;
    margin-right: 20%;
}

.hr {
    margin-bottom: 20px;
}

</style>