<template>
  <div id="app">
    <div class="box-resistor">
      <Resistor 
        :color1="faixa1"
        :color2="faixa2"
        :color3="faixa3"
        :color4="faixa4"
        :color5="faixa5"
      />

      <h2>{{ resistencia }} &#8486; {{ faixa5 | calculaTolerancia }}</h2>
    </div>

    <div class="box-forms">
      <div class="forms">
        <h3>Faixa 1</h3>
        <ul>
          <li><div class="color color-0" @click="faixa1update(0)"></div></li>
          <li><div class="color color-1" @click="faixa1update(1)"></div></li>
          <li><div class="color color-2" @click="faixa1update(2)"></div></li>
          <li><div class="color color-3" @click="faixa1update(3)"></div></li>
          <li><div class="color color-4" @click="faixa1update(4)"></div></li>
          <li><div class="color color-5" @click="faixa1update(5)"></div></li>
          <li><div class="color color-6" @click="faixa1update(6)"></div></li>
          <li><div class="color color-7" @click="faixa1update(7)"></div></li>
          <li><div class="color color-8" @click="faixa1update(8)"></div></li>
          <li><div class="color color-9" @click="faixa1update(9)"></div></li>
        </ul>
      </div>

      <div class="forms">
        <h3>Faixa 2</h3>
        <ul>
          <li><div class="color color-0" @click="faixa2update(0)"></div></li>
          <li><div class="color color-1" @click="faixa2update(1)"></div></li>
          <li><div class="color color-2" @click="faixa2update(2)"></div></li>
          <li><div class="color color-3" @click="faixa2update(3)"></div></li>
          <li><div class="color color-4" @click="faixa2update(4)"></div></li>
          <li><div class="color color-5" @click="faixa2update(5)"></div></li>
          <li><div class="color color-6" @click="faixa2update(6)"></div></li>
          <li><div class="color color-7" @click="faixa2update(7)"></div></li>
          <li><div class="color color-8" @click="faixa2update(8)"></div></li>
          <li><div class="color color-9" @click="faixa2update(9)"></div></li>
        </ul>
      </div>

      <div class="forms">
        <h3>Faixa 3</h3>
        <ul>
          <li><div class="color color-0" @click="faixa3update(0)"></div></li>
          <li><div class="color color-1" @click="faixa3update(1)"></div></li>
          <li><div class="color color-2" @click="faixa3update(2)"></div></li>
          <li><div class="color color-3" @click="faixa3update(3)"></div></li>
          <li><div class="color color-4" @click="faixa3update(4)"></div></li>
          <li><div class="color color-5" @click="faixa3update(5)"></div></li>
          <li><div class="color color-6" @click="faixa3update(6)"></div></li>
          <li><div class="color color-7" @click="faixa3update(7)"></div></li>
          <li><div class="color color-8" @click="faixa3update(8)"></div></li>
          <li><div class="color color-9" @click="faixa3update(9)"></div></li>
        </ul>
      </div>

      <div class="forms">
        <h3>Multiplicador</h3>
        <ul>
          <li><div class="color color-0" @click="faixa4update(0)"></div></li>
          <li><div class="color color-1" @click="faixa4update(1)"></div></li>
          <li><div class="color color-2" @click="faixa4update(2)"></div></li>
          <li><div class="color color-3" @click="faixa4update(3)"></div></li>
          <li><div class="color color-4" @click="faixa4update(4)"></div></li>
          <li><div class="color color-5" @click="faixa4update(5)"></div></li>
          <li><div class="color color-6" @click="faixa4update(6)"></div></li>
          <li><div class="color color-7" @click="faixa4update(7)"></div></li>
          <li><div class="color color-10" @click="faixa4update(10)"></div></li>
          <li><div class="color color-11" @click="faixa4update(11)"></div></li>
        </ul>
      </div>

      <div class="forms">
        <h3>Tolerância</h3>
        <ul>
          <li><div class="color color-1" @click="faixa5update(1)"></div></li>
          <li><div class="color color-2" @click="faixa5update(2)"></div></li>
          <li><div class="color color-5" @click="faixa5update(5)"></div></li>
          <li><div class="color color-6" @click="faixa5update(6)"></div></li>
          <li><div class="color color-7" @click="faixa5update(7)"></div></li>
          <li><div class="color color-8" @click="faixa5update(8)"></div></li>
          <li><div class="color color-10" @click="faixa5update(10)"></div></li>
          <li><div class="color color-11" @click="faixa5update(11)"></div></li>
        </ul>
      </div>

    </div>
  </div>
</template>

<script>
import Resistor from './components/Resistor.vue'

export default {
  name: 'App',
  components: {
    Resistor
  },
  data() {
    return {
      faixa1: 2,
      faixa2: 2,
      faixa3: 0,
      faixa4: 0,
      faixa5: 10,
      resistencia: '220'
    }
  },
  methods: {
    faixa1update (color) {
      this.faixa1 = color;
      this.updateResistencia();
    },
    faixa2update (color) {
      this.faixa2 = color;
      this.updateResistencia();
    },
    faixa3update (color) {
      this.faixa3 = color;
      this.updateResistencia();
    },
    faixa4update (color) {
      this.faixa4 = color;
      this.updateResistencia();
    },
    faixa5update (color) {
      this.faixa5 = color;
      this.updateResistencia();
    },
    updateResistencia() {
      this.resistencia = '' + this.faixa1 + this.faixa2 + this.faixa3 + this.calculaMultiplicador(this.faixa4);      
    },
    calculaMultiplicador(num) {
      if (num === 0) {
        return ''
      } else if (num === 1) {
        return '0'
      } else if (num === 2) {
        return '00'
      } else if (num === 3) {
        return 'K'
      } else if (num === 4) {
        return '0K'
      } else if (num === 5) {
        return '00K'
      } else if (num === 6) {
        return 'M'
      } else if (num === 7) {
        return '0M'
      } else if (num === 10) {
        return 'x0.1'
      } else if (num === 11) {
        return 'x0.01'
      }
    },
    calculaTolerancia(num) {
      if (num === 1) {
        return '+/- 1%'
      } else if (num === 2) {
        return '+/- 2%'
      } else if (num === 5) {
        return '+/- 0.5%'
      } else if (num === 6) {
        return '+/- 0.22%'
      } else if (num === 7) {
        return '+/- 0.01%'
      } else if (num === 8) {
        return '+/- 0.05%'
      } else if (num === 10) {
        return '+/- 5%'
      } else if (num === 11) {
        return '+/- 10%'
      }
    }
  },
  filters: {
    calculaTolerancia: (num) => {
      if (num === 1) {
        return '+/- 1%'
      } else if (num === 2) {
        return '+/- 2%'
      } else if (num === 5) {
        return '+/- 0.5%'
      } else if (num === 6) {
        return '+/- 0.22%'
      } else if (num === 7) {
        return '+/- 0.01%'
      } else if (num === 8) {
        return '+/- 0.05%'
      } else if (num === 10) {
        return '+/- 5%'
      } else if (num === 11) {
        return '+/- 10%'
      }
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;

  position: absolute;
  height: 100%;
  width: 100%;
}


.box-resistor {
  height: 100%;
  width: 40%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.box-forms {
  height: 100%;
  width: 40%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-left: 32px;
}

@media (max-width: 900px) {
  #app {
    flex-direction: column;
    height: auto;
  }

  .box-resistor {
    height: auto;
    width: 90%;
    margin: 32px 5%;
  }

  .box-forms {
    height: auto;
    width: 90%;
    margin: 32px 5%;
  }
}

.forms {
  width: 100%;
  background: #eee;
  padding: 16px 8px;
  margin-bottom: 32px;
}

.forms ul {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  flex-direction: row;
  list-style: none;
}

.color {
  background: blue;
  width: 30px;
  height: 30px;
  cursor: pointer;
  margin: 8px 8px 0 0;
}

.color-0 {
 background: black;
}
.color-1 {
  background: brown;  
}
.color-2 {
  background: red;
}
.color-3 {
  background: orange;
}
.color-4 {
  background: yellow;
}
.color-5 {
  background: green;
}
.color-6 {
  background: blue;
}
.color-7 {
  background: violet;
}
.color-8 {
  background: gray;
}
.color-9 {
  background: white;
}
.color-10 {
  background: gold;  
}
.color-11 {
  background: silver;  
}
</style>
