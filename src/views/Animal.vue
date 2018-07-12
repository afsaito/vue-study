<template>
  <div class="animal">
    <input type="button" value="Click" @click="whoAnimal()" />
    <p>{{ animalName }}</p>

    <ul>
      <AnimalList v-for="animal in animals" :key="animal.id"
        :name="animal.name"
        :age="animal.age"
        :eat="animal.eat"></AnimalList>      
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import AnimalList from '@/components/AnimalList.vue';

@Component({
  components: {
    AnimalList,
  },
})

export default class Animal extends Vue {
  private animalName = '私は誰でしょう！？';
  private animals = [
    { id: 1, name: 'ねこ', age: 2, eat: 'さかな' },
    { id: 2, name: 'いぬ', age: 3, eat: 'おにく' },
    { id: 3, name: 'さる', age: 5, eat: 'ばなな' },
    { id: 4, name: 'きじ', age: 7, eat: 'めめず' },
    { id: 5, name: 'ごり', age: 1, eat: 'りんご' },
  ];

  private whoAnimal() {
    this.animalName = 'レッサーパンダだよ！！';
  }
}
</script>

