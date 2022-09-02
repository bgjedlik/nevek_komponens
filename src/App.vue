<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-6">
        <h2 class="mb-3">Új név</h2>
        <input-form @addToList="saveName"></input-form>
        <!-- <div class="mb-3">
          <label for="nev" class="form-label">
            Név:
          </label>
          <input
            type="text"
            class="form-control"
            id="nev"
            v-model="name"
            ref="inputName"
          />
          
          <button type="button" class="btn btn-primary mt-3" @click="saveName">Mentés</button>
        </div> -->
      </div>
      <div class="col-md-6">
        <h2>Nevek:</h2>
        <name-list :names="names"></name-list>
        <!-- <ul>
          <li v-for="name in names" :key="name">{{ name }}</li>
        </ul> -->
        <!-- <p v-for="name in names" :key="name">{{ name }}</p>
        <table class="table">
          <tr v-for="name in names" :key="name">
            <td>{{ name }}</td>
          </tr>
        </table> -->
      </div>
    </div>
  </div>
</template>

<script>
import InputForm from './components/InputForm.vue';
import NameList from './components/NameList.vue';

export default {
  name: "App",
  data(){
    return {
    //  name : '',
      names:[],
    }
  },
  components:{
    NameList,
    InputForm

  },
  methods:{
    saveName(data){
      //if (this.name == '') return
      this.names.push(data)
      //this.name=''
      //console.log(this.names)
      //console.log(this.$refs.inputName)
      //this.$refs.inputName.focus(); // rá viszi a fókuszt az objektumra
    }
  },
};
</script>

<style>
</style>
