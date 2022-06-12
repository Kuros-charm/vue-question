<script setup lang="ts">
import { computed, ref } from 'vue';
import SubmissionBy from './SubmissionBy.vue';
import Contact from './Contact.vue';
import Category from './Category.vue';

const q1 = ref({
    bu: {
        checked: false,
        fieldValue: ''
    },
    function: {
        checked: false,
        fieldValue: '',
    }
});
const q2 = ref({
    name: '',
    pos: '',
    dept: '',
    email: '',
    phone: ''
})

const q3 = ref({
    obessed: '',
    sustainability: '',
    culture: ''
})

const q4 = ref({
    name: '',
    periodFrom: '',
    periodTo: '',
    description: '',
    preiodYear: 2021
})

const q5 = ref({
    genSales: {
        checked: false,
        value: '',
        percent: ''
    },
    gobeSales: {
        checked: false,

        percentFrom: '',
        percentTo: ''
    },
    newMember: {
        checked: false,

        value: '',
        percent: ''
    },
    memberActive: {
        checked: false,

        percentFrom: '',
        percentTo: '',
        percentConversion: ''
    },
    marketShare: {
        checked: false,

        percentFrom: '',
        percentTo: '',
        category: ''
    },
    socialMediaFans: {
        checked: false,

        value: '',
        percent: '',
        percentPenetration: '',
        percentEnagement: '',
        reach: ''
    },
    cost: {
        checked: false,

        value: ''
    },
    costSaving: {
        checked: false,

        value: ''
    },
    award: {
        checked: false,

        name: ''
    },
    other: {
        checked: false,

        value: ''
    }
});

const q6 = ref({
    engagement: '',
    differentiation: '',
    anywhere: '',
    relationship: '',
    experience: ''
});
const q7 = ref({
    engaement: ''
});

const q8 = ref({
    sustainability: '',
    description: ''
});

const q9 = ref({
    technology: ''
});

const q10 = ref({
    collaboration: ''
});

const q11 = ref({
    visualsChecked: false,
    videoChecked: false,
    file: null
})

</script>

<template>
    <div class="container">
        <h5>For the period</h5>
        <div class="question-wrapper">
            <h3>1. Submission by</h3>
            <div class="row">
                <SubmissionBy checkboxLabel="BU" fieldLabel="state the bu and market:" v-model:checked="q1.bu.checked"
                    v-model:field-value="q1.bu.fieldValue"> </SubmissionBy>
                <SubmissionBy checkboxLabel="Group Function" fieldLabel="state the function:"
                    v-model:checked="q1.function.checked" v-model:field-value="q1.function.fieldValue"> </SubmissionBy>
            </div>

        </div>
        <div class="question-wrapper">

            <h3>2. Contact</h3>
            <div class="row">
                <Contact fieldLabel="Name" v-model:field-value="q2.name"></Contact>
                <Contact fieldLabel="Position" v-model:field-value="q2.pos"></Contact>
                <Contact fieldLabel="Department" v-model:field-value="q2.dept"></Contact>
                <Contact fieldLabel="Email" v-model:field-value="q2.email"></Contact>
                <Contact fieldLabel="Phone" v-model:field-value="q2.phone"></Contact>

            </div>
        </div>
        <div class="question-wrapper">

            <h3>3. Category</h3>
            <div class="row">
                <Category common-name="Category" category="Obessed" :options="['a', 'b', 'c']"
                    v-model:selected-value="q3.obessed"></Category>
                <Category common-name="Category" category="Sustainability" :options="['a', 'b', 'c']"
                    v-model:selected-value="q3.sustainability">
                </Category>
                <Category common-name="Category" category="Culture" :options="['a', 'b', 'c']"
                    v-model:selected-value="q3.culture"></Category>

            </div>
        </div>
        <div class="question-wrapper">
            <h3>4. Detiails of the Submission</h3>
            <div class="row">
                <div class="input-group mb-1">
                    <span class="input-group-text col-md-3">Name of </span>
                    <input v-model="q4.name" type="text" class="form-control">
                </div>
                <div class="input-group mb-1">
                    <span class="input-group-text col-md-3">Period</span>
                    <select class="form-select form-select-sm" v-model="q4.periodFrom">
                        <option v-for="i in 12" :value="i">{{ i }}</option>

                    </select>
                    <span class="input-group-text">{{ q4.preiodYear }}</span>
                    <select class="form-select form-select-sm" v-model="q4.periodTo">
                        <option v-for="i in 12" :value="i">{{ i }}</option>
                    </select>
                    <span class="input-group-text">{{ q4.preiodYear }}</span>
                </div>
                <div class="input-group mb-1">
                    <span class="input-group-text col-md-3">Description</span>
                    <textarea v-model="q4.description" class="form-control"></textarea>
                </div>

            </div>
        </div>
        <div class="question-wrapper">
            <h3>5. Business Results</h3>
            <div class="input-group mb-1">
                <div class="input-group-text col-1">
                    <input class="form-check-input mt-0" type="checkbox" v-model="q5.genSales.checked">
                </div>
                <span class="input-group-text">General Incremental salesL (In HKD)$</span>
                <input v-model="q5.genSales.value" type="text" class="form-control">
            </div>
            <div class="input-group mb-3">
                <div class="col-1">
                </div>
                <span class="input-group-text">Percentage increase vs total company (or total category):</span>
                <input v-model="q5.genSales.value" type="text" class="form-control">
                <span class="input-group-text col-md-2">% during that period</span>

            </div>

        </div>

        <h5>Fill the sections</h5>
        <div class="question-wrapper">
            <h3>6. Customer Engagement</h3>
            <div class="subquestion-wrapper">
                <h6>Describe</h6>
                <textarea v-model="q6.engagement"></textarea>

            </div>
            <div class="container row">
                <h4>6a. Differentiation</h4>
                <h6>Describe</h6>
                <textarea v-model="q6.differentiation"></textarea>

            </div>

        </div>
        <div class="question-wrapper">
            <h3>11. Customer Engagement</h3>
            <div class="form-check">
                <input class="form-check-input" type="checkbox" id="visualsChecked" v-model="q11.visualsChecked">
                <label class="form-check-label" for="visualsChecked">
                    Up to 6 Visuals
                </label>

            </div>
            <div class="form-check">
                <input class="form-check-input" type="checkbox" id="videoChecked" v-model="q11.videoChecked">
                <label class="form-check-label" for="videoChecked">
                    Up to 3 Videos
                </label>
            </div>

            <div class="row">
                <div class="col-4 text-end">Attachments <span class=" text-danger">*</span></div>
                <div class="col">Select a file</div>


            </div>
            <div class="row mt-1">
                <div class="col-sm-4"></div>
                <div class="col-sm-1">Name</div>
                <div class="col">
                    <input class="form-control form-control-sm" id="formFileSm" type="file" @change="(value) =>  q11.file = value">
                </div>


            </div>

        </div>



    </div>



</template>

<style lang="scss">
@use '../assets/main.scss';

.input-group-text {
    background: none;
    border: none;
}

 .question-wrapper {
    @extend .mb-5;   
    @extend .mt-2;
}

.subquestion-wrapper{
    @extend .container;
    @extend .row;
    @extend .mb-4;


}


h3,
h4 {
    color: rgb(13, 102, 143);
}
</style>