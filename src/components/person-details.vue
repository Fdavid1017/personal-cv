<template>
  <div class="person-container">
    <div class="img-container">
      <img :src="imageLoc" />
    </div>
    <div class="details-container">
      <h1 class="color-main p-0 m-0">{{ name }}</h1>
      <p><b>Állampolgárság:</b> {{ nationality }}</p>
      <p><img src="../assets/icons/phone-call.svg" />{{ phoneNumber }}</p>
      <p><b>Születési idő:</b> {{ birthDate }}</p>
      <p><b>Nem:</b> {{ gender }}</p>
      <p>
        <img src="../assets/icons/email.svg" /><b>E-mail-cím:</b>{{ email }}
      </p>
      <p>
        <img src="../assets/icons/profile-user.svg" /><b>Github:</b>{{ github }}
      </p>
      <p><img src="../assets/icons/pin.svg" /><b>Cím:</b>{{ address }}</p>
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

.person-container {
  display: grid;
  grid-template-columns: auto 90%;
  grid-template-rows: 100%;
  grid-column-gap: 0px;
  grid-row-gap: 0px;

  .img-container {
    grid-area: 1 / 1 / 2 / 2;
    margin-right: 2em;

    img {
      border-radius: 50%;
      border: 0.25em solid #c6c6c6;
      width: 10em;
    }
  }

  .details-container {
    grid-area: 1 / 2 / 2 / 6;

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
