<template>
  <div class="wrapper">
  <div class="badge" :style="'background: linear-gradient(-135deg, '+color+' 50%, '+darkColor+' 50%, '+color+' 100%); border:2px solid '+color+';'">
    <div class="badge__scene">
      <figure class="badge__image"> 
        <img :src="symbol" alt="">
        <!-- {{symbol}} -->
      </figure> 
    </div> 
  </div>
</div>
</template>

<script>
  export default {
    props:{
      symbol:String,
      color:String,
      darkColor:String
    },
    data() {
      return {
      };
    },
  };
</script>
<style lang="scss">
$badge_border_size: 2px;

// $color: #61DAFB;
// $color-dark: darken($color,10%);
$gray: #EEEEEE;

@mixin badge_control_initial_state() {
  --badge-control-transform-z: -1000px;
  --badge-control-scale: 0.5;
  --badge-control-icon-opacity: 0;
}

:root {
  // --badge-bar-color: #{$color};
  --badge-bar-height: 100%;

  @include badge_control_initial_state();
}

.wrapper {
  width: 90%;
  margin:10px;
  max-width: 100px;
}

.badge {
  position: relative;
  overflow: hidden;

  width: 100%;
  padding-top: calc(100% - #{$badge_border_size} * 2);
  
  // border: $badge_border_size solid $gray;
  border-radius: 50%;
  // background: linear-gradient(-135deg, #{$color} 50%, #{$color-dark} 50%, #{$color} 100%);

}

.badge__scene {
  width: 80%;
  height: 80%;

  border: inherit;
  border-radius: inherit;

  perspective: 1000px;
  transform-style: preserve-3d;

  position: absolute;
  top: 10%;
  left: 10%;
  z-index: 5;
} 

.badge__image {
  position: relative;
  width: 80%;
  height: 80%;
  margin: 0;
  transform: translate(-50%, -50%);
  position: absolute;
  max-width: 70%;
  max-height: 70%;
  top: 50%;
  left: 50%;
  filter:invert(1);
}

</style>
