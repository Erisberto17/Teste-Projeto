<template>
    <div id="table">
        <div id="head">
            <p  class="name">Nome</p>
            <p  class="start">Inicio</p>
            <p  class="creds">Credenciais</p>
            <p  class="fila">Em fila</p>
            <p  class="consultas">Consultas</p>
            <p  class="acoes">Ações</p>
        </div>
        <div id="body">
            <div id="rows" v-for="user in users" :key="user.id">

                <a href="" id="name" class="name"><img class="user" src="../Imgs/rope-circle.png" alt="">{{user.name}}</a>
                <p id="start" class="start">{{ user.start }}</p>
                <div id="creds" class="creds">
                    <p><img src="../Imgs/check.png" alt="">{{user.Creds.checked}}</p>
                    <p><img src="../Imgs/minus.png" alt="">{{user.Creds.wait}}</p>
                    <p><img src="../Imgs/block.png" alt="">{{user.Creds.blocked}}</p>
                </div>
                <div id="fila" class="fila"> <meter ></meter> </div>
                <div id="consultas" class="container"> <div class="progress-bar"></div></div>
                <div id="acoes" class="acoes">
                    <img  src="../Imgs/play-button.png" alt="">
                    <img src="../Imgs/Edit.png" alt="">
                    <img @click="deleteData(user.id)" src="../Imgs/Trash.png" alt="">
                </div> 
            </div>
        
        </div>
        
    </div>
</template>
<script>

export default {
    name:"Dashboard",
    data(){
        return{
            users: null

        }
    },
    methods:{
        async getData(){
            const req = await fetch("http://localhost:3000/users");

            const res = await req.json()

            this.users = res
            console.log(res)



        },
        async deleteData(id){
            const req = await fetch(`http://localhost:3000/users/${id}`, {
                method: "DELETE"
            });
            this.getData();
        }
    },
    mounted(){
        this.getData();
    }
}
</script>
<style scoped>
    .user{
        width: 10px; height: 10px;
        margin-right: 8px;
        
    }
    .creds img, .acoes img{
        width: 17px; height: 18px; 
        margin-left: 10px;
    
    }
    #rows .creds ,#rows .acoes{
        display: flex;
    }
    
    #table #head{
        display: flex;
        align-items: center;        
        padding: 2px;
        justify-content: space-between;
        text-align: center;
    }
    
    #table #body #rows{
        border: 1px solid rgba(85, 85, 85, 0.247);
        display: flex;
        align-items: center;
        padding: 0 5px;
        justify-content: space-between;
        text-align: center;
    }
    .container {
        height: 25px;
        background-color: #CCC;
        position: relative;
    }
    .container .progress-bar{
       position: absolute;
       height: 100%;
       background-color: #0fd439;
       animation: progress-animation 5s infinite;
    }
    @keyframes progress-animation{
        0% { width: 0%; } 
        100% { width: 100%}
    }
</style>