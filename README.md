# vue-ganttastic
<img src="https://user-images.githubusercontent.com/28678851/77186503-45358300-6ad3-11ea-9392-7f670eb1ca8c.png" width="600"/>

A simple and easy-to-use Gantt chart component for Vue.js

## Homepage
[Homepage of the project](https://infectoone.github.io/vue-ganttastic-homepage/#/docs)

## Installation
If you use <kbd>npm</kbd> in your project, you can install vue-ganttastic simply with:
```
npm install vue-ganttastic
```
If you do not use <kbd>npm</kbd> in your project, you may alternatively copy and paste all files from the 
<code>components</code> folder and
and import the components <code>GGanttChart</code> and <code>GGanttRow</code> wherever you need them

## Basic Usage
Import the components <code>GGanttChart</code> and <code>GGanttRow</code>.  
Use <code>g-gantt-chart</code> in your template, pass the desired chart start and chart end time as props (<code>chart-start</code> and <code>chart-end</code>) and add <code>g-gantt-row</code>s
to the default template slot.  
Pass an array containing your bar objects to every row using the <code>bars</code> prop, while specifying the name of the properties in your bar objects that stand for the bar start and bar end time using the props <code>bar-start</code> and <code>bar-end</code>  

For more detailed information, such as how to style the bars or additional configuration options, please refer to the [docs](https://infectoone.github.io/vue-ganttastic-homepage/#/docs) on the project's homepage (coming soon).

The following code showcases a simple usage example in a .vue SFC (Single File Component)
```html
<template>
  ...

  <g-gantt-chart
    :chart-start="myChartStart"
    :chart-end="myChartEnd"
  >
    <g-gantt-row
      v-for="row in rows"
      :key="row.label"
      :label="row.label"
      :bars="row.bars"
      bar-start="myStart"
      bar-end="myEnd"
    />
  </g-gantt-chart>

  ...
</template>

<script>

import {GGanttChart, GGanttBar} from 'vue-ganttastic'

export default {

  ...

  components:{
    GGanttChart,
    GGanttBar
  },

  data(){
    return {
      myChartStart: "2020-03-01 00:00",
      myChartEnd: "2020-03-03 00:00",
      rows: [
        {
          label: "My row #1",
          bars: [
            {
              myStart: "2020-03-01 12:10",
              myEnd: "2020-03-01 16:35"
            }
          ]
        },
        {
          label: "My row #2",
          bars: [
            {
              myStart: "2020-03-02 01:00",
              myEnd: "2020-03-02 12:00"
            },
            {
              myStart: "2020-03-02 13:00",
              myEnd: "2020-03-02 22:00"
            }
          ]
        }
      ]
    }
  }

  ...

}
</script>

```

## Contributing
Pull requests are warmly welcomed, while every major change or proposal ought to be discussed in an issue first. As the project is still new, I will gladly accept suggestions, proposals, contributions etc.

### Contributing - How to run the project
  1. Clone the project
  2. Install the Vue CLI service, if you don't already have it installed:
      ```
        npm install -g @vue/cli
        npm install -g @vue/cli-service-global
      ```
  3. <code>Playground.vue</code> is a dedicated Vue SFC where all    Vue-Ganttastic components can be
     played around with and tested out. Get it running using:
      ```
        vue serve src/Playground.vue
      ```
## Dependencies
[Moment.js](https://momentjs.com/)

## License
[MIT](https://choosealicense.com/licenses/mit/)
