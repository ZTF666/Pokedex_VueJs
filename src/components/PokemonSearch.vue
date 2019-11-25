
<template>
    <div class="searchbar">
        <form @submit.prevent="setPokemonUrl">
            <input type="text" v-model="searchValue">
        </form>
        <i class="fas fa-search" @click="setPokemonUrl"></i>
    </div>
</template>
<script>
export default {
    
props:[
    'apiUrl'
],
data:()=>{
    return{
        searchValue :'',
    }
},
methods:{
    setPokemonUrl(){
        if(this.searchValue !== '')
         this.$emit('setPokemonUrl', this.apiUrl + this.searchValue);
    }
}

}
</script>

<style lang="scss" scoped>

 .searchbar {
    position: relative;
    width: 100%;
    max-width: 510px;
    padding-bottom: 20px;
    input {
      border: none;
      outline: none;
      border-radius: 5px;
      padding: 10px 40px 10px 10px;
      width: calc(100% - 50px);
      font-size: 1rem;
      box-shadow: 0 15px 30px rgba(0,0,0,.2),
                  0 10px 10px rgba(0,0,0,.2);
    }
    i {
      position: absolute;
      top: 10px;
      right: 10px;
      font-size: 1.25rem;
      color: #0A2E50;
      cursor: pointer;
    }
  }
</style>