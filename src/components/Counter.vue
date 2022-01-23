<template>
  <h2>{{ customTitle }}</h2>
  <p> {{ counter }} <sup>2</sup> = {{ getSquereCounter }} </p>
  <div>
      <button @click="decrease">-1</button>
      <button @click="increase" >+1</button>
  </div>  
</template>
<script>
    export default {
        // name : 'Patito'
        // props: ['start'],
        props: {
            titulo: {
                type: String,
                required: false
            },
            start: {
                type: Number,
                default: 10,
                validator: ( value ) => value > 10
                // required: true,
            }
        },

        data() {
            return {
                counter : this.start
            }
        },

        methods: {

            getSquareValue(){
                console.log('SquerValue');
                return this.counter * this.counter;
            },

            increase(){
                this.counter++;
            },

            decrease(){
                this.counter--;
            }
        },
        computed : {
            getSquereCounter(){
                console.log('SquerCounter');
                return this.counter * this.counter;
            },

            customTitle(){
                return ( this.titulo ) ? this.titulo : 'Counter';
            }
        }

    };
</script>

<style>
    button{
        background-color: #64BB87;
        border-radius: 5px;
        border: 1px solid white;
        color: white;
        margin: 0 10px;
        padding: 5px 15px;
    }
</style>