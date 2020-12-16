<template>
    <div>

        <button @click="toggleView">Toggle View</button>
        <div id="tweets" :class="{'list-view': lisView}" >
            <article class="tweet" v-for="(tweet, index) in tweets" :key="index">
                <h4> {{tweets.author}}</h4>
                <h6> {{tweets.data}}</h6>
                <p> {{tweets.text}}</p>
                {{tweet.text}}
            </article>

        </div>

    </div>

</template>

<script>
export default {
    name: 'vue-tweets',
    data() {
        return {
            listView: true,
            tweets: [
                {
                    author: 'Felipe',
                    date: 'December 12, 2020',
                    text: 'Hello world I am tweet!!!'
                },
                {
                    author: 'Luan',
                    date: 'December 03, 2020',
                    text: 'Going to Canada 2021'
                },
                {
                    author: 'Wagner',
                    date: 'December 10, 2020',
                    text: 'I sent the tshirts'
                },
            ]
        }
    },
    methods: {
        toggleView() {
            this.listView = !this.listView;
            if(this.listView == true) {
                document.querySelector('button').innerText = "List View";
            }else{
                document.querySelector('button').innerText = "Gtid View";
            }
        }
    }
    
}
</script>

<style scoped>
    #tweets {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 1rem;
        padding: 1rem;
    }
    #tweets.list-view {
        grid-template-columns: 1fr;

    }
    article {
        padding: 1rem;
        margin: 1rem;
        background-color: skyblue;
    }
    @media only screen and (min-width: 991px){
        #tweets{
            display: grid;
            grid-template-columns: repeat(2, 1fr);

        }
    }

</style>