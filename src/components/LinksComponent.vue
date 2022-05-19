<template>
  <div class="links-component">
    <p>SHARE</p>
    <img src="../assets/images/icon-facebook.svg" alt="icon-facebook" />
    <img src="../assets/images/icon-twitter.svg" alt="icon-twitter" />
    <img src="../assets/images/icon-pinterest.svg" alt="icon-pinterest" />
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang="scss">
//colors
$Very-Dark-Grayish-Blue: hsl(217, 19%, 35%);
$Desaturated-Dark-Blue: hsl(214, 17%, 51%);
$Grayish-Blue: hsl(212, 23%, 69%);
$Light-Grayish-Blue: hsl(210, 46%, 95%);

//font
$ff: "Manrope", sans-serif;
$font-size: 13px;
$fw-500: 500;
$fw-700: 700;

//mixins
@mixin desktop {
  @media screen and (min-width: 870px) {
    @content;
  }
}
.links-component {
  position: absolute;
  width: 100%;
  height: 5.4rem;
  left: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-inline: 2rem 7.5rem;
  border-radius: 0 0 8px 8px;
  background-color: $Very-Dark-Grayish-Blue;
  > p {
    color: $Grayish-Blue;
    font-size: 0.8rem;
    font-weight: $fw-700;
    letter-spacing: 4px;
  }
  > img {
    width: 1.4rem;
  }
  @include desktop {
    .links-component {
      width: 15rem;
      height: 3.5rem;
      left: 50%;
      top: -5.3rem;
      transform: translateX(-50%);
      border-radius: 8px;
      padding-inline: 2rem;
      box-shadow: 0 5px 13px 0 rgba(0, 0, 0, 0.25);
      &::after {
        position: absolute;
        bottom: -20%;
        content: "";
        left: 50%;
        border-bottom: 20px solid $Very-Dark-Grayish-Blue;
        border-left: 20px solid transparent;
        border-right: 20px solid transparent;
        transform: translate(-50%) rotate(180deg);
      }
    }
  }
}
</style>
