<template>
    <main>
        <div class="container">
            <h1>I Miei Post</h1>
            <ul class="card-wrapper">
                <PostCard v-for="post in posts" :key="post.id" :post="post" />
            </ul>
        </div>
    </main>
</template>

<script>
import PostCard from "./partials/PostCard.vue";

export default {
    name: "Posts",
    components: {
        PostCard,
    },
    data() {
        return {
            apiUrl: "http://127.0.0.1:8000/api/posts",
            posts: {},
        };
    },
    mounted() {
        this.getPosts();
    },
    methods: {
        getPosts() {
            axios
                .get(this.apiUrl)
                .then((response) => {
                    // handle success
                    this.posts = response.data.data;
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                });
        },
    },
};
</script>

<style lang="scss" scoped>
main {
    height: calc(100vh - 140px);
    overflow: auto;
    padding-bottom: 100px;
}
h1 {
    margin: 25px 0;
}

.container {
    width: 80%;
    margin: 0 auto;
}
.card-wrapper {
    list-style: none;
    padding: 0;
    margin: 0;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(30ch, 1fr));
    grid-gap: 1.5rem;
    max-width: 100vw;
    width: 120ch;
    padding-left: 1rem;
    padding-right: 1rem;
}
</style>
