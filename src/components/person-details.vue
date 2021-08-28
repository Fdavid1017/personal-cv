<template>
  <div class="person-container">
    <div class="img-container">
      <div><img :src="imageLoc" /></div>
    </div>
    <div class="details-container">
      <h1 class="color-main p-0 m-0">{{ name }}</h1>
      <p><b>Állampolgárság:</b>&nbsp;{{ nationality }}</p>
      <p>
        <img src="../assets/icons/phone-call.svg" />
        <a :href="`tel: ${phoneNumber}`">{{ phoneNumber }}</a>
      </p>
      <p><b>Születési idő:</b>&nbsp;{{ birthDate }}</p>
      <p><b>Nem:</b>&nbsp;{{ gender }}</p>
      <p>
        <img src="../assets/icons/email.svg" /><b>E-mail-cím:</b>&nbsp;
        <a :href="`mailto: ${email}`">{{ email }}</a>
      </p>
      <p>
        <img src="../assets/icons/profile-user.svg" /><b>Github:</b> &nbsp;
        <a :href="github" target="_blank">{{ github }}</a>
      </p>
      <p><img src="../assets/icons/pin.svg" /><b>Cím:</b>&nbsp;{{ address }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "person-details",
  props: {
    imageLocation: {
      type: String,
      default: "",
    },
    name: {
      type: String,
      default: "",
    },
    nationality: {
      type: String,
      default: "",
    },
    phoneNumber: {
      type: String,
      default: "",
    },
    birthDate: {
      type: String,
      default: "",
    },
    gender: {
      type: String,
      default: "",
    },
    email: {
      type: String,
      default: "",
    },
    github: {
      type: String,
      default: "",
    },
    address: {
      type: String,
      default: "",
    },
  },
  computed: {
    imageLoc() {
      return require("../assets/" + this.imageLocation);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style";

@media screen and (max-width: 640px) {
  .person-container {
    grid-template-columns: 100%;
    grid-template-rows: repeat(2, auto);

    .img-container {
      grid-area: 1 / 1 / 2 / 2;
    }

    .details-container {
      grid-area: 2 / 1 / 3 / 2;
    }
  }
}

@media screen and (min-width: 640px) {
  .person-container {
    grid-template-columns: auto;
    min-width: 0;

    .img-container {
      grid-area: 1 / 1 / 2 / 2;
      margin-right: 2em;
    }

    .details-container {
      grid-area: 1 / 2 / 2 / 20;
    }
  }
}

.person-container {
  display: grid;
  grid-column-gap: 0px;
  grid-row-gap: 0px;

  white-space: -moz-pre-wrap !important;
  white-space: -o-pre-wrap;
  white-space: pre-wrap;
  word-wrap: break-word;
  word-break: break-all;
  white-space: normal;

  .img-container {
    max-width: 100%;
    display: flex;
    justify-content: center;

    img {
      border-radius: 50%;
      border: 0.25em solid #c6c6c6;
      width: 10em;
    }
  }

  .details-container {
    p {
      display: flex;
      align-items: center;

      img {
        width: 1.2em;
        margin-right: 0.3em;
      }
    }
  }
}
</style>
