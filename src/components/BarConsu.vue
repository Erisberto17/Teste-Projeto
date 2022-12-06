<template>
    <div>
        <div class="box">
            <div class="box-circle">
                <svg>
                    <circle cx="17" cy="17" r="17"></circle>
                    <circle id="barProg" cx="17" cy="17" r="17"></circle>
                </svg>
            </div>
        </div>
    </div>
</template>
<style scoped>

circle{
    width: 150px; height: 150px;
    fill: none;
    stroke: black;
    stroke-width: 5;
    transform:translate(5px, 5px);
    stroke-dasharray: 106;
    stroke-dashoffset: 106;
    
  }
  circle:nth-child(1){
    stroke-dashoffset: 0;
    stroke: #111;
  }
  circle:nth-child(2){
    transition: stroke-dashoffset 5s;
    stroke: dodgerblue;
  }
 

</style>
<script>
    export default {
        name:"BarConsu",
        props:{
            consulta: String
        },
        data(){
            return{
                consulta: this.consulta
            }
        },
        methods:{
            progBar() {
                const bar = document.querySelector("#barProg");
                const num = this.consulta;
                bar.style.strokeDashoffset = 106 - (106 * num) / 100;

            }
        },
        mounted(){
            this.progBar()
        }
    }
        </script>