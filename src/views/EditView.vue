<template>
  <MemoForm v-if="memo" :memo="memo"/>
  <p v-else>Don't memo.</p>
</template>

<script>
import MemoForm from '@/components/MemoForm.vue' 
export default{
    name:'EditView',
    components:{
        MemoForm
    },
    computed :{
        memo(){
            const id = parseInt(this.$route.params.id)
            return this.$store.getters.getMemoById(id)
        }
    }
}
</script>