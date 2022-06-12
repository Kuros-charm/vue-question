<script setup lang="ts">
import { ref, computed } from 'vue';
import { v4 } from 'uuid'


const props = defineProps({
    commonName: String,
    category: String,
    options: Array,
    selectedValue: String,

})
const emit = defineEmits(['update:selectedValue'])

const ids = computed(() => {
    return (props.options as string[])?.map(x => x.replace(/[^a-zA-Z0-9]/g, ''))
})

//const uuid = v4();

</script>

<template>
    <div class="col-lg-6 mt-2 mb-2">
        <h6>{{category}}</h6>
        <div class="row">

            <template v-for="(item, i) in options">
                <div class="col-12">
                    <div class="form-check">
                        <input class="form-check-input" type="radio" :name="commonName" :value="item" :id="ids[i]"
                            :checked="selectedValue === item"
                            @change="$emit('update:selectedValue', ($event.target as any).value)">
                        <label class="form-check-label" :for="ids[i]">
                            {{ item }}
                        </label>

                    </div>


                </div>



            </template>
        </div>
    </div>


</template>

