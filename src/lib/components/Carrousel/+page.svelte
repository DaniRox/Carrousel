<script>
  export let img1 = "/images/Picsart1.jpg";
  export let img2 = "/images/Picsart2.jpg";
  export let img3 = "/images/Picsart3.jpg";
  export let img4 = "/images/Picsart4.jpg";
  export let img5 = "/images/Picsart5.jpg";
  export let img6 = "/images/Picsart6.jpg";
  export let img7 = "/images/Picsart7.jpg";
  export let img8 = "/images/Picsart8.jpg";
  export let img9 = "/images/Picsart9.jpg";
  
  let images = [
    img1, 
    img2, 
    img3, 
    img4, 
    img5, 
    img6, 
    img7, 
    img8, 
    img9, 
  ];
  
  let currentImageIndex = 0; 

  function nextImage() {
    currentImageIndex = (currentImageIndex + 1) % images.length;
  }
  
  function prevImage() {
    currentImageIndex = (currentImageIndex - 1 + images.length) % images.length;
  }

</script>


<style>
  .carousel { 
    position: relative; 
    width: 100%;
    height: 35rem;
    margin: 0 auto; 
    overflow: hidden;
  }
  
  .image-container { 
    display: flex; 
    transition: transform 0.5s ease; 
    width: 100%;
    height: 100%;
  } 
  
  .image-wrapper { 
    min-width: 100%;
    display: flex;
    align-items: flex-end;
  } 
  
  .image-wrapper img {
    width: 100%; 
    height: auto; 
  } 
  
  .arrows { 
    position: absolute; 
    top: 50%; 
    transform: translateY(-50%); 
    display: flex; 
    justify-content: 
    space-between; 
    width: 100%; 
  }
  
  .arrow { 
    background-color: none; 
    color: rgb(214, 214, 214); 
    border: none; 
    font-size: 3rem; 
    cursor: pointer; 
    padding: 2rem; 
  } 
  
  .arrow.left { 
    left: 0;
  } 
  
  .arrow.right { 
    right: 0;
  }

</style>


<div class="carousel">

  <div class="image-container" style="transform: translateX({-currentImageIndex * 100}%)"> 
    {#each images as image} 
      <div class="image-wrapper">
        <img src={image} alt="Carousel Image" />
      </div> 
    {/each}
  </div> 
  <div class="arrows"> 
    <button class="arrow left" on:click={prevImage}>&#10094;</button> 
    <button class="arrow right" on:click={nextImage}>&#10095;</button>
  </div>

</div>