# Return data to the sheet

Single values, arrays, and charts are the JavaScript types that can be returned to the sheet. Any data can be structured as an array and returned to the sheet.&#x20;

## Single value&#x20;

```javascript
// from variable with assigned value
let data = 5; 

// return this value to the sheet
return data;
```

## 1-d array&#x20;

```javascript
let data = [1, 2, 3, 4, 5];

return data;
```

## 2-d array&#x20;

```javascript
let data = [[1,2,3,4,5],[1,2,3,4,5];

return data;
```

## Charts

```javascript
import Chart from 'https://esm.run/chart.js/auto';

let canvas = new OffscreenCanvas(800, 450);
let context = canvas.getContext('2d');

// create data 
let data = [['Africa', 'Asia', 'Europe', 'Latin America', 'North America'],[2478, 5267, 734, 784, 433]]

// print data to console 
console.log(data);

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
