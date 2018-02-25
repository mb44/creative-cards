<template>
    <div>
        <h1 class="text-center">Creative Cards</h1>
        <ul class="nav justify-content-center">
            <li class="nav-item"><a @click="pageSelected='cardFront'" class="nav-link">Front</a></li>
            <li class="nav-item"><a @click="pageSelected='cardInsideLeft'" class="nav-link">Inside Left</a></li>
            <li class="nav-item"><a @click="pageSelected='cardInsideRight'" class="nav-link">Inside Right</a></li>
            <li class="nav-item"><a @click="pageSelected='cardBack'" class="nav-link">Back</a></li>
        </ul>
        <hr>
        <cc-card-progress></cc-card-progress>
    </div>
</template>

<script>
import CardProgress from './card/CardProgress.vue'

    export default {
        data: function() {
            return {
                pageSelected: ''
            }
        },
        watch: {
            pageSelected: function() {
                this.$emit('pageWasChanged', this.pageSelected)
            }
        },
        components: {
            ccCardProgress: CardProgress
        }
    }

</script>

<style>

</style>