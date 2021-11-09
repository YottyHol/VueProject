<template>
  <div id="app">
    <div class="app-container">

      <HelloWorld msg="Welcome to Your PrimeVue App"/>
      <form @submit.prevent="greet">
        <InputText type="text" v-model="text"/>
        <Button type="submit" label="Submit"/>
        <h3>{{message}}</h3>
           <Chart class ="p-20"
        type="doughnut" :data="chartData" :options="lightOptions" />
      </form>
    </div>

    <Toast/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
    data() {
        return {
            message: null,
            text: null,

                        chartData: {
                labels: ['A','B','C'],
                datasets: [
                    {
                        data: [300, 50, 100],
                        backgroundColor: ["#FF6384","#36A2EB","#FFCE56"],
                        hoverBackgroundColor: ["#FF6384","#36A2EB","#FFCE56"]
                    }
                ]
            },
			lightOptions: {
				plugins: {
                    legend: {
                        labels: {
                            color: '#495057'
                        }
                    }
                }
			}
        }
        
    },
    methods: {
        greet() {
            this.$toast.add({severity: 'info', summary: 'Hello '  + this.text});
            this.message = 'Hello ' + this.text;
        }
    },
    components: {
      HelloWorld
    }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.app-container {
  text-align: center;
}

body #app .p-button {
  margin-left: .2em;
}

form {
  margin-top: 2em;
}
</style>