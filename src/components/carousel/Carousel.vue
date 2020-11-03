<template>
    <div>
        <slot></slot>
        <button class="carousel__nav carousel__next" @click.prevent="next"></button>
        <button class="carousel__nav carousel__prev" @click.prevent="prev"></button>
        <div class="carousel__pagination">
            <button v-for="n in slideCount" @click="goto(n-1)" :class="{active: n - 1 == index}"></button>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            index: 0,
            slides: [],
            direction: 'right'
        }
    },
    watch: {
        slides (slides) {
            if (this.index >= this.slideCount) {
                this.index = this.slideCount - 1
            }
        }
    },
    computed: {
        slideCount () { return this.slides.length }
    },
    methods: {
        next () {
            this.index++
            this.direction = 'right'
            if (this.index >= this.slideCount) {
                this.index = 0
            }
        },        
        prev () {
            this.index--
            this.direction = 'left'
            if (this.index < 0 ) {
                this.index = this.slideCount - 1
            }
        },
        goto (index) {
            this.direction = index > this.index ? 'right' : 'left'
            this.index = index
        }
    },
    mounted () {
        this.slides = this.$children
    }
}
</script>