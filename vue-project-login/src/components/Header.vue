<template>
  <div>
    <header class="header">
      <figure class="img-header">
        <img width="50vw" src="/icons/logo.png" alt="">
      </figure><!--img-header-->

      <nav class="nav">
        <ol>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/login">Login</router-link></li>
        </ol>
      </nav><!--nav-->
    </header><!--header-->
    <router-view></router-view>
  </div>
</template>

<script>

export default{
  name: 'Header',
}

</script>


<style scoped>

.header{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  padding: 1% 0;
}

.nav > ol{
  display: flex;
  gap: 50px;
}
.nav ol li{
  list-style-type: none;
  background-color: blueviolet;
  padding: 10px 20px;
  border-radius: 10px;
}

.nav ol li a{
  text-decoration: none;
  color: #fff;
  font-weight: 800;
}

.nav ol li:hover{
  transition: 0.3s;
  transform: scale(1.1);
}

</style>