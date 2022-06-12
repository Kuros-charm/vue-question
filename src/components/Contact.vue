<script setup lang="ts">



const props = defineProps({
        fieldLabel: String,
        fieldValue: {type: String, default: ''}

})
const emit =   defineEmits(['update:fieldValue'])



</script>

<template>
   <div class="input-group mb-1">
        <span class="input-group-text col-lg-3">{{fieldLabel}}</span>
        <input :value="fieldValue"
    @input="$emit('update:fieldValue', ($event.target as any).value)" type="text" class="form-control">
        </div>
</template>

