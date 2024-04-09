<template>
    <view class="top-window-container">
        <view class="top-window-boarder">
            this is top window
            <p />
            and good day!
        </view>
        <custom-tab-bar class="tab-bar-flex" direction="horizontal" :show-icon="false" :selected="selected"
            @onTabItemTap="onTabItemTap" />
    </view>
</template>

<script setup>
    import {
        ref
    } from "vue";
    const selected = ref(0)
    const onTabItemTap = (e) => {
        console.log("tab!", e)
    }
</script>

<style>
    .top-window-container {
        display: flex;
        orientation: landscape;
    }

    .top-window-boarder {
        display: block;
        color: black;
        background: orange;
    }

    .tab-bar-flex {
        display: flex;
    }
</style>