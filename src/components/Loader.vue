<template>
    <div>
        caricamento
        
    </div>
</template>

<script>
export default {
  name: "Loader",
  props: {
    msg: String,
  },
};
</script>
<style scoped lang="scss">
div{
    width: 50%;
    margin: auto;
    color: black;
    height: 500px;
    background-color: white;
    border-radius: 50%;
    text-align: center;
    line-height: 250px;
    font-size: 40px;
}
</style>