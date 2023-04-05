<!-- a big image, but not too big... -->
<script setup lang="ts">
import { ref, computed } from 'vue'

const props = defineProps({
    imgsrc: {
        type: String,
    },
    classes: {
        type: String,
        default: 'px-36 py-16',
    }
})

const imgsrc = ref(props.imgsrc)
const classes = ref(props.classes)

const containerClasses = computed(() => {
    return `container content-center flex-col items-center ${classes.value}`
})
</script>

<template>
    <div :class="containerClasses">
        <img :src="imgsrc" alt="Big Image" />
    </div>
</template>