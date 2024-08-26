---
created: 2024-08-21T10:46:30-05:00
modified: 2024-08-21T16:13:14-05:00
---
# Charts Example

#### Weight as Property

```dataviewjs

dv.span("**Weight Log**")

const pages = dv.pages('#daily-note').sort(p => p.file.name)
const dates = pages.map(p => p.file.name).values
const weight = pages.map(p => p.weight).values

const chartData = {

type: 'line',
data: {
  labels: dates,
  datasets: [{
   label: 'Weight (lbs)',
   data: weight,
   pointRadius: 5,
   pointBackgroundColor: [
    'rgba(46, 204, 113, 1)'
   ],
   pointBorderColor: [
    'rgba(207, 0, 15, 1)'
   ],
   borderColor: [
    'rgba(46, 204, 113, 1)'
   ],
   borderWidth: 1.5,
   spanGaps: true,
  }],
},
};

window.renderChart(chartData, this.container)
```

``` tracker
searchType: frontmatter
searchTarget: weight
folder: 03 - Periodic
summary:
	template: "Minimum: {{min()}} lbs \n
			   Maximum: {{max()}} lbs \n
			   Average: {{average()}} lbs \n
			   Net Loss: {{max()-min()}} lbs"

```

#### Steps as Property

```dataviewjs

dv.span("**Steps Log**")

const pages = dv.pages('#daily-note').sort(p => p.file.name)
const dates = pages.map(p => p.file.name).values
const steps = pages.map(p => p.steps).values

const chartData = {

type: 'line',
data: {
  labels: dates,
  datasets: [{
   label: 'Steps',
   data: steps,
   pointRadius: 5,
   pointBackgroundColor: [
    'rgba(46, 204, 113, 1)'
   ],
   pointBorderColor: [
    'rgba(207, 0, 15, 1)'
   ],
   borderColor: [
    'rgba(46, 204, 113, 1)'
   ],
   borderWidth: 1.5,
   spanGaps: true,
  }],
},
};

window.renderChart(chartData, this.container)
```

#### Distance as Property

```dataviewjs

dv.span("**Distance Log**")

const pages = dv.pages('#daily-note').sort(p => p.file.name)
const dates = pages.map(p => p.file.name).values
const distance = pages.map(p => p.distance).values

const chartData = {

type: 'line',
data: {
  labels: dates,
  datasets: [{
   label: 'Distance (miles)',
   data: distance,
   pointRadius: 5,
   pointBackgroundColor: [
    'rgba(46, 204, 113, 1)'
   ],
   pointBorderColor: [
    'rgba(207, 0, 15, 1)'
   ],
   borderColor: [
    'rgba(46, 204, 113, 1)'
   ],
   borderWidth: 1.5,
   spanGaps: true,
  }],
},
};

window.renderChart(chartData, this.container)
```