<template>
    <main>
        <div class="container">
            <h1>I miei Posts</h1>
            <div class="container_post">
                <PostCard v-for="post in posts" :key="post.id" :post="post" />
            </div>
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

.container {
    width: 80%;
    margin: 0 auto;
}

h1 {
    margin: 25px 0;
}

.container_post {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}
</style>
