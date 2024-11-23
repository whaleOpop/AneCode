<template>
  <div class="wrapper">
    <p class="label">{{ label }}</p>
    <input :type="type" :maxlength="maxLength" v-model="valueInput" :placeholder="placeholder">
    <img v-if="valueInput.length>0" src="../assets/icons/close.svg" alt="" @click="valueInput = ''">
    <p v-if="maxLength>0" class="counter">{{ valueInput.length }}/{{ maxLength }}</p>
  </div>
</template>

<script>
export default {
    props: ['label', 'type', 'maxLength', 'value', 'placeholder'],
    data() {
        return {
            valueInput: '',
        }
    },
    mounted(){
        this.valueInput = this.value;
    },
    methods: {
        changeStatement() {
            this.$parent.$emit('changed', this.valueInput)
        },
    },
}
</script>

<style scoped>
img{
    cursor: pointer;
    position: absolute;
    width: 10px;
    aspect-ratio: 1;
    top: 34px;
    right: 15px;
}
img:hover{
    filter: brightness(50%);
}
.wrapper{
    display: flex;
    flex-direction: column;
    gap: 3px;
    width: 250px;
    position: relative;
}
input{
    font-size: 12px;
    border-radius: 7px;
    padding: 10px 15px;
    border: 1px solid var(--secondary-accent);
    color: var(--colors-black);
    padding-right: 35px;
}
input:focus{
    outline: none;
    border: 1px solid var(--main-accent);
}
input::placeholder{
    color: var(--secondary-accent);
}


.label{
    font-size: 12px;
    color: var(--colors-black);
    margin: 0;
}
.counter{
    font-size: 12px;
    color: var(--secondary-accent);
    display: flex;
    justify-content: end;
    text-align: end;
    margin: 0;
}
</style>