<template>
    <main>
        <div class="container">
            <div class="disk-card" v-if="disk.length > 0">
                <DiskCard v-for="(card, index) in disk" :key="index" :card="card" />
            </div>
            <Loader v-else />
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import DiskCard from './DiskCard'
import Loader from './Loader'

export default {
  name: "Main",
  components: {
    DiskCard,
    Loader
    
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
    height: auto;
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