<template>
    <section>
        <div>
            This is list data
        </div>
        <div>
            <input type="text" v-model="inputData">
            <button @click="submitFun">Add</button>
        </div>
        <teleport to="body">
            <error-msg v-if="isInputEmpty">
                <h3>Error</h3>
                <p>Please enter something!</p>
                <button @click="closeError">close</button>
            </error-msg>
        </teleport>
    </section>
</template>

<script>
import ErrorMsg from './ErrorMsg.vue'

    export default {
        name: 'ListData',
        components: {
            'error-msg': ErrorMsg,
        },
        data(){
            return{
                inputData: '',
                isInputEmpty: false,
            };
        },
        methods: {
            submitFun(){
                if(this.inputData === ''){
                    this.isInputEmpty = true;
                }
            },
            closeError(){
                this.isInputEmpty = false;
            },
        },
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