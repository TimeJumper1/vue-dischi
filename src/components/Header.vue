<template>
    <header>
        <img src="../assets/img/logo-small.svg" alt="logo spotify">
    </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    msg: String,
  },
};
</script>
<style scoped lang="scss">
header{
    height: 90px;
    background-color: #2e3a46;
    img{
        width: 70px;
        height: auto;
        margin: 10px;
    }
}
</style>