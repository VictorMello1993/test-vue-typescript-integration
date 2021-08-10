<template>
  <div>
    <h1>Contador (Classe)</h1>
    <h2>{{value}}</h2>
    <h3>{{getEvenOrOdd()}}</h3>
    <h3>{{EvenOrOdd}}</h3>
    <button @click="setValue(-1)">Dec</button>
    <button @click="setValue(1)">Inc</button>
    </div>  
</template>
<script lang="ts">
import {Vue, Component, Prop} from 'vue-property-decorator'

@Component({})
export default class CounterClass extends Vue {
  @Prop(Number) private readonly startValue?: number
  private value: number = this.startValue || 0

  public setValue(delta: number) {
    this.value += delta
  }

  public getEvenOrOdd(): string {
    return this.value % 2 === 0 ? 'Par' : 'ímpar'
  }

  //Inserindo propriedade computada (método com a palavra 'get' na frente, para definir um método que se comporta como se fosse um atributo)
  public get EvenOrOdd(): string {
    return this.value % 2 === 0 ? 'Par' : 'ímpar'
  }
}
</script>

<style>

</style>
