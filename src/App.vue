<template>
  <div>
    <h1>Zhopa</h1>
    <div style="display: flex; gap: 10px; margin-bottom: 40px;">
      <Button :label="'Сохранить изменения'" :type="1"/>
      <Button :label="'Отмена'" :type="2"/>
      <Button :label="'Выйти'" :type="3"/>
    </div>

    <div style="display: flex; flex-direction: column; gap: 0px; margin-bottom: 40px;">
      <CheckBox :label="'Сохранить изменения'" :checked="true"/>
      <CheckBox :label="'Отмена'" :checked="false"/>
      <CheckBox :label="'Выйти'" :checked="false"/>
    </div>

    <div style="display: flex; flex-direction: column; gap: 0px; margin-bottom: 40px;">
      <RadioButton :label="'Сохранить изменения'" :checked="false"/>
    </div>

    <div style="display: flex; flex-direction: column; gap: 0px; margin-bottom: 40px;">
      <Input :label="'Название отчета'" :counter="false" :type="text" :placeholder="'Отчет'"/>
      <Input :label="'Название отчета'" :counter="false" :type="text" :value="'Изначальное'"/>
      <Input :label="'Название отчета'" :counter="false" :type="text" :maxLength="5"/>
      <Input :label="'Название отчета'" :counter="false" :type="text"/>
    </div>
    
  </div>
</template>

<script>
import Button from "../src/components/ButtonComponent.vue"; 
import CheckBox from "../src/components/CheckBoxComponent.vue"; 
import RadioButton from "../src/components/RadioButton.vue"; 
import Input from "../src/components/Inputcomponent.vue"; 

export default{
  components: { Button, CheckBox, RadioButton, Input },
}
</script>

<style scoped>

</style>
