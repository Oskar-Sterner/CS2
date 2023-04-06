<script setup lang="ts">
    let text1: string = "CS2 (Counter-Strike 2) is a competitive first-person shooter game that builds on the legacy of the popular CS:GO game. With a cutting-edge graphical engine and physics-based mechanics, CS2 immerses players in intense tactical battles with an unprecedented level of realism. Choose your side and work with your team to outsmart and outgun your opponents in fast-paced, skill-based gameplay. With an expanded arsenal of weapons, maps, and game modes, CS2 offers a new level of depth and challenge for both veteran and new players alike.";
    let text2: string = "CS2 also known as Counter-Strike 2, is a first-person shooter game that takes the competitive legacy of its predecessor, CS:GO, to the next level. The game features a state-of-the-art graphical engine and physics-based mechanics that provide players with a realistic and immersive tactical experience. Whether you choose to play on the terrorist or counter-terrorist side, you must work with your team to outsmart and outgun your opponents in a fast-paced and skill-based gameplay. With an extensive selection of weapons, maps, and game modes, CS2 offers a depth of content and challenge suitable for both new and experienced players.";
    let text3: string = "Experience the next level of competitive first-person shooting with CS2, also known as Counter-Strike 2. This game builds upon the success of its predecessor, CS:GO, with cutting-edge graphics and physics-based mechanics that provide an unparalleled level of realism. With the option to play on the terrorist or counter-terrorist team, you and your teammates must utilize your skills and outsmart your opponents to win. CS2 boasts an extensive selection of weapons, maps, and game modes that provide a new level of depth and challenge suitable for both seasoned players and newcomers to the series.";

    let randomText = [text1, text2, text3][Math.floor(Math.random() * 3)].replace(/CS2/g, '<span>CS2</span>');


    let heroImage = document.querySelector<HTMLDivElement>('.hero-image');
    let diamond = document.querySelector<HTMLDivElement>('.diamond');

    heroImage?.addEventListener('mouseenter', () => {
      diamond?.classList.add('hover-effect');
    });

    heroImage?.addEventListener('mouseleave', () => {
      diamond?.classList.remove('hover-effect');
    });
</script>

<template>
    <div class="hero">
      <div class="hero-title">
        <h1>CS2</h1>
        <p class="hero-text" v-html="randomText"></p>
      </div>
      <div class="hero-image">
        <img src="../assets/characters.png" alt="Two illustrated men">
        <div class="diamond"></div>
        <div class="diamond-2"></div>
        <div class="diamond-3"></div>
        <div class="diamond-4"></div>
      </div>
    </div>
  </template>
  
  <style scoped>
  .hero {
    display: flex;
    padding: 50px 0;
    align-items: flex-start;
    justify-content: space-evenly;
  }

  .hero-title {
    display: flex;
    flex-direction: column;
    width: 30%;
    z-index: 2;
  }
  
  .hero-title h1 {
    margin-block-start: 1.15em;
    margin-block-end: 0.27em;
    font-size: 6rem;
    font-weight: bold;
  }

  .hero-text {
    width: 100%;
    /*text-shadow: rgba(255,255,255,1) 0px 0px 10px;*/
    font-weight: bold;
  }

  ::v-deep span {
    color: #00ff80;
    text-shadow: rgba(0,255,128,1) 0px 0px 10px;
  }
  
  .hero-image {
    position: relative;
    margin-top: 50px;
  }
  
  .hero-image img {
    width: 500px;
    position: relative;
    z-index: 2;
    transform: translate(-10%, 20%);
  }
  
  .diamond {
    position: absolute;
    width: 360px;
    height: 360px;
    background-color: #00FF81;
    z-index: 1;
    border-radius: 20px;
    transform: translate(20%, -80%) rotate(45deg);
    transition: 300ms;
  }
  .hero-image:hover .diamond {
    -webkit-box-shadow:0px 0px 50px 0px #00FF81;
    -moz-box-shadow: 0px 0px 50px 0px #00FF81;
    box-shadow: 0px 0px 50px 0px #00FF81;
    transform: translate(20%, -80%) rotate(135deg);
  }

  .hero-image:hover .diamond:hover-effect {
    -webkit-box-shadow:0px 0px 50px 0px #00FF81;
    -moz-box-shadow: 0px 0px 50px 0px #00FF81;
    box-shadow: 0px 0px 50px 0px #00FF81;
    transform: translate(20%, -80%) rotate(135deg);
  }

  .diamond-2 {
    position: absolute;
    width: 360px;
    height: 360px;
    background-color: #00552c;
    z-index: 1;
    border-radius: 20px;
    transform: translate(-280%, -60%) rotate(45deg);
    -webkit-box-shadow:0px 0px 50px 0px rgba(0,85,44,1);
    -moz-box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
    box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
    animation: wiggle 4s ease-in-out infinite;
  }

  .diamond-3 {
    position: absolute;
    width: 130px;
    height: 130px;
    background-color: #00552c;
    z-index: 1;
    border-radius: 20px;
    transform: translate(-315%, -50%) rotate(45deg);
    -webkit-box-shadow:0px 0px 50px 0px rgba(0,85,44,1);
    -moz-box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
    box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
  }

  .diamond-4 {
    position: absolute;
    width: 60px;
    height: 60px;
    background-color: #00552c;
    z-index: 1;
    border-radius: 20px;
    transform: translate(-515%, -380%) rotate(45deg);
    -webkit-box-shadow:0px 0px 50px 0px rgba(0,85,44,1);
    -moz-box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
    box-shadow: 0px 0px 50px 0px rgba(0,85,44,1);
  }

  </style>