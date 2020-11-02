<template>
    <div>
        <slot></slot>
        <button class="carousel__nav carousel__next" @click.prevent="next"></button>
        <button class="carousel__nav carousel__prev" @click.prevent="prev"></button>
    </div>
</template>

<script>
export default {
    data () {
        return {
            index: 0,
            slides: [],
            direction: null
        }
    },
    mounted () {
        this.slides = this.$children
        this.slides.forEach((slide, i) => {
            slide.index = i
        })
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
    }
}
</script>