<template>
    <header id="header" class="header fixed-top d-flex align-items-center">
    <div class="container d-flex align-items-center justify-content-between">

      <div id="logo">
        <h1><a href="/" ><span>e</span>Pengaduan</a></h1>
        <!-- Uncomment below if you prefer to use an image logo -->
        <!-- <a href="/"><img src="assets/img/logoukk.svg" alt="" title="" /></a> -->
      </div>

      <nav id="navbar" class="navbar">
        <ul>
          <li><a class="nav-link scrollto" href="/">Halaman Utama</a></li>
          <li><a class="nav-link scrollto" href="/petugas">Data Petugas</a></li>
          <li><a class="nav-link scrollto" href="/masyarakat">Data Masyarakat</a></li>
          <li><a class="nav-link scrollto" href="/kategori">Kategori</a></li>
          <li><a class="nav-link scrollto" href="/pengaduan">Pengaduan</a></li>
          <li><a class="nav-link scrollto" href="" @click="logout">Logout</a></li>
        </ul>

      </nav><!-- .navbar -->

    </div>
  </header><!-- End Header -->
</template>

<script>
export default {
   name: 'navbar',
    computed : {
        isLoggedIn : function(){ return this.$store.getters.isLoggedIn}
    },
    methods:{
      logout:function(){
          this.$store.dispatch('logout')
          .then(response => {
            this.$store.commit('logout')
            localStorage.removeItem("Authorization")
            this.$router.push('/login')
          }).catch(error => {
        });
      },
  },
}
</script>