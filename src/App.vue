<template>
  <div id="q-app">
    <div class="container">
     <q-toolbar>      
         <h3 class="text-centre"> The Super  Quiz </h3>        
      </q-toolbar>
      <div class="row">
        <component :is="mode" @answered="answered($event)" @confirmed="mode='app-question'"></component>
      </div>
      </div>
  </div>
</template>

<script>
import Question from './components/Question.vue';
import Answer from './components/Answer.vue';
export default {
  name: 'App',

  data() {
    return {
      mode :'app-question'
    }
  },
  methods :{

    answered(isCorrect){
      if(isCorrect){
        this.mode='appAnswer';
      }else{
        this.mode='appQuestion';
        alert('Wrong ! Try again');
      }
    }
  },
  components :{
    appQuestion : Question,
    appAnswer :Answer 
  }
}
</script>

<style>
.flip-enter {
        /*transform: rotateY(0deg);*/
    }

    .flip-enter-active {
        animation: flip-in  0.5s ease-out forwards;
    }

    .flip-leave {
        /*transform: rotateY(0deg);*/
    }

    .flip-leave-active {
        animation: flip-out 0.5s ease-out forwards;
    }

    @keyframes flip-out {
        from {
            transform: rotateY(0deg);
        }
        to {
            transform: rotateY(90deg);
        }
    }

    @keyframes flip-in {
        from {
            transform: rotateY(90deg);
        }
        to {
            transform: rotateY(0deg);
        }
    }
</style>
