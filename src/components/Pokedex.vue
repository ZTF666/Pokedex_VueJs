<template>
  <div class="container">
    <h1>Pokémon List</h1>
  <PokemonSearch 
  :apiUrl="apiUrl"
   @setPokemonUrl="setPokemonUrl"
  />
    
    <PokemonList 
    :imgUrl="imgUrl" 
    :apiUrl="apiUrl"
     @setPokemonUrl="setPokemonUrl" />
    <PokemonDetail 
      v-if="showDetail"
      :pokemonUrl="pokemonUrl"
      :imgUrl="imgUrl"
      @closeDetail="closeDetail"
    />

    
  </div>
</template>

<script>
import PokemonSearch from './PokemonSearch.vue';
import PokemonList from './PokemonList.vue';
import PokemonDetail from './PokemonDetail.vue';

export default {
  data:()=>{
    return{
      imgUrl:"https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/",
      apiUrl:'https://pokeapi.co/api/v2/pokemon/',
      pokemonUrl:'',
      showDetail:false
    }
  },
  components:{
    
    PokemonSearch,
    PokemonList,
    PokemonDetail
  },
  methods: {
    setPokemonUrl(url){
      this.pokemonUrl=url;
      this.showDetail=true;
    },
    closeDetail(){
      this.pokemonUrl='';
      this.showDetail=false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css?family=Acme');
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 10px;
    width: calc(100% - 20px);
    min-height: calc(100vh - 20px);
    background: radial-gradient(#360033, #0b8793);
    font-family: 'Acme', arial;
    font-size: 1rem;
    font-weight: normal;
  }
  h1 { color: #efefef; }
</style>