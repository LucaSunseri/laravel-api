<template>
    <div class="card">
        <h2>{{ post.title }}</h2>
        <p class="content">{{ post.content }}</p>
        <p class="data">10/25/2000</p>
        <p class="card__apply">
            <a class="card__link" href="#"
                >Vai al Post <i class="fas fa-arrow-right"></i
            ></a>
        </p>
    </div>
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
    margin: 20px;
    padding: 20px;
    width: 500px;
    min-height: 200px;
    border-radius: 10px;
    box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.25);
    transition: all 0.2s;
    background: radial-gradient(#76b2fe, #b69efe);
}

.card:hover {
    box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.4);
    transform: scale(1.01);
}

.card__apply {
    margin-top: 30px;
}

.card__link {
    position: relative;
    text-decoration: none;
    color: rgba(255, 255, 255, 0.9);
}

.card__link::after {
    position: absolute;
    top: 25px;
    left: 0;
    content: "";
    width: 0%;
    height: 3px;
    background-color: rgba(255, 255, 255, 0.6);
    transition: all 0.5s;
}

.card__link:hover::after {
    width: 100%;
}

.content {
    padding: 20px 0;
}

.data {
    text-align: end;
}
</style>
