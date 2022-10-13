<template>
    <MemoFrom v-if="memo" :memo="memo" />
    <p v-else>指定されたメモはありません</p>
</template>

<script>
import MemoFrom from '@/components/MemoForm.vue'
export default {
    name: 'EditView',
    components: {
        MemoFrom,
    },
    computed: {
        memo () {
            const id = parseInt(this.$route.params.id)
            return this.$store.getters.getMemoById(id)
        }
    }
}
</script>