<script setup lang="ts"></script>

<template>
  

  <nav>
    <ul>
      <li>
        <NuxtLink to="/" exact-active-class="router-link-active">Home</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about" exact-active-class="router-link-active">About</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/contact" exact-active-class="router-link-active">Contact</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/pricing" exact-active-class="router-link-active">Pricing</NuxtLink>
      </li>
    </ul>
  </nav>

</template>

<style scoped>
  nav {
  padding: 20px;
  background-color: rgba(0, 220, 130, 0.1);
  margin-bottom: 20px;
}

ul {
  list-style: none;
  display: flex;
  gap: 20px;
  padding: 0;
  margin: 0;
}

a {
  color: #00dc82;
  text-decoration: none;
  font-weight: 500;
  transition: opacity 0.3s;
}

a:hover {
  opacity: 0.7;
}

a.router-link-active {
  text-decoration: underline;
}
</style>
