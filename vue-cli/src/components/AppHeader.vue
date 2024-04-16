<template lang="ko">
    <header>
        <h1>{{propsdata}}</h1>
        <button v-on:click="sendEvent">Send</button>
    </header>
</template>
<script>
export default {
    props: ['propsdata'],
    methods: {
        sendEvent : function(){
            this.$emit('renew'); // $emit() 을 하면 상위컴포넌트로 날릴 이벤트 이름? 상위 테그에서 v-on:올린이름="상위컴포넌트에서실행하메서드이름" 으로 받음
        }
    }
}
</script>
<style lang="">
    
</style>