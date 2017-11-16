<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <br>
                <button class="btn btn-primary"
                        @click="selectedComponent = 'appBlue'"
                >Load Blue Template</button>
                <button class="btn btn-success"
                        @click="selectedComponent = 'appGreen'"
                >Load Green Template</button>
                <button class="btn btn-danger"
                        @click="selectedComponent = 'appRed'"
                >Load Red Template</button>
                <hr>
                <component v-if="selectedComponent" :is="selectedComponent">
                  <p>Hello there !!! </p>
                </component>
                <div v-else>
                  <h2 class="info">Press any button above to continue...</h2>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Blue from './components/Blue.vue';
    import Green from './components/Green.vue';
    import Red from './components/Red.vue';

    export default {
        data: function() {
          return {
            selectedComponent: null
          }
        },
        components: {
            appBlue: Blue,
            appGreen: Green,
            appRed: Red
        }
    }
</script>

<style scoped>
  .info {
    border: 1px solid yellow;
    background-color: lightgoldenrodyellow;
    padding: 30px;
    margin: 20px auto;
    text-align: center
  }
</style>
