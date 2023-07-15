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
    /* outline: 2px solid black; */
    margin: 0 auto;
    margin-top: 50px;
    padding: 7px;
    position: relative;
    width: 23%;
    height: 50vh;
    text-align: center;
    background-color: #5ABFE5;
    border-radius: 8px;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.5);
    /* animation: card-rotate 10s ease-in 5; */
  }

  #card-image {
    /* width: 100%; */
    /* background-color: #800784; */
    /* border-radius: 100%; */
    padding: 5px;
  }

  img {
    width: 300px;
    height: 300px;
    border-radius: 8px;
  }

  #card-title {
    margin-top: 10px;
    font-size: 20px;
  }

  @keyframes card-rotate {
    0% {
      transform: rotateY(0deg);
    }

    100% {
      transform: rotateY(360deg);
    }
  }

 </style>
