<template>
  <div>
    <div id="slogan" class="text-center">
      <h1>Fliper</h1>
      <h6>venha colocar seu dinheiro na gente</h6>
    </div>

    <div id="main">
      <div class="container">
        <div class="row">
          <div class="col-md">
            <h5>Login</h5>
            <div class="card">
              <div class="card-body">
                <input
                  class="form-control"
                  type="text"
                  v-model="email"
                  placeholder=" Digite o seu email"
                />
              </div>
              {{email}}
            </div>
          </div>
          <div class="col-md">
            <h5>Senha 44444444444</h5>
            <div class="card">
              <div class="card-body">
                <input
                  class="form-control"
                  type="text"
                  v-model="senha"
                  placeholder=" Digite o sua senha"
                />
              </div>
              {{senha}}
            </div>
          </div>
        </div>
        <br />
        <div class="row">
          <div class="col-md">
            <button type="button" class="btn btn-primary" v-on:click="submitLogin()">Entrar</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gql from "graphql-tag";
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";

export default {
  name: "App",
  data() {
    return {
      me: null,
      email: "",
      senha: ""
    };
  },
  apollo: {
    me: gql`
      query getInvestmentAgents {
        getInvestmentAgents {
          id
          name
          email
          cellphone
          doc
          fliperCode
        }
      }
    `
  },
  methods: {
    submitLogin() {
      console.log("botaao clicado");
    }
  }
};
</script>

<style>
#slogan {
  margin-top: 30px;
  margin-bottom: 30px;
}
#main {
  background-color: #f1f1f1;
  padding-top: 30px;
  padding-bottom: 30px;
}
</style>