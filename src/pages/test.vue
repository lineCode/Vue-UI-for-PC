<template>
    <div class="demo">
        <comHeader/>
        <p @click="show=true">click</p>
        <p>&nbsp;</p>
        <p @click="show=false">close</p>
        <transition>
            <div v-if="show" v-show="show">
                <p>12131312</p>
                <transition name="fade">
                    <div class="" v-show="show">00</div>
                </transition>
            </div>
        </transition>

        <formItem>
            <vInput></vInput>
        </formItem>
    </div>

</template>
<script>
    import vInput from '../components/input/index'
    import formItem from '../components/form/formItem'
    import Test from '../components/test.vue'
    export default {
        name: 'test',
        path: '/test',
        data(){
            return {
                show: false
            }
        },
        props: {},
        mounted(){
        },
        components: {Test,vInput, formItem},
        methods: {},
        computed: {}
    }
</script>
<style>

    .fade-enter{ opacity: 0 }
    .fade-enter-active{
        animation-name: fold-in;
        animation-duration: .5s;
    }
    .fade-leave-active{ animation: leave 3s }
    @keyframes leave{
        0%{ opacity: 1 }
        100%{ opacity: 0 }
    }
    @keyframes fold-in{
        0%{
            transform: translate3d(0, 100%, 0);
        }
        100%{
            transform: translate3d(0, 0, 0);
        }
    }
</style>