<template>
    <div>{{info}}</div>
</template>

<script lang="ts">
import {Component, Prop, Vue, Watch} from 'vue-property-decorator';
import {componentPrefix} from '@/config';

@Component
export default class CTest extends Vue {
    @Prop({default: 'default string', type: String}) private prop1!: string;
    @Prop({required: true, type: Number}) private prop2!: number;

    static get componentName() {
        return `${componentPrefix}-test`;
    }

    get info() {
        return `${this.prop1}: ${this.prop2}`;
    }

    @Watch('prop1')
    public onProp1Changed() {
        this.$emit('propsUpdated', this.prop1, this.prop2);
    }
}

Vue.component(CTest.componentName, CTest);
</script>
