<template>
  <div class="container">
    <div class="row">
    <div class="col m-1 py-1 border rounded w-1">
      <div class="row">
        <div class="col-1">
          <img :src="user.picture.medium" />
        </div>
        <div class="col-9" v-if="!masInfo">
          <div class="container">
            <div class="row">
              Name: {{ user.name.title }} {{ user.name.first }}
              {{ user.name.last }}
            </div>
            <div class="row">Gender: {{ user.gender }}</div>
            <div class="row">Country: {{ user.location.country }}</div>
          </div>
        </div>
        <div class="col-9" v-if="masInfo">
          <div class="container">
            <div class="row">
              E-mail: {{user.location.city}}
            </div>
            <div class="row">City: {{ user.gender }}</div>
          </div>
        </div>
        <div class="col">
          <div class="badge tier3" v-if="user.registered.age > 15">
            Registrado por mas de 15 años!
          </div>
          <div class="badge tier2" v-else-if="user.registered.age > 10">
            Registrado por mas de 10 años!
          </div>
          <div class="badge tier1" v-else-if="user.registered.age > 5">
            Registrado por mas de 5 años!
          </div>
          <div class="badge" v-else>
            <i>No se encontraron insignias.</i>
          </div>
        </div>
      </div>
    </div>
    <div class="col-1 m-1 py-1 w-1 button male rounded" v-if="user.gender == 'male'">
        <div class="d-flex align-items-center" @click="masInfo = !masInfo">
            <span>Más información</span>
        </div>
    </div>
    <button class="col-1 m-1 py-1 w-1 button female rounded" v-else>
        <div class="d-flex align-items-center" @click="masInfo = !masInfo">
            <span>Más información</span>
        </div>
    </button>
  </div>
  </div>
</template>
  
<script>
export default {
  name: "users",
  props: {
    user: Object,
  },
  data(){
    return {
        masInfo: false
    }
  }
};
</script>
  
<style>
.badge {
  margin-bottom: 2px;
  padding: 5px;
  border-radius: 5px;
  width: 100%;
  color: #adb5bd;
}
.tier1 {
  border: 1px, solid, #2079ff;
  background-color: #5a9cff;
  color: white;
}
.tier2 {
  border: 1px, solid, #ffc107;
  background-color: #ffdd79;
  color: white;
}
.tier3 {
  border: 1px, solid, #ff1c07;
  background-color: #ff7979;
  color: white;
}
.button{
    height: 100%;
    color: white;
}
.male{
    border: 2px solid #2d81ff;
    background-color: #5a9cff;
}
.female{
    border: 2px solid #e48dff;
    background-color: #efbbff;
}
</style>