---
created: 2024-08-21T10:46:30-05:00
modified: 2024-08-28T12:34:59-07:00
---
# Charts Example

#### random
```tracker
searchType: frontmatter
searchTarget: steps
folder: 03 - Periodic/01 - Daily
startDate: 2024-08-19
endDate: 2024-08-25
summary:
     template: "Average: {{average()}} steps"
```


#### random 2
```tracker
searchType: frontmatter
searchTarget: steps
folder: 03 - Periodic/01 - Daily
summary:
     template: "Average: {{average()}} steps"
```

#### Week

#### The base data
```dataview
TABLE steps
FROM "03 - Periodic/01 - Daily" 
GROUP BY dateformat(file.day, "yyyy-'W'WW") as week

FLATTEN round(sum(nonnull(rows.steps)), 10)/(length(nonnull(rows.steps))) as steps 
```

```dataview
TABLE weight, steps
FROM "03 - Periodic/01 - Daily" 
GROUP BY dateformat(file.day, "yyyy-'W'WW") as week

FLATTEN trunc(sum(nonnull(rows.weight)))/length(nonnull(rows.weight)) as weight
FLATTEN trunc(sum(nonnull(rows.steps)))/length(nonnull(rows.steps)) as steps 
```


####  The bar chart
```dataviewjs
const result = await dv.tryQuery(`
  TABLE weight, steps 
  FROM "03 - Periodic/01 - Daily" 
  GROUP BY dateformat(file.day, "yyyy-'W'WW") as week 

  FLATTEN sum(nonnull(rows.weight))/length(nonnull(rows.weight)) as weight
  FLATTEN sum(nonnull(rows.steps))/length(nonnull(rows.steps)) as steps 
`)

const myHeaders = result.headers
const myLabels = result.values.map(d => d[0])
const myData = result.values[0].map((_, colIndex) => result.values.map(row => row[colIndex]))

const chartData = {
  type: 'bar',
  data: {
    labels: myLabels,
    datasets: [{
      label: myHeaders[1],
      data: myData[1],
      backgroundColor: 'rgba(255, 99, 132, 0.2)',
      borderColor: 'rgba(255, 99, 132, 0.9)',
      borderWidth: 1,
      yAxisID: 'left-y-axis'
    }, {
      label: myHeaders[2],
      data: myData[2],
      backgroundColor: 'rgba(99, 255, 132, 0.2)',
      borderColor: 'rgba(99, 255, 132, 0.9)',
      borderWidth: 1,
      yAxisID: 'right-y-axis'
    },
    ]
  },
  options: {
    plugins: {
      legend: {
        position: 'bottom'
      }
    },
    scales: {
      'left-y-axis': {
        title: {
          display: true,
          text: "Percentage"
        },
        type: 'linear',
        position: 'left'
      },
      'right-y-axis': {
        title: {
          display: true,
          text: "Hours"
        },
        type: 'linear',
        position: 'right'
      }
    }
  }
}

window.renderChart(chartData, this.container)
```


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