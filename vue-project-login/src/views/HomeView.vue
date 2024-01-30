<template>
  <main class="main">
    <figure class="img-main">
      <img width="50vw" src="/icons/Login.gif" alt="">
    </figure><!--img-main-->

    <div class="title-main">
      <h2>Faça Seu Login Agora Mesmo!</h2>
    </div><!--title-main-->
  </main><!--main-->
</template>

<script>

export default{
  name: 'Home',
}
</script>


<style scoped>


.main{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}

.img-main img{
  width: 35vw;
}

.title-main h2{
  font-weight: 700;
  border-bottom: 1px solid black;
  border-right: 1px solid black;
  padding: 0px 10px 10px 0px;
}

</style>
