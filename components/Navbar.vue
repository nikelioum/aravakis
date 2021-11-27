<template>
    <div>
    <div class="container-fluid">
    <div class="row">
    <nav class="navbar navbar-expand-lg navbar-light fixed-top bg-white">
  <div class="container-fluid">
    <a class="navbar-brand" href="/"><img src="~/assets/images/logo.png"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mx-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <NuxtLink to="/services" class="nav-link">ΥΠΗΡΕΣΙΕΣ</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/portfolio" class="nav-link">ΔΕΙΓΜΑΤΑ ΚΑΤΑΣΚΕΥΩΝ</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/about" class="nav-link">Η ΕΤΑΙΡΕΙΑ ΜΑΣ</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/blog" class="nav-link">DIY ΚΑΝΤΟ ΜΟΝΟΣ ΣΟΥ</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/contact" class="nav-link">ΕΠΙΚΟΙΝΩΝΙΑ</NuxtLink>
        </li>
           <li class="nav-item ms-auto">
               <a class="btn btn-outline-dark btn-phone-dark" href="tel:2102020220">
                   ΚΑΛΕΣΤΕ ΜΑΣ ΓΙΑ ΠΡΟΣΦΟΡΑ
               </a>
           </li>
       </ul>
    </div>
  </div>
</nav>
</div>
</div>
    </div>
</template>


<style>

.swiper-pagination.swiper-pagination-clickable.swiper-pagination-bullets.swiper-pagination-vertical[data-v-581a1316] {
    background-color: rgb(184 187 193) !important;
    padding: 10px;
}

.swiper-pagination-vertical.swiper-pagination-bullets .swiper-pagination-bullet, .swiper-vertical>.swiper-pagination-bullets .swiper-pagination-bullet {
    margin: 6px 0;
    margin: var(--swiper-pagination-bullet-vertical-gap,6px) 0;
    display: block;
    background-color: black !important;
    padding: 5px !important;
}

@import url('https://fonts.googleapis.com/css2?family=Ubuntu+Mono&display=swap');

a.nav-link {
    font-family: 'Ubuntu Mono', monospace;
}

a.btn.btn-outline-dark.btn-phone-dark {
    font-family: 'Ubuntu Mono', monospace;
}

a.nuxt-link-active {
  font-weight: bold;
}

a.btn.btn-outline-dark.btn-phone-dark {
    border-top: none;
    border-left: none;
    border-right: none;
    border-radius: 0;
}
</style>

