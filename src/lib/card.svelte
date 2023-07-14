<script lang="ts">
  export let name: string;
  export let image: string;
</script>

<div id="card">
  <div id="card-image">
    <img src={image} alt={name}>
  </div>
  <div id="card-title">
    <h2>{name}</h2>
  </div>
 </div>

 <style lang="css" scoped>
  #card {
    outline: 2px solid black;
    margin: 0 auto;
    margin-top: 50px;
    padding: 7px;
    position: relative;
    width: 27%;
    height: 50vh;
    text-align: center;
  }

  #card-image {
    width: 100%;
  }

  img {
    width: 300px;
    height: 300px;
  }

  #card-title {
    margin-top: 10px;
    font-size: 20px;
  }

 </style>
