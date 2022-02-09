<template>
    <footer>
        <p>Questo è il footer del Blog</p>
    </footer>
</template>

<script>
export default {
    name: "Footer",
};
</script>

<style lang="scss" scoped>
footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background: linear-gradient(
            to bottom,
            rgba(255, 255, 255, 0.15) 0%,
            rgba(0, 0, 0, 0.15) 100%
        ),
        radial-gradient(
                at top center,
                rgba(255, 255, 255, 0.4) 0%,
                rgba(0, 0, 0, 0.4) 120%
            )
            #989898;
    background-blend-mode: multiply, multiply;
    p {
        text-align: center;
        font-size: 20px;
        font-weight: 700;
        color: #fff;
        padding: 20px;
    }
}
</style>
