<template>
  <section>
    <div class="image-container"></div>
    <div class="content">
      <h1>
        Shift the overall look and feel by adding these wonderful touches to
        furniture in your home
      </h1>
      <p>
        Ever been in a room and felt like something was missing? Perhaps it felt
        slightly bare and uninviting. I’ve got some simple tips to help you make
        any room feel complete.
      </p>
      <div class="user-details">
        <img
          class="profile-pic"
          src="./assets/images/avatar-michelle.jpg"
          alt="profile picture"
        />
        <div class="user">
          <p class="name">Michelle Appleton</p>
          <p class="date">28 Jun 2020</p>
        </div>
        <div class="share-button">
          <div
            :class="[show ? 'active-share' : '']"
            class="share-container"
            @click="showLinks"
          >
            <svg xmlns="http://www.w3.org/2000/svg" width="15" height="13">
              <path
                fill="#6E8098"
                d="M15 6.495L8.766.014V3.88H7.441C3.33 3.88 0 7.039 0 10.936v2.049l.589-.612C2.59 10.294 5.422 9.11 8.39 9.11h.375v3.867L15 6.495z"
              />
            </svg>
          </div>
          <links-component v-if="show"></links-component>
        </div>
      </div>
    </div>
  </section>
  <div class="attribution">
    Challenge by
    <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
      >Frontend Mentor</a
    >. Coded by <a href="#">Plora Dora</a>
  </div>
</template>

<script>
import LinksComponent from "./components/LinksComponent.vue";

export default {
  components: { "links-component": LinksComponent },
  data() {
    return {
      show: false,
    };
  },
  methods: {
    showLinks() {
      this.show = !this.show;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@400;700&display=swap");

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

html {
  box-sizing: border-box;
}

*,
*::after,
*::before {
  box-sizing: inherit;
  margin: 0;
  padding: 0;
}

body {
  height: 100vh;
  background-color: $Light-Grayish-Blue;
  font-family: $ff;
  font-size: 13px;
  display: grid;
  place-items: center;
  section {
    margin: auto;
    width: min(90%, 330px);
    background-color: #fff;
    border-radius: 8px;
    .image-container {
      border-radius: 8px 8px 0 0;
      background-image: url(./assets/images/drawers.jpg);
      background-position: center 20%;
      background-repeat: no-repeat;
      background-size: cover;
      height: 13rem;
    }
    .content {
      padding: 2rem 2rem 1.2rem 2rem;
      position: relative;
      h1 {
        font-size: 16px;
        color: $Very-Dark-Grayish-Blue;
        margin-bottom: 1rem;
        line-height: 23px;
      }
      > p {
        color: $Desaturated-Dark-Blue;
        font-weight: $fw-700;
        line-height: 20px;
        margin-bottom: 2.5rem;
      }
      .user-details {
        width: 100%;
        display: flex;
        align-items: center;
        .profile-pic {
          width: 3rem;
          border-radius: 50%;
          margin-right: 1rem;
        }
        .user {
          .name {
            font-size: 0.9rem;
            font-weight: $fw-700;
            color: $Very-Dark-Grayish-Blue;
            margin-bottom: 0.2rem;
          }
          .date {
            color: $Desaturated-Dark-Blue;
          }
        }
        .share-container {
          position: relative;
          width: 2.5rem;
          height: 2.5rem;
          border-radius: 50%;
          background-color: $Light-Grayish-Blue;
          z-index: 10;
          cursor: pointer;
          svg {
            pointer-events: none;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
          }
        }
        .active-share {
          background-color: $Light-Grayish-Blue;
          path {
            fill: $Very-Dark-Grayish-Blue;
          }
        }
        .share-button {
          margin-left: auto;
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
          }
        }
      }
    }
  }
  @include desktop {
    section {
      display: flex;
      width: 730px;
      .image-container {
        border-radius: 8px 0 0 8px;
        background-size: cover;
        background-position: 20% top;
        height: unset;
        flex-basis: 36%;
      }
      .content {
        padding: 2rem 2.5rem 2rem 2rem;
        flex-basis: 64%;
        h1 {
          margin-bottom: 0.9rem;
          font-size: 1.25rem;
          width: 90%;
        }
        > p {
          margin-bottom: 1.2rem;
        }
        .user-details {
          .share-button {
            position: relative;
            .active-share {
              background-color: $Very-Dark-Grayish-Blue;
              path {
                fill: #fff;
              }
            }
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
      }
    }
  }
}

.attribution {
  position: absolute;
  bottom: 0.7rem;
  left: 50%;
  transform: translateX(-50%);
  font-size: 9px;
  text-align: center;
}
.attribution a {
  color: hsl(228, 45%, 44%);
}
</style>
