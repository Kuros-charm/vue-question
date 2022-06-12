<script setup lang="ts">



const props = defineProps({
        description: String,
        modelValue: String,

})
const emit =   defineEmits(['update:modelValue'])



</script>

<template>
    <h6>{{description}}</h6>
    <textarea  class="form-control" v-model="modelValue" ></textarea>
        {{ modelValue }}
</template>