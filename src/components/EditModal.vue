<template>
    <el-dialog v-model="props.show" title="Edit" width="30%" center>
        <FormVue v-if="props.show" editMode="edit" :item="props.item" @change1="emit('change', false)" />
    </el-dialog>
</template>
<script lang="ts" setup>
import FormVue from './Form.vue';
const props = defineProps({
    show: Boolean,
    item: Object,
})
const emit = defineEmits<{
    (e: 'change', action: boolean): void
}>()
</script>
<style >
.dialog-footer button:first-child {
    margin-right: 10px;
}

@media screen and (max-width: 400px) {
    .el-dialog--center {
        width: 100% !important;
    }
}
</style>
