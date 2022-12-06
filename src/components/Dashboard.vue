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

                <a href="" id="name" class="name"><img id="user" src="../Imgs/rope-circle.png">{{user.name}}</a>
                <p id="start" class="start">{{ user.start }}</p>
                
                <div id="creds" class="creds">
                    <p><img src="../Imgs/check.png">{{user.Creds.checked}}</p>
                    <p><img src="../Imgs/minus.png">{{user.Creds.wait}}</p>
                    <p><img src="../Imgs/block.png">{{user.Creds.blocked}}</p>
                </div>

                <div id="fila" class="fila"><meter></meter>  </div>
                <BarConsu :consulta="user.consultas"/>
                
                <div id="acoes" class="acoes">
                    <img  src="../Imgs/play-button.png">
                    <img src="../Imgs/Edit.png">
                    <img @click="deleteData(user.id)" src="../Imgs/Trash.png">
                </div> 
            </div>
        
        </div>
        
    </div>
</template>
<script>
    import BarConsu from "./BarConsu.vue"

export default {
    name:"Dashboard",
    
    components:{
        BarConsu
    },
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
    #user{
       max-width: 10px; max-height: 10px;
        
    }
    .creds img, .acoes img{
        width: 100px; height: 18px; 
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
</style>