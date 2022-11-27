<template>
    <nav>
        <h1>CAMPANHA</h1>
        <div class="opt">
            <a href=""><img src="../Imgs/Search.png" alt="Search"></a>
            <a href=""><img src="../Imgs/Bell.png" alt="Bell"></a>
            <a href=""><img src="../Imgs/chat.png" alt="Chat"></a>
            <a href=""><img src="../Imgs/share.png" alt="Share"></a>
            <a href=""><div id="user">
                <img src="../Imgs/user.png" alt="User">
                <p>Admin</p>
            </div></a>

        </div>
    </nav>
</template>
<script>
export default {
    name:"Nav"
}
</script>
<style scoped>
    img{
        max-width: 20px;
        min-height: 25px;
    }
    nav{
        height: 250px;
        display: flex;

        justify-content: space-between;
        padding: 10px 20px;
    }
    nav .opt{
        padding: 15px;
        margin: 0 15px;
    }
    nav .opt #user{
        background-color: rgb(238, 238, 238);
        border-radius: 5px;
        display: flex-box;
    }
</style>