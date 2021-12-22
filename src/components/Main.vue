<template>
    <main>
        <div class="container">
            <div class="disk-card">
                <DiskCard v-for="(card, index) in disk" :key="index" :card="card" />
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import DiskCard from './DiskCard'

export default {
  name: "Main",
  components: {
    DiskCard
    
  },
  data: function(){
      return{
          disk: []
        }
    },
    created: function(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.disk = response.data.response
        });
    }
};
</script>
<style scoped lang="scss">
main{
    width: 100%;
    height: auto;
    background-color:#1e2d3b ;
    height: calc(100vh - 90px);
    .container{
        width: 70%;
        margin: auto;
        padding: 40px 10px;
        .disk-card{
            display: flex;
            flex-wrap: wrap;
        }
    }
}
</style>