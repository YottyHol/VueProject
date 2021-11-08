<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
   <div>
        <Chart type="doughnut" :data="chartData" :options="lightOptions" />
   </div>
  </div>
  
</template>

<script>
export default {
    
  name: 'HelloWorld',
  
  props: {
    msg: String
  },
      data() {
        return {
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
    }
}
</script>