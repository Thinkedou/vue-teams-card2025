<script setup>
import {ref} from 'vue'
const props = defineProps({
    member:Object
})

// ou directement une variable car ici 
// nous ne sommes pas en asynchrone
// il n'y aura donc jamais de maj de cette valeur
const pictureUrlRiskyTest = ref(`url(src/assets/img/${props.member.profilePic})`)

</script>
<template>
    <div class="card">
    <div class="card-image" >
    </div>
    <div class="card-text">
      <span class="job">{{member.jobTitle}} {{ fullPictureUrl }}</span>
      <h2>{{member.firstName+ ' '+member.lastName}}</h2>
      <p>{{member.verbatim}}</p>
    </div>
    <div class="card-stats">
      <div class="stat">
        <div class="techno">Techno</div>
        <div class="level">⭐⭐⭐⭐</div>
      </div>
      <div class="stat border">
        <div class="techno">Techno</div>
        <div class="level">⭐⭐⭐</div>
      </div>
    </div>
  </div>
</template>
<style setup>
.card {
  display: grid;
  grid-template-columns: 300px;
  grid-template-rows: 210px 210px;
  grid-template-areas: "image" "text";
  border-radius: 15px;
  background: white;
  box-shadow: 5px 5px 15px rgba(0,0,0,0.9);
  font-family: roboto;
  text-align: center;
  margin:30px;
}
.card-image {
  grid-area: image;
  background: v-bind(pictureUrlRiskyTest);
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  background-size: cover;
}
.card-text {
  grid-area: text;
  margin: 25px;
}
.card-text .job {
  color: rgb(255, 7, 110);
}
.card-text p {
  color: grey;
  font-size:15px;
  font-weight: 300;
}
.card-text h2 {
  margin-top:0px;
  font-size:20px;
}
.card-stats {
  display: flex;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
  justify-content: center;
  background: rgb(255, 7, 110);
}
.card-stats .stat {
  padding:20px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  color: white;
}
.card-stats .border {
  border-left: 1px solid rgb(172, 26, 87);
}
.card-stats .techno{
  font-size:22px;
  font-weight: 500;
}

.card-stats .level{
  font-size:15px;
}



</style>
