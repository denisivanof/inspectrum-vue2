<template>
<section class="staff">
  <div class="staff__items">
    <div class="staff__header">
      <h2 class="staff__title">Сотрудники</h2>
      <div class="staff__company">
        <img :src="company.img" alt="логотип компании">
        <div class="staff__company-title">{{company.name}}</div>
      </div>
    </div>
  </div>
</section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Staff",
  data:()=>({
    company: {
      name: 'ООО «Модуль»',
      img: require('../assets/company_logo.png')
    }
  })

}
</script>

<style scoped>
@import "../style/staff.scss";
</style>