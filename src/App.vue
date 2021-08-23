<template>
  <div>
    <h1>使用Typescript的裝飾器前後差異</h1>

    <div>
      裝飾器：<a href="https://www.typescriptlang.org/docs/handbook/decorators.html">https://www.typescriptlang.org/docs/handbook/decorators.html</a> <br>
      使用套件：<a href="https://github.com/kaorun343/vue-property-decorator">https://github.com/kaorun343/vue-property-decorator</a> <br>
       - 前置套件：<a href="https://github.com/vuejs/vue-class-component">https://github.com/vuejs/vue-class-component</a>
    </div>

    <div>
      可以搭配 Vue.js devtools 使用 <br>
      <a href="https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd">https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd</a>
    </div>

    <h3>基本Component</h3>
    <DefaultVueComponent />
    <ClassVueComponent />

    <hr>
    
    <h3>自訂組件Prop傳值</h3>
    <DefaultProp property1="1" property2="1" property3="1" propsync1="sync1" />
    <ClassProp property1="2" property2="2" property3="2" propsync1="sync1" />
    
    <hr>
    
    <h3>自訂組件Emit事件輸出</h3>
    <DefaultEmit @click="emitShowContent" @click2="emitShowContent" />
    <ClassEmit @click="emitShowContent" @click2="emitShowContent" />

    <hr>
    
    <h3>自訂組件Model修改預設值prop與emit類型 (不影響外部v-model使用)</h3>
    <DefaultModel v-model="test1" />
    <ClassModel v-model="test1" />

    <hr>
    
    <h3>自訂組件Provide父子組件使用 提供(Provide)/注入(Inject) 傳值(不常用)</h3>
    <DefaultProvide />
    <ClassProvide />

    <hr>
    
    <h3>自訂組件VModel建立的簡易方法，使用預設參數 (value屬性與input事件)</h3>
    <DefaultVModel v-model="test1" />
    <ClassVModel v-model="test1" />

    <hr>
    
    <h3>自訂組件Ref取得子組件內容(VNode)</h3>
    <DefaultRef />
    <DefaultRef />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import DefaultVueComponent from './components/DefaultVueComponent.vue';
import ClassVueComponent from './components/ClassVueComponent.vue';

import DefaultProp from './components/Prop/Default_Prop.vue';
import ClassProp from './components/Prop/Class_Prop.vue';

import DefaultEmit from './components/Emit/Default_Emit.vue';
import ClassEmit from './components/Emit/Class_Emit.vue';

import DefaultModel from './components/Model/Default_Model.vue';
import ClassModel from './components/Model/Class_Model.vue';

import DefaultProvide from './components/Provide/Default_Provide.vue';
import ClassProvide from './components/Provide/Class_Provide.vue';

import DefaultVModel from './components/VModel/Default_VModel.vue';
import ClassVModel from './components/VModel/Class_VModel.vue';

import DefaultRef from './components/Ref/Default_Ref.vue';
import ClassRef from './components/Ref/Class_Ref.vue';

@Component({
  components: {
    DefaultVueComponent,
    ClassVueComponent,

    DefaultProp,
    ClassProp,

    DefaultEmit,
    ClassEmit,

    DefaultModel,
    ClassModel,

    DefaultProvide,
    ClassProvide,

    DefaultVModel,
    ClassVModel,

    DefaultRef,
    ClassRef,
  },
})
export default class App extends Vue {
  test1: string = '12315fds';

  emitShowContent(...content: any[]) {
    console.log('emitShowContent', content);
  }
}
</script>