<template>
  <form @submit.prevent="onSubmit">
    <ul>
      <li>Входные данные</li>
      <hr>
      <li><h5>Рост</h5></li>
      <li><input v-model="height" min="0" placeholder="см" type="number"></li>
      <li><h5>Вес</h5></li>
      <li><input v-model="weight" min="0" placeholder="кг" type="number"></li>
      <li><h5>ППТ</h5></li>
      <li><input v-model="ppt" min="0" placeholder="кв.м" type="number"></li>
      <li><h5>СВ</h5></li>
      <li><input v-model="sv" min="0" placeholder="л/мин" type="number"></li>
      <li><h5>ЧСС</h5></li>
      <li><input v-model="chss" min="0" placeholder="уд/мин" type="number"></li>
      <li><h5>ДЗЛА</h5></li>
      <li><input v-model="dzla" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>АДср</h5></li>
      <li><input v-model="adsr" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>ЛАср</h5></li>
      <li><input v-model="lasr" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>ЦВД</h5></li>
      <li><input v-model="cvd" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>КДО</h5></li>
      <li><input v-model="kdo" min="0" placeholder="мл" type="number"></li>
      <li>
        <button type="submit">Вычисление</button>
      </li>
    </ul>
  </form>
</template>

<script>

export default {

  data() {
    return {
      height: '',
      weight: '',
      ppt: '',
      sv: '',
      chss: '',
      dzla: '',
      adsr: '',
      lasr: '',
      cvd: '',
      kdo: ''
    }
  },

  methods: {
    onSubmit() {
      const newCalcData = {
        userId: 1,
        height: this.height,
        weight: this.weight,
        ppt: this.ppt,
        sv: this.sv,
        chss: this.chss,
        dzla: this.dzla,
        adsr: this.adsr,
        lasr: this.lasr,
        cvd: this.cvd,
        kdo: this.kdo,
      }
      console.log(newCalcData);
      this.$parent.newCalc(newCalcData);
      // this.$emit('new-calc', newCalcData);
    }
  }
}

</script>


<style scoped>
form {
  display: flex;
  width: fit-content;
  border: 1px solid #ccc;
  padding-top: 2%;
  padding-bottom: 2%;
  padding-right: 3%;
}

input {
  width: 100%;
  margin-bottom: 2%;
}

button {
  width: 100%;
  justify-content: center;
  margin-bottom: 2%;
  margin-top: 2%;
}

li {
  display: flex;
  justify-content: space-between;
  min-width: 100px;
}

ul {
  list-style: none;
  margin-top: 2%;
  margin-bottom: 2%;
}

h5 {
  margin-top: 1%;
  margin-right: 2%;
  margin-bottom: 1%;
  font-style: normal;
  font-weight: normal;
}


</style>