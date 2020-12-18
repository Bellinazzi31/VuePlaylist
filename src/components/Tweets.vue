<template>
    <div>
        <button @click="toggleView">
            {{ buttonText }}
        </button>

        <div class="tweets" :class="{'list-view': gridView}" >
            <article class="tweet" v-for="(tweet, index) in tweets" :key="index">
                <h4> {{tweet.author}}</h4>
                <h6> {{tweet.data}}</h6>
                <p> {{tweet.text}}</p>
            </article>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Tweets',

    data() {
        return {
            gridView: false,
            buttonText: 'List view',
            tweets: [
                {
                    author: 'Felipe',
                    date: 'December 12, 2020',
                    text: 'Whats up Boyzzz!!!'
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
            this.gridView = !this.gridView;
            this.buttonText = !this.gridView ? 'Grid view' : 'List view'
        }    
    }
    
}
</script>

<style scoped>
    .tweets {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 1rem;
        padding: 1rem;
    }

    .tweets.list-view {
        grid-template-columns: 1fr;

    }

    .tweet {
        padding: 1rem;
        margin: 1rem;
        background-color: skyblue;
    }

    @media only screen and (min-width: 991px){
        .tweets {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
        }
    }

</style>