<template>
  <form @submit.prevent="onSubmit">
    <ul>
      <li>Преднагрузка</li>
      <hr>
      <li><h5>ЦВД</h5></li>
      <li><input v-model="height" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>ДЗЛА</h5></li>
      <li><input v-model="weight" min="0" placeholder="мм рт. ст." type="number"></li>
      <li><h5>КДО</h5></li>
      <li><input v-model="ppt" min="0" placeholder="мл" type="number"></li>
      <li><h5>ИКДО</h5></li>
      <li><input v-model="sv" min="0" placeholder="мл/ м2" type="number"></li>
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
      sv: ''
    }
  },

  methods: {
    onSubmit() {
      this.height.trim();
      this.weight.trim();
      this.ppt.trim();
      this.sv.trim();
      this.chss.trim();
      this.dzla.trim();
      this.adsr.trim();
      this.lasr.trim();
      this.cvd.trim();
      this.kdo.trim();

      const preloadCalc = {
        userId: 1,
        height: this.height,
        weight: this.weight,
        ppt: this.ppt,
        sv: this.sv,
      }
      this.$emit('preload-calc', preloadCalc)
      this.height = ''
      this.weight = ''
      this.ppt = ''
      this.sv = ''
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