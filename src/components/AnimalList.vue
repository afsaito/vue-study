<template>
    <li>お名前：{{ name }} | 年齢：{{ age }}才 | すきな食べ物：{{eat}}</li>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class AnimalList extends Vue {
  @Prop() private name!: String;
  @Prop() private age!: Number;
  @Prop() private eat!: String;
}
</script>
