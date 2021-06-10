<template>
    <transition name="custom" enter-active-class="animate__animated animate__fadeInDown" leave-active-class="animate__animated animate__slideOutRight">
        <div v-if="sliderStatus">
            <div class="align-items-center" :class="sliderState">
                <label for="" class="font-weight-bold me-2">Max</label>
                <input type="number" class="form-control mx-2" style="width: 60px; text-align: center;" v-model="maxAmount" @change="$emit('update:maximum', maximum)">
                <input type="range" class="ml-1 custom-range" min="0" max="200" v-model="maxAmount" @input="$emit('update:maximum', maximum)">
            </div>
        </div>
    </transition>
</template>

<script>
export default {
    name: "price-slider",
    data: function () {
        return {
            maxAmount: 50
            }
    },
    props: ["sliderStatus", "maximum"],
    computed: {
        sliderState: function () {
            return this.sliderStatus ? 'd-flex' : 'd-none'
        }
    }
}
</script>

<style>
.fade-enter, .fade-leave-to {
    opacity: 0;
}
.fade-enter-active, .fade-leave-active {
    transition: all .5s ease-in-out;
}
</style>