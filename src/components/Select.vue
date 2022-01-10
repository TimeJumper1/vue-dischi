<template>
    <div class="wrapper"> 
            <select name="" id="" v-model="options" @change="$emit('selectChosen', options)">
                <option value="All">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>
</template>

<script>
export default {
  name: "Select",
  data: function() {
      return{
          options: ''
      };
    },
    
    
};
</script>
<style scoped lang="scss">
.wrapper{
    width: 70%;
    margin: auto;
    padding-top: 10px;
}
</style>