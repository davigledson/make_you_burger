<template>
    <div id="main-banner">
        <h1>
            make your Burger
        </h1>
    </div>
</template>
<script>
export default {
    name: "Banner",
}
</script>
<style scoped>

#main-banner {
    background-image: url("/img/burger.jpg");
    background-position: 0 - 250px;
    background-size: cover;
    display: flex;
    height: 500px;
    align-items: center;
    justify-content: flex-start;

}
#main-banner h1 {
    color: #fff;
    text-align: center;
    font-size: 60px;
    background-color: #222;
    padding: 20px;

}
</style>