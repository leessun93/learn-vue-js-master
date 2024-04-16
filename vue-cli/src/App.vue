<template lang=""> 
    <div>
        <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트 데이터 이름"></app-header> -->
        <app-header 
        v-bind:propsdata="str"
        v-on:renew="renewStr"></app-header>
    </div>
</template>
<script>
import AppHeader from './components/AppHeader.vue'; //가급적 .vue까지 기입해줘야한다
export default {
    data: function() {
        return {
            str : 'hi'
        }
    },
    components: {
        'app-header' : AppHeader
    },
    methods: {
        renewStr: function(){
            this.str = 'getAmped';
        }
    }
}
</script>
<style lang="">
    
</style>