<template>
    <DocSectionText v-bind="$attrs">
        <p>Label of an option is used as the display text of an item by default, for custom content support define an <i>option</i> template that gets the option instance as a parameter.</p>
    </DocSectionText>
    <div class="card flex justify-center">
        <SelectButton v-model="value" :options="options" optionLabel="value" dataKey="value" aria-labelledby="custom">
            <template #option="slotProps">
                <i :class="slotProps.option.icon"></i>
            </template>
        </SelectButton>
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import SelectButton from '@/volt/SelectButton.vue';
import { ref } from 'vue';

const value = ref(null);
const options = ref([
    { icon: 'pi pi-align-left', value: 'Left' },
    { icon: 'pi pi-align-right', value: 'Right' },
    { icon: 'pi pi-align-center', value: 'Center' },
    { icon: 'pi pi-align-justify', value: 'Justify' }
]);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <SelectButton v-model="value" :options="options" optionLabel="value" dataKey="value" aria-labelledby="custom">
            <template #option="slotProps">
                <i :class="slotProps.option.icon"></i>
            </template>
        </SelectButton>
    </div>
</template>

<script setup lang="ts">
import SelectButton from '@/volt/SelectButton.vue';
import { ref } from 'vue';

const value = ref(null);
const options = ref([
    { icon: 'pi pi-align-left', value: 'Left' },
    { icon: 'pi pi-align-right', value: 'Right' },
    { icon: 'pi pi-align-center', value: 'Center' },
    { icon: 'pi pi-align-justify', value: 'Justify' }
]);
<\/script>
`);
</script>
