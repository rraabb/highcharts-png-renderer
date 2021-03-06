highcharts-png-renderer
=======================

Renders charts based on Highcharts through Phantom.js as PNG files

# Usage

* Edit config.json to match your preferences
* Run `phantomjs run.js`
* Perform POST-requests against / where the body of the request is the
  JSON-options you would normally pass to the Highcharts constructor

# Example:
POST to / with the following request body:

```JSON
{
    "chart": {
        "type": "line",
        "marginRight": 130,
        "marginBottom": 25
    },
    "title": {
        "text": "Monthly Average Temperature",
        "x": -20
    },
    "subtitle": {
        "text": "Source: WorldClimate.com",
        "x": -20
    },
    "xAxis": {
        "categories": ["Jan", "Feb", "Mar", "Apr", "May", "Jun",
            "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
    },
    "yAxis": {
        "title": {
            "text": "Temperature (°C)"
        },
        "plotLines": [{
            "value": 0,
            "width": 1,
            "color": "#808080"
        }]
    },
    "legend": {
        "layout": "vertical",
        "align": "right",
        "verticalAlign": "top",
        "x": -10,
        "y": 100,
        "borderWidth": 0
    },
    "series": [{
        "name": "Tokyo",
        "data": [7.0, 6.9, 9.5, 14.5, 18.2, 21.5, 25.2, 26.5, 23.3, 18.3, 13.9, 9.6]
    }, {
        "name": "New York",
        "data": [-0.2, 0.8, 5.7, 11.3, 17.0, 22.0, 24.8, 24.1, 20.1, 14.1, 8.6, 2.5]
    }, {
        "name": "Berlin",
        "data": [-0.9, 0.6, 3.5, 8.4, 13.5, 17.0, 18.6, 17.9, 14.3, 9.0, 3.9, 1.0]
    }, {
        "name": "London",
        "data": [3.9, 4.2, 5.7, 8.5, 11.9, 15.2, 17.0, 16.6, 14.2, 10.3, 6.6, 4.8]
    }]
}
```

Will give the following image as response body:

![Example output](https://raw.github.com/vgnett/highcharts-png-renderer/master/example.png)

# License
MIT, see LICENSE

# Credits
Thrown together by Espen Hovlandsdal loosely based on the the official
Highcharts rendering server

