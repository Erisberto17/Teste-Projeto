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
            <div id="rows">

                <a href="" id="name" class="name"><img class="user" src="../Imgs/rope-circle.png" alt="">Promobank</a>
                <p id="start" class="start">24/09/1994</p>
                <div id="creds" class="creds">
                    <p><img src="../Imgs/check.png" alt="">12</p>
                    <p><img src="../Imgs/minus.png" alt="">34</p>
                    <p><img src="../Imgs/block.png" alt="">34</p>
                </div>
                <div id="fila" class="fila"> <meter></meter> </div>
                <div id="consultas" class="consultas"><progress style="width:50px;"></progress></div>
                <div id="acoes" class="acoes">
                    <img src="../Imgs/play-button.png" alt="">
                    <img src="../Imgs/Edit.png" alt="">
                    <img src="../Imgs/Trash.png" alt="">
                </div>
            </div>
        
        </div>
        
    </div>
</template>
<script>

export default {
    name:"Dashboard",
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
</style>