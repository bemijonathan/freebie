<template>
<div>
  <div class="container-fluid pl-4">
    <div class="row pl-5 mb-5">
      <div class="col-sm p-0" v-for="(product, i) in itemThree" :key="i">
        <div class="d-flex flex-column bd-highlight mb-3">
          <div class="bd-highlight">
            <div class="rounded blank">
              <div class="strip m-auto">
                <img v-bind:src="product.images[0].img " />
              </div>
              <router-link :to="`cart/${product._id}`" >
              <button class="rounded text-center price mt-5 ml-3">{{'$'+ product.cost}}</button>
              </router-link>
            </div>
          </div>
          <div class="bd-highlight quest">
            <div class="d-flex flex-row bd-highlight justify-content-between align-items-center">
              <div class="bd-highlight hyde">{{product.name}}</div>
              <div class="pt-3 bd-highlight">
                <div class="d-flex flex-row bd-highlight">
                  <div class="bd-highlight">
                    <span class="tion">
                      <i class="fas fa-question"></i>
                    </span>
                  </div>
                  <div class="bd-highlight mt-1 number">
                    <p>(25)</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="bd-highlight blue">BLUE AND WHITE</div>
          <div class="bd-highlight mt-3">
            <div class="d-flex flex-row bd-highlight align-items-center">
              <router-link :to="`cart/${product._id}`" class="bd-highlight order">ORDER NOW</router-link>
              <div class="ml-1 bd-highlight now"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      
    };
  },
  computed:{
    itemThree(){
      return this.$store.state.itemThree.slice(0, 3);
    }
  },
  mounted(){
     this.$store.dispatch("getProductFromServer")
  }
};
</script>

<style>
</style>
