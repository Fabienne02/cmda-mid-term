<!-- 
- Border img nog niet goed gexporteerd
- Content uit json halen  -->
<template>
  <section class="CardSwitch">
    <h1>1.2 Competenties</h1>
    <div class="CardCon" :class="[isChecked ? 'bgBlack' : 'bgYellow']">
      <div>
        <h4 style="margin-bottom:0;">Beroeps specifieke kerncompetentie</h4>
        <p>Hebben betrekking op inhoudelijke geschiktheid in de beroepspraktijk en de situaties die zich daar voordoen
        </p>
        <h2>Principes</h2>
        <h3 v-if="isChecked">Nieuw</h3>
        <h3 v-else>Oud</h3>
        <ul v-if="isChecked">
          <li>Multidisciplinair samenwerken </li>
          <li>Manifesteren en presenteren </li>
          <li>Initiëren organiseren en regisseren</li>
          <li>Ontwikkelen en reflecteren</li>
          <li>Onderzoeken</li>
        </ul>
        <ul v-else>
          <li>Multidisciplinair samenwerken </li>
          <li>Manifesteren en presenteren </li>
          <li>Initiëren organiseren en regisseren</li>
          <li>Ontwikkelen en reflecteren</li>
          <li>Onderzoeken</li>
        </ul>
        <label class="switch">
          <input type="checkbox" @click="CardConColor">
          <span class="slider" :class="[isChecked ? 'CBlack' : 'Cwhite']"></span>
        </label>
      </div>
      <img
        src="https://images.prismic.io/cmd-midterm/663bf539-c574-417c-97e6-7b35177b4144_CardCon-Border.png?auto=compress,format"
        class="cardBorder" />
    </div>
  </section>
</template>

<script>
export default {
  name: 'CardSwitch',
  data() {
    return {
      isChecked: false
    }
  },
  methods: {
    CardConColor() {
      this.isChecked = !this.isChecked
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700;800&display=swap');

.CardCon {
  font-family: 'Open Sans';
  font-weight: 500;
  height: 35em;
  width: 30em;
  margin-left: 2em;
  margin-top: 3em;
}

.CardSwitch h1 {
  margin-left: 1em;
  font-family: 'Open Sans';
  font-weight: 700;
  font-size: 1.7em;
}

.cardBorder {
  height: 36em;
  width: 31.5em;
  margin-left: -0.6em;
  margin-top: -33.2em;
}

.bgYellow {
  background-color: #FFF021;
  border: 2px solid #000000;
  -webkit-transition: .2s;
  transition: .2s;
}

.bgBlack {
  background-color: #000000;
  color: #ffffff;
  border: 2px solid #000000;
  -webkit-transition: .2s;
  transition: .2s;
}

.CBlack {
  color: #000000;
}

.CardCon div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  margin-left: 1em;
  padding: 1em;
}

.CardCon h3 {
  font-weight: 700;
  font-size: 2rem;
  margin: 0.2em 0 0.2em 0;
}

.Cardcon div h4 {
  font-size: 1rem;
  font-weight: 700;
}

.CardCon h2 {
  font-weight: 400;
  margin: 0;
  margin-top: 0.5em;
}

.CardCon ul {
  list-style: none;
  padding: 0;
  margin-bottom: 1.8em;
}

.CardCon ul li {
  margin-bottom: 1em;
}

.CardCon ul li:before {
  content: "";
  float: left;
  width: 0;
  height: 0;
  display: inline-block;
  border: 9px solid transparent;
  border-left-color: black;
}

.CBlack~.CardCon ul li:before {
  border-left-color: #FFF021;
}

.switch {
  position: relative;
  display: inline-block;
  width: 5.5em;
  height: 2em;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgb(0, 0, 0);
  -webkit-transition: .4s;
  transition: .4s;
  border-radius: 3px;
}

.slider:before {
  position: absolute;
  content: "Nieuw";
  font-size: 0.8em;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 60%;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
  border-radius: 2.5px;
}

input:checked+.slider {
  background-color: #ffffff;
}

input:checked+.slider:before {
  background-color: #FFF021;
}

input:checked+.CardCon {
  background-color: #000000;
}

input:checked+.slider:before {
  content: "Oud";
  -webkit-transform: translateX(68%);
  -ms-transform: translateX(68%);
  transform: translateX(68%);
}
</style>