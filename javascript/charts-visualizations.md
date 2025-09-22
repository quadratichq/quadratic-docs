# Charts/visualizations

Charts are supported in JavaScript using [charts.js](https://www.chartjs.org/). No other libraries are currently supported.&#x20;

## Bar chart

```javascript
import Chart from 'https://esm.run/chart.js/auto';

let canvas = new OffscreenCanvas(800, 450);
let context = canvas.getContext('2d');

// create data 
let data = [['Africa', 'Asia', 'Europe', 'Latin America', 'North America'],[2478, 5267, 734, 784, 433]]

// print data to console 
console.log(data)

// Create chart 
new Chart(canvas, {
    type: 'bar',
    data: {
        labels: data[0],
        datasets: [
        {
            label: "Population (millions)",
            backgroundColor: ["#3e95cd", "#8e5ea2","#3cba9f","#e8c3b9","#c45850"],
            data: data[1]
        }
        ]
    },
    options: {
        legend: { display: false },
        title: {
        display: true,
        text: 'Predicted world population (millions) in 2050'
        }
    }
});

// return chart to the sheet 
return canvas;
```

## Line chart

```javascript
import Chart from 'https://esm.run/chart.js/auto';

let canvas = new OffscreenCanvas(800, 450);
let context = canvas.getContext('2d');

// create data 
let data = [['1999', '2000', '2001', '2002', '2003'],[2478, 5267, 734, 784, 433]]

// print data to console 
console.log(data)

// Create chart 
new Chart(canvas, {
    type: 'line',
    data: {
        labels: data[0],
        datasets: [
        {
            label: "Population (millions)",
            backgroundColor: ["#3e95cd", "#8e5ea2","#3cba9f","#e8c3b9","#c45850"],
            data: data[1]
        }
        ]
    },
    options: {
        legend: { display: false },
        title: {
        display: true,
        text: 'Predicted world population (millions) in 2050'
        }
    }
});

// return chart to the sheet 
return canvas;
```
