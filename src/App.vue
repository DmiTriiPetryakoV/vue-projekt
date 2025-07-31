<template>

    <p>ToDo-List</p>
    <div id="BoxApp">
      <div id="section">
      <input id="UserTasks" placeholder="Сюда задачу" maxlength="40" v-model="newTasks"/>
      <button id="AddTasks" @click="AddTasks">Добавить задачу</button>
      </div>
      <div id="BoxApp2">
        <div id="boxTasks" v-for="(task, index) in tasks" :key="index">
          {{task}}
        </div>
      
      </div>
    </div>


</template>

<script>
export default {
  data(){
    return{
    name: 'App',
    newTasks:'',
    tasks:[],
};
},
methods:{
AddTasks(){
  if(this.newTasks.trim() !== ''){
  this.tasks.push(this.newTasks);
  this.newTasks = ''

  }
}
}
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap");
:root{
  --white:#ffffffea;
  --green:#d1e7dd;
  --blue:#3c6ddfd2;
  --tasks:rgb(4, 0, 131);
}
html{
  width:100%;
  height:100%;
}
body{
  width:100%;
  height:100%;
  background:var(--white);
  margin:0;
  color:var(--blue);
  font-family:'Poppins';
  color: var(--blue);
}
#App{
  display: grid;
  grid-template-columns:repeat(1,1fr);
  grid-template-rows:20% 80%;
  align-items: center;
  justify-content: center;
  justify-items: center;
  width:100%;
  height:100%;
}
#BoxApp{
  width:95%;
  height:95%;
  background:var(--green);
  display: flex;
  border:2px solid var(--blue);
  box-shadow:var(--blue) 2px 2px 4px;
  border-radius:15px;
  display: grid;
  grid-template-rows:15% 85%;
  align-items: center;
  overflow:scroll;
}
#UserTasks{
  height:3.2rem;
  width:100%;
  border-radius:10px;
  border:3px solid var(--blue);
  font-size:1.25rem;
  color:var(--blue);
  grid-row:1;
  grid-column:1;
  margin:2%;
}
p{
  font-size:5.5rem;
}
#AddTasks{
  width:10rem;
  height:3rem;
  border:2px solid var(--blue);
  border-radius:12px;
  grid-row:1;
  font-size:1.1rem;
  font-family:'Poppins';
  color: var(--blue);
  margin-left:10%;
  margin-top:5%;
}
#BoxApp2{
  width:100%;
  height:100%;

}
#section{
  display: grid;
  grid-template-columns:70% 30%;
}
#boxTasks{
  width:70%;
  height:5rem;
  background:var(--blue);
  display: flex;
  font-size:1.2rem;
  color:black;
  border:2px solid var(--tasks);
  border-radius:20px;
  margin:1%;
  align-items:center;
}
@media(max-width:480px){
  #boxTasks{
    font-size:1rem;

  }
}

</style>
