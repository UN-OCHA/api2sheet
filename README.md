# api2sheet

Api2sheet is a Javascript utility that tries to make requests to an API and outputs the results in a google spreadsheet.

## Installation

You can either download the index.html file and run it from localhost or, even easier, run it from https://guillaumev.github.io/api2sheet

## Usage

api2sheet takes the following arguments to run:

 * Spreadsheet ID: enter the google spreadsheet ID. For example, if the URL of your spreadsheet is https://docs.google.com/spreadsheets/d/1Y4QAxuRkkKLvlOc4UrU0N2fqypDG1dug70VFSna1MT8/, enter 1Y4QAxuRkkKLvlOc4UrU0N2fqypDG1dug70VFSna1MT8
 * Sheet Name: enter the name of the sheet in which you want to import data
 * API URL: enter the API query from which you want to extract data. api2sheet will always perform a GET request.
 * API Key: if the API requires an API key, enter it here. The API key will be added to the Authorization header in the format "Authorization: Bearer <API_KEY>"

### Pagination

api2sheet will try to get ALL results from your API query, even if they are in multiple pages. You therefore need to think through your API query carefully, because depending on the total number of results your query will return, the number of HTTP requests made to the API can be high. The total number of results returned by the API can be provided in 2 different ways:

 * Via the "X-Total-Count" header
 * Directly in the JSON results, via a "count" attribute (in this case, api2sheet will expect to retrieve data in the "data" attribute)

