<template>
  <div class="content">
    <person-details
      image-location="img.jpg"
      name="Fábry Dávid"
      nationality="magyar"
      phone-number="(+36) 306886695"
      birth-date="1999/10/17"
      gender="férfi"
      email="fdavid1017@gmail.com"
      github="https://github.com/Fdavid1017"
      address="Gagarin út 10., 3151 Rákóczibánya (Magyarország)"
    />

    <panel title="Oktatás és képzés">
      <panel title="Felsőoktatási szakképzés" :secondary="true">
        <p><b>Eszterházy Károly Egyetem</b> [ 01/09/2018 – 30/01/2021 ]</p>
        <p class="muted"><b>Szakirány(ok):</b> Programtervező informatikus</p>
      </panel>
      <panel title="Érettségi bizonyítvány " :secondary="true">
        <p>
          <b>
            Salgótarjáni Szakképzèsi Centrum Stromfeld Aurél Szakgimnáziuma És
            Szakközépiskolája
          </b>
          [ 01/09/2014 – 15/06/2018 ]
        </p>
        <p class="muted"><b>Szakirány(ok):</b> Informatikai rendszergazda</p>
      </panel>
    </panel>

    <panel title="nyelvtudás">
      <p class="muted">Anyanyelv(ek):</p>
      <p>
        <b>magyar</b>
      </p>
      <p class="muted">További nyelv(ek):</p>
      <panel title="angol" :secondary="true">
        <p>
          <b class="uppercase">Hallás utáni értés</b> B1
          <b class="uppercase">Olvasás</b> B1 <b class="uppercase">Írás</b> B1
        </p>
        <p>
          <b class="uppercase">Folyamatos beszéd</b> B1
          <b class="uppercase">Társaégás</b> B1
        </p>
      </panel>
    </panel>

    <panel title="Digitális készségek">
      <div class="m-0 p-0">
        {{ formattedDigitalSkills }}
      </div>
    </panel>

    <panel title="Vezetői engedély"> <b>Vezetői engedély:</b> B </panel>

    <panel title="Hobbik">
      <b>Hobbik</b>
      <p>Videó játékok</p>
      <p>Játékok, weboldalak és különféle alkalmazások fejlesztése</p>
    </panel>
  </div>
</template>

<script>
import PersonDetails from "@/components/person-details";
import Panel from "@/components/panel";

export default {
  name: "main-content",
  components: { Panel, PersonDetails },
  data() {
    return {
      digitalSkills: [
        "JavaScript",
        "MySQL",
        "PHP",
        "Vue.js",
        "C#",
        "Python",
        "Django",
        "Unity",
        "Windows",
        "Bootstrap 3/4",
        "HTML",
        "GIT (Github)",
        "CSS (SASS)",
        "OOP",
        "React",
        "MVC",
        "Spring Boot",
        "Java",
        "Nuxt.js",
        "Python Flask",
      ],
    };
  },
  computed: {
    formattedDigitalSkills() {
      if (this.digitalSkills.length < 1) {
        return "";
      }

      let formatted = this.digitalSkills[0];
      for (let i = 1; i < this.digitalSkills.length; i++) {
        formatted += ` / ${this.digitalSkills[i]}`;
      }

      return formatted;
    },
  },
};
</script>

<style lang="scss" scoped>
.content {
  background-color: white;
  padding: 3em;

  .panel {
    margin-bottom: 3em;

    .muted {
      opacity: 85%;
    }
  }
}
</style>
