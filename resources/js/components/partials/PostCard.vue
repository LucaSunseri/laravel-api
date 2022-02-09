<template>
    <li class="card">
        <img
            src="https://images.unsplash.com/photo-1611916656173-875e4277bea6?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MXwxNDU4OXwwfDF8cmFuZG9tfHx8fHx8fHw&ixlib=rb-1.2.1&q=80&w=400"
            alt=""
        />
        <h3>
            <a href="#">{{ post.title }}</a>
        </h3>
        <p>{{ post.content }}</p>
    </li>
</template>

<script>
export default {
    name: "PostCard",
    props: {
        post: Object,
    },
};
</script>

<style lang="scss" scoped>
.card {
    --card-gradient: rgba(0, 0, 0, 0.8);
    --card-gradient: #5e9ad9, #e271ad;
    // --card-gradient: tomato, orange;
    --card-blend-mode: overlay;
    // --card-blend-mode: multiply;

    background-color: #fff;
    border-radius: 0.5rem;
    box-shadow: 0.05rem 0.1rem 0.3rem -0.03rem rgba(0, 0, 0, 0.45);
    padding-bottom: 1rem;
    background-image: linear-gradient(
        var(--card-gradient),
        white max(9.5rem, 27vh)
    );
    overflow: hidden;

    img {
        border-radius: 0.5rem 0.5rem 0 0;
        width: 100%;
        object-fit: cover;
        // height: max(10rem, 25vh);
        max-height: max(10rem, 30vh);
        aspect-ratio: 4/3;
        mix-blend-mode: var(--card-blend-mode);
        // filter: grayscale(100);

        ~ * {
            margin-left: 1rem;
            margin-right: 1rem;
        }
    }

    > :last-child {
        margin-bottom: 0;
    }

    &:hover,
    &:focus-within {
        --card-gradient: #24a9d5 max(8.5rem, 20vh);
    }
}

.card h3 {
    margin-top: 1rem;
    font-size: 1.25rem;
}

.card a {
    color: inherit;
}
</style>
