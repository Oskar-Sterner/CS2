<script setup lang="ts">
    const links = [
        { id: 1, href: "#home", text: "HOME"},
        { id: 2, href: "#about", text: "ABOUT"},
        { id: 3, href: "#game", text: "GAME"},
        { id: 4, href: "#contact", text: "CONTACT"},
    ];
</script>

<template>
    <nav>
      <a v-for="link in links" :key="link.id" :href="link.href" class="link">
        <span class="text">
          <span v-for="(letter, index) in link.text" :key="index" class="letter">
            {{ letter }}
          </span>
        </span>
      </a>
    </nav>
</template>
  
<style scoped>
    nav {
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: center;
      column-gap: 20px;
      height: 50px;
      font-weight: bold;
    }
  
    .link {
      font-size: 1.4em;
      position: relative;
      display: inline-block;
      transition: 300ms;
    }
  
    .link .text {
      position: relative;
      z-index: 1;
      display: inline-block;
      overflow: hidden;
      padding: 10px;
    }
  
    .letter {
      display: inline-block;
      transition: transform 0.3s ease-in-out;
    }
  
    .link:hover .letter:nth-child(odd) {
      transform: translateY(5%);
    }
  
    .link:hover .letter:nth-child(even) {
      transform: translateY(-5%);
    }
  
    .link:hover {
      cursor: pointer;
      text-shadow: 1px 0px 10px #00FF81;
      color: #00FF81;
    }
</style>  