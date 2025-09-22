# Packages

Packages in JavaScript are supported using ESM. You can use a third-party JS CDN to load third-party packages. Some possible CDNs include:&#x20;

* We recommend using esm.run from [https://www.jsdelivr.com/esm](https://www.jsdelivr.com/esm)
* [https://www.unpkg.com](https://www.unpkg.com)
* [https://esm.sh](https://esm.sh)

Below are examples on how to correctly use esm.run to import packages in JavaScript.&#x20;

## Examples

Below are some common examples of libraries, imported using esm.run. Many more libraries are available for use in Quadratic and you can use the JS CDN of your choice. Below is how to use esm.run, which we recommend as a top option.

### Charting&#x20;

Chart.js is the only charting library in JavaScript supported in Quadratic.&#x20;

```javascript
import Chart from 'https://esm.run/chart.js/auto';
```

### Analytics

D3.js is a common analytics library for JavaScript.

```javascript
import * as d3 from 'https://esm.run/d3';

let my_data = [1,2,3]
let sum = d3.sum(my_data)
return sum
```

Brain.js is a Machine Learning library that works in Quadratic

```javascript
import * as brain from 'https://esm.run/brain.js';

// provide optional config object (or undefined). Defaults shown.
const config = {
  binaryThresh: 0.5,
  hiddenLayers: [3], // array of ints for the sizes of the hidden layers in the network
  activation: 'sigmoid', // supported activation types: ['sigmoid', 'relu', 'leaky-relu', 'tanh'],
  leakyReluAlpha: 0.01, // supported for activation type 'leaky-relu'
};

// create a simple feed-forward neural network with backpropagation
const net = new brain.NeuralNetwork(config);

await net.train([
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] },
]);

const output = net.run([1, 0]); // [0.987]

return output[0]
```

