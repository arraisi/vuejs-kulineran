<template>
  <div class="hero">
    <!-- desktop -->
    <div class="d-none d-md-block">
      <div class="row mt-4">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-cenntera align-self-center">
              <h2>
                <strong>Delicious Food Menu, </strong><br />
                in Your Gadget
              </h2>
              <p>Segera pilih dan pesan makanan dan minuman favorit Kamu</p>
              <router-link to="/food" class="btn btn-lg btn-success">
                <b-icon-arrow-right></b-icon-arrow-right> Pesan
              </router-link>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="../assets/hero.png" width="100%" />
        </div>
      </div>
    </div>

    <!-- mobile -->
    <div class="d-ms-block d-md-none">
      <div class="row mt-4">
        <div class="col-md-6 mb-3">
          <img src="../assets/hero.png" width="100%" />
        </div>
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-cenntera align-self-center">
              <h2>
                <strong>Delicious Food Menu, </strong><br />
                in Your Gadget
              </h2>
              <p>Segera pilih dan pesan makanan dan minuman favorit Kamu</p>
              <button class="btn btn-lg btn-success">
                <b-icon-arrow-right></b-icon-arrow-right> Pesan
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style>
</style>