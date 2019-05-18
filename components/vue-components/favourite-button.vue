<template>
    <div>
        <button @click="setFavourite">
            {{ text }}
        </button>
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            text: 'Favourite'
        }
    },
    mounted() {
        if(localStorage[this.name]) this.text = localStorage[this.name];
    },
    props: {
        name: {
            type: String,
            default: "this manga"
        }
    },
    methods: {
        setFavourite: function (event) {
            this.text = this.text == 'Unfavourite' ? 'Favourite' : 'Unfavourite';
            localStorage[this.name] = this.text;
        }
    }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css?family=Raleway&display=swap');
    button {
        background-color: white;
        border: 1px solid #343a40;
        padding: 10px;
        margin: 5px;
        font-family: 'Raleway', sans-serif;
        border-radius: 3px;
        outline: none;
    }

    button:hover {
        background-color: #343a40;
        color: white;
    }
</style>



