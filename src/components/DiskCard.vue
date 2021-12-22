<template>
    <div>
        <img :src="card.poster" :alt="card.title">
        <h3>{{ card.title }}</h3>
        <h4>{{ card.author }}</h4>
        <h4>{{ card.year }}</h4>
    </div>
</template>

<script>
export default {
  name: "DiskCard",
  props: {
    card: Object
  },
};
</script>
<style scoped lang="scss">
div{
    width: calc((100% / 5) - 30px);
    padding: 14px;
    background-color:#2e3a46 ;
    margin: 10px;
    img{
        width: 100%;
        height: auto;
        margin: 15px;
        margin: auto;

    }
    h3{
        color: white;
        text-align: center;

    }
    h4{
        color: #6e7471;
        text-align: center;
    }
}
</style>