<script setup lang="ts">



const props = defineProps({
        checked: {type: Boolean, default: false},
        checkboxLabel: String,
        fieldLabel: String,
        fieldValue: {type: String, default: ''}

})
const emit =   defineEmits(['update:fieldValue', 'update:checked'])



</script>

<template>
   <div class="input-group mb-1">
        <div class="input-group-text">
                <input class="form-check-input mt-0" type="checkbox" :checked="checked"
    @change="$emit('update:checked', ($event.target as any).checked)">
        </div>
        <span class="input-group-text col-lg-2" >{{checkboxLabel}}</span>
        <span class="input-group-text col-lg-3">{{fieldLabel}}</span>

        <input :value="fieldValue"
    @input="$emit('update:fieldValue', ($event.target as any).value)" type="text" class="form-control">
        </div>
</template>