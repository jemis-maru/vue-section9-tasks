<template>
    <section>
        <div v-for="itemArr in listArr" :key="itemArr">
            <!-- <p>{{ item }}</p> -->
            <slot :item="itemArr" otherProp="-------------------------"></slot>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'TempList',
        data(){
            return{
                listArr: ['first item', 'second item', 'third item'],
            }
        }
    }
</script>

<style scoped>
section {
  margin: 2rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
}
</style>