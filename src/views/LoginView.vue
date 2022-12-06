<template>
  <div class="box">
    <div class="box-circle">
      <svg>
        <circle cx="70" cy="70" r="70"></circle>
        <circle id="barProg" cx="70" cy="70" r="70"></circle>
      </svg>
      <div class="number">
        70%
      </div>
    </div>
  </div>
</template>
<style scoped>

  .box{
    position:absolute ;
    top: 50%; left: 50%;
    background: rgba(0, 0, 0, 0.6);
    border-radius: 6px;
    padding: 4px;
  }
  .box-circle svg{
    width: 150px; height: 150px;
    position: relative;
  }
  circle{
    width: 150px; height: 150px;
    fill: none;
    stroke: black;
    stroke-width: 5;
    transform:translate(5px, 5px);
    stroke-dasharray: 440;
    stroke-dashoffset: 440;
  }

  circle:nth-child(1){
    stroke-dashoffset: 0;
    stroke: #111;
  }
  circle:nth-child(2){
    transition: stroke-dashoffset 1s;
    stroke: dodgerblue;
  }

</style>
<script>
export default {
  data(){
    return{

    }
  },
  methods:{
    async progBar(){
      const num = 80;
      const bar = document.querySelector("#barProg");
      bar.style.strokeDashoffset = 440 - (440 * num) / 100;

    }
  },
  mounted(){
    this.progBar()
  }
}
</script>
