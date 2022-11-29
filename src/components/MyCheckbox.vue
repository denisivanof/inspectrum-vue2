<template>
  <div class="checkbox">
    <input class="custom-checkbox"
           type="checkbox"
           :id="name"
           :name="name"
           :checked="checked"
           @change="$emit('change', $event.target.checked)"
    >
    <label :for="name"></label>
  </div>
</template>

<script>
export default {
  name: "MyCheckbox",
  model: {
    prop: 'checked',
    event: 'change'
  },
  props:{
    checked: Boolean,
    name: String
  }
}
</script>

<style scoped>

.checkbox{
  width: 16px;
  height: 16px;
}
.custom-checkbox {
  position: absolute;
  z-index: -1;
  opacity: 0;
}
.custom-checkbox+label {
  display: inline-flex;
  align-items: center;
  user-select: none;
  width: 16px;
  height: 16px;
}
.custom-checkbox+label::before {
  content: '';
  display: inline-block;
  width: 14px;
  height: 14px;
  border: 1px solid #E31243;
  border-radius: 2px;
  background-repeat: no-repeat;
  background-position: center center;
  background-size: 50% 50%;
}
.custom-checkbox:not(:disabled):not(:checked)+label:hover::before {
  border-color: #E31243;
}
.custom-checkbox:not(:disabled):active+label::before {
  background-color: #ea748f;
  border-color: #ea748f;
}
.custom-checkbox:focus+label::before {
  box-shadow: 0 0 0 0.2rem #ec6a8a;
}
.custom-checkbox:focus:not(:checked)+label::before {
  border-color: #ea748f;
}
.custom-checkbox:checked+label::before {
  border-color: #E31243;
  background-color: #E31243;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23fff' d='M6.564.75l-3.59 3.612-1.538-1.55L0 4.26 2.974 7.25 8 2.193z'/%3e%3c/svg%3e");
}
.custom-checkbox:disabled+label::before {
  background-color: #e9ecef;
}
</style>
