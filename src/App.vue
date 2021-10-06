<template>
    <div>
        <div>
    <kinesis-container class="k-container">
    <kinesis-element :perspective="50" :strength="10" type="translate">
    <kinesis-element :perspective="30" :strength="20" type="depth">
    <h1 class="page-title" id = "h1-text">
        <kinesis-element :strength="-10" type="translate" transformOrigin="10% 100%" duration="100"><span>C</span></kinesis-element>
        <kinesis-element :strength="-20" type="rotate" transformOrigin="25% -20%" duration="100"><span>l</span></kinesis-element>
        <kinesis-element :strength="20" type="translate" transformOrigin="10% 100%" duration="200"><span>o</span></kinesis-element>
        <kinesis-element :strength="-10" type="translate" duration="200"><span>c</span></kinesis-element>
        <kinesis-element :strength="20" type="rotate" duration="20000"><span>k</span></kinesis-element>
        <kinesis-element :strength="-20" type="rotate" transformOrigin="10% 10%" duration="200"><span>s</span></kinesis-element>
    </h1>
<!--     <h1 class="page-title" id = "h1-shadow">Clocks</h1> -->
    </kinesis-element>
    </kinesis-element>
    </kinesis-container>
    </div>
    <div style="display:flex">
        <div><HexClock /></div>
        <div><DecClock /></div>
        <div><BinClock /></div>
    </div>
    </div>
    
</template>

<script>
import HexClock from "./components/HexClock.vue";
import BinClock from "./components/BinClock.vue";
import DecClock from "./components/DecClock.vue";
export default {
    components: {
        HexClock,
        BinClock,
        DecClock,
    }
}
</script>

<style lang="css">
    @import "assets/style.css";
</style>