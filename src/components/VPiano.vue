<template>
    <div class="content">
        <div class="container">
            <img src="@/assets/logo.png" alt="Digits logo">
            <hr class="hr">
            <div id="note"  class="touches">
                <button v-for="note in notes" :key="note.name" class="blanc" v-on:click="play('do')">Do</button>
                <button v-for="note in notes" :key="note.name" class="noir" v-on:click="play('do#')">Do#</button>
                <button class="blanc" v-on:click="say('re')">Ré</button>
                <button class="noir" v-on:click="say('re##')">Ré#</button>
                <button class="blanc" v-on:click="say('mi')">Mi</button>
                <button class="blanc" v-on:click="say('fa')">Fa</button>
                <button class="noir" v-on:click="say('fa#')">Fa#</button>
                <button class="blanc" v-on:click="say('sol')">Sol</button>
                <button class="noir" v-on:click="say('sol#')">Sol#</button>
                <button class="blanc" v-on:click="say('la')">La</button>
                <button class="noir"  v-on:click="say('la#')">La#</button> 
                <button class="blanc" v-on:click="say('si')">Si</button>
                <!--<audio v-for="note in notes" :key="note.src" ref="audioElm"></audio>-->
                <audio ref="audioElm" src="assets/sounds/B.mp3"></audio>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    el: 'note',
    data() {
		return {
			notes: [
                {
                    name: "do",
                    src: "assets/sounds/C.mp3"
                },
                {
                    name: "do#",
                    src: "assets/sounds/C#.mp3"
                }
            ]
        }
	},
    methods: {
        play() {
            this.$refs.audioElm.play();
        }
    },
    
}

</script>

<style lang="postcss" scoped>
.container {
    margin-left: auto;
    margin-right: auto;
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