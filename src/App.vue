<template>
  <div class="container">
    <div class="row">
      
      <div class="col-md-4">
        <img alt="Vue logo" src="./assets/wesley.png" />
      </div>
      <!-- fim da imagem -->

      <div class="col-md-7">

            <h1>Cálculo de % de anjo</h1>
            <p>
              Em 2015 uma obra prima da música foi lançada. <b>Aquele 1%</b> é a
              música que por meio de uma matemática sofistica calcula seu valor de
              anjo perfeito.
            </p>

            <div class="mb-3">
              <label class="form-label">dia:</label>
              <input class="form-control" type="text" v-model="dia" />
            </div>
            <div>
              <label class="form-label">mês:</label>
              <input class="form-control" type="text" v-model="mes"/>
            </div>
            <div>
              <label class="form-label">ano:</label>
              <input class="form-control" type="text" v-model="ano"/>
            </div>
            <button class="btn btn-primary my-3" v-on:click="calcular()">Calcular</button>


      </div>
      <!-- fim do formulário -->

    </div>

    <div class="row">
      <div class="offset-md-4 col-md-8">
        <!-- area para exibir as variáveis -->
        <p>Você é {{anjeza}}% anjo, mas aquele {{nao_anjeza}}% não anjo</p>
      </div>
    </div>

  </div>
</template>
<script>


  export default {
    name: 'App',
    data() {
      return {
        dia: 0,
        mes: 0,
        ano: 0,
        anjeza: 0,
        nao_anjeza: 0,
      }
    },
    methods:{
      somatorio(mes){
        var soma = 0;
        for(var i = 1; i <= mes; i++){
          soma += i;
        }
        return soma;
      },
      calcular(){
        if(this.ano > 1900){
          this.nao_anjeza = somatorio(parseInt(this.mes)) + (parseInt(this.ano - 1900)/100) * (50 - parseInt(this.dia));
          this.anjeza = 100 - this.nao_anjeza;
        }
        else{
          this.nao_anjeza = somatorio(parseInt(this.mes)) + (parseInt(this.ano - 2000)/100) * (50 - parseInt(this.dia));
          this.anjeza = 100 - this.nao_anjeza;
        }
        
      }
    }
  }

</script>
<style >

 @import "https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css";

</style>