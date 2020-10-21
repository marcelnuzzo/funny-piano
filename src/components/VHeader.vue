<template>
    <header class="content">
        <div class="container">
            <img src="@/assets/logo.png" alt="Digits logo">
            <hr>
            <div id="do">
                <button class="blanc" v-on:click="say('do')">Do</button>
                <button class="noir" v-on:click="say('do#')">Do#</button>
                <button class="blanc" v-on:click="say('re')">Ré</button>
                <button class="noir" v-on:click="say('re##')">Ré#</button>
                <button class="blanc" v-on:click="say('mi')">Mi</button>
            </div>
        </div>
    </header>
</template>

<script>

export default {
    el: '#do',
    methods: {
        say: function (message) {
            alert(message)
        }
    }
}

</script>

<style lang="postcss" scoped>
.container {
    margin-left: auto;
    margin-right: auto;
}

.blanc {
    display: inline; 
    width: 100px;
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
}

img {
    display: block;
    margin-left: auto;
    margin-right: auto 
}

</style>