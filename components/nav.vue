<template>
  <div class="nav-component">
    <div class="container nav">
      <div class="left">
        <h1><a href="/">Igor Martins</a></h1>
        <p>photographer</p>
      </div>
      <div class="right">
        <p><a href="#">overview</a></p>
        <p><a href="#">projects</a></p>
        <p><a href="#">social</a></p>
        <p><a href="#">about + contact</a></p>
      </div>
    </div>
  </div>
</template>
<style>
.nav-component .nav {
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    align-items: center;

    height: 20vh;
}
.nav-component .nav .left h1 {
    font-family: 'Pacifico', cursive;
    font-size: 30px;
}
.nav-component .nav .left a, .nav-component .nav .left a:hover {
    color: #795548 !important;
}
.nav-component .nav .left p {
    color: #777;
}
.nav-component .nav .right {
    display: flex;
    justify-content: space-between;
    flex-direction: row;
}
.nav-component .nav .right > p {
    margin: 10px;
    /* font-family: 'Montserrat', sans-serif; */
    font-family: 'Amatic SC', cursive;
    font-size: 25px;
}
</style>
