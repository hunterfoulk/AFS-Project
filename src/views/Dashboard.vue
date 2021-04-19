<template>
  <v-container id="dashboard-view" fluid tag="section">
    <v-col>
      <v-row cols="12">
        <v-col>
          <v-row
         v-bind:style='{justifyContent:"space-around",padding:"10px"}'
            v-for="(chart, i) in charts"
            :key="`chart-${i}`"
           :align="align"
           no-gutters
          >
            <material-chart-card
              :color="chart.color"
              :data="chart.data"
              :options="chart.options"
              :responsive-options="chart.responsiveOptions"
              :title="chart.title"
              :type="chart.type"
               v-bind:style='{width : "800px",maxWidth:"100%",marginBottom:"15px",}'
            >
              <template #subtitle>
                <div class="font-weight-light text--secondary">
                  <div v-html="chart.subtitle" />
                </div>
              </template>

              <template #actions>
                <v-icon class="mr-1" small>
                  mdi-clock-outline
                </v-icon>

                <span
                  class="text-caption grey--text font-weight-light"
                  v-text="chart.time"
                />
              </template>
            </material-chart-card>
               <material-card color="primary" v-bind:style='{width:"400px"}'>
                 <v-col>
               <h1>Extremely important graph!</h1>
               <p>Look at how important this graph!</p>
                </v-col>
            </material-card>
          </v-row>
        
        </v-col>
      </v-row>
 
          
    </v-col>
  </v-container>
</template>

<script>
// Utilities
import { get } from "vuex-pathify";
import Vue from "vue";

const lineSmooth = Vue.chartist.Interpolation.cardinal({
  tension: 0,
});

export default {
  name: "DashboardView",

  data: () => ({
    charts: [
      {
        type: "Bar",
        color: "primary",
        title: "Website Views",
        subtitle: "Last Campaign Performance",
        time: "updated 10 minutes ago",
        data: {
          labels: [
            "Ja",
            "Fe",
            "Ma",
            "Ap",
            "Mai",
            "Ju",
            "Jul",
            "Au",
            "Se",
            "Oc",
            "No",
            "De",
          ],
          series: [
            [542, 443, 320, 780, 553, 453, 326, 434, 568, 610, 756, 895],
          ],
        },
        options: {
          axisX: {
            showGrid: false,
          },
          low: 0,
          high: 1000,
          chartPadding: {
            top: 0,
            right: 5,
            bottom: 0,
            left: 0,
          },
        },
        responsiveOptions: [
          [
            "screen and (max-width: 640px)",
            {
              seriesBarDistance: 5,
              axisX: {
                labelInterpolationFnc: function(value) {
                  return value[0];
                },
              },
            },
          ],
        ],
      },
      {
        type: "Line",
        color: "success",
        title: "Daily Sales",
        subtitle:
          '<i class="mdi mdi-arrow-up green--text"></i><span class="green--text">55%</span>&nbsp;increase in today\'s sales',
        time: "updated 4 minutes ago",
        data: {
          labels: ["12am", "3pm", "6pm", "9pm", "12pm", "3am", "6am", "9am"],
          series: [[230, 750, 450, 300, 280, 240, 200, 190]],
        },
        options: {
          lineSmooth,
          low: 0,
          high: 1000, // creative tim: we recommend you to set the high sa the biggest value + something for a better look
          chartPadding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0,
          },
        },
      },
      {
        type: "Line",
        color: "info",
        title: "Completed Tasks",
        subtitle: "Last Campaign Performance",
        time: "campaign sent 26 minutes ago",
        data: {
          labels: ["M", "T", "W", "T", "F", "S", "S"],
          series: [[12, 17, 7, 17, 23, 18, 38]],
        },
        options: {
          lineSmooth,
          low: 0,
          high: 50, // creative tim: we recommend you to set the high sa the biggest value + something for a better look
          chartPadding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0,
          },
        },
      },
    ],




    
  }),

  computed: {
    sales: get("sales/sales"),
    totalSales() {
      return this.sales.reduce((acc, val) => acc + val.salesInM, 0);
    },
  },
};
</script>
