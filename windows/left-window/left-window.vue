<template>
    <view class="left-window-border">
        left window shows here
    </view>
</template>

<script setup>
    import {
        onMounted,
        ref,
        getCurrentInstance
    } from 'vue';
    let isPcObserver, isPhoneObserver
    const isPC = ref(false)
    onMounted(() => {
        const instance = getCurrentInstance()
        isPcObserver = uni.createMediaQueryObserver(instance)
        isPhoneObserver = uni.createMediaQueryObserver(instance)
        isPcObserver.observe({
            minWidth: 768
        }, matched => {
            isPC.value = matched
            console.log("isPC:", isPC)
            uni.reLaunch({
                url: "/pages/nontabpage/nontabpage"
            })
        })

        isPhoneObserver.observe({
            maxWidth: 767
        }, matched => {
            isPC.value = !matched
            console.log("isPC:", isPC)
            if (matched) {
                uni.reLaunch({
                    url: "/pages/page3/page3"
                })
            }
        })
    })
</script>

<style>
    .left-window-border {
        background: green;
    }
</style>