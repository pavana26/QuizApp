<template>
     <div >
          <div class="layout-padding">
         <span class="label bg-secondary text-white  test">That's Correct!</span>
        
        <hr>
        <button class="btn btn-primary full-width" @click="onNextQuestion">Next Question</button>
          </div>
    </div>
</template>

<script>
export default {

 methods: {
            onNextQuestion() {
                this.$emit('confirmed');
            }
        }
}
</script>

<style>
.btn-primary {
  color: purple (73, 204, 249, 1.0);
  border-color: goldenrod;
  background-color: blue;
}

.btn {
  outline: none;
  box-shadow: none;
  border-width: 2px;
  border-radius: 3px;
  border-style: solid;
  padding: 8px;
}

.test {
  width:100%;
  border: none;
  border-top: 2px solid rgba(73, 204, 249, 1.0);
  border-bottom: 2px solid rgba(73, 204, 249, 1.0);
  margin-right: 10px;
  padding: 5px;
  line-height: 17px;
}
</style>
