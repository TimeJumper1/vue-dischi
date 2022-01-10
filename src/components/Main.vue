<template>
    <main>
        <Select @selectChosen="selectStart" />
        <div class="container">
            <div class="disk-card" v-if="disk.length > 0">
                <DiskCard v-for="(card, index) in FilteringCard" :key="index" :card="card" />
            </div>
            <Loader v-else />
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import DiskCard from './DiskCard'
import Loader from './Loader'
import Select from './Select'

export default {
  name: "Main",
  components: {
    DiskCard,
    Loader,
    Select
    
  },
  data: function(){
      return{
          disk: [],
          opzioni: ''
        }
    },
    methods: {
        selectStart: function(options) {
            this.opzioni = options;
        },
    },
    computed: {
        FilteringCard: function(){
            if(this.opzioni === 'All'){
                return this.disk
            }
            let filteredArray = this.disk.filter((element) => {
                return element.genre.includes(this.opzioni)
            });
            return filteredArray
            // return this.disk 
            
        },
        
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