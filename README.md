# 👽 UFOs
An exercise on JavaScript, Bootstrap, and UFOs

# :one: Overview of the Project

The objective of the project was to create a website that displays a dynamic table with UFOs sightings in differnet parts of the United States and Canada.  The page contains a form to input and filter data.

The website was created using HTML for the basic structure and Bootstrap to control the look of the site.  There is also a `style.css` file that works in combination with Bootstrap to complete the decoration and feel of the website.

The site shows a table with the data of the sightings.  The data comes from a file called  `data.js` that contains an array with the keys of the sightings (datetime, city, state, country, shape, durationMinutes and comments).  Here is an example of the array:

```
{
    datetime: "1/1/2010",
    city: "bonita",
    state: "ca",
    country: "us",
    shape: "light",
    durationMinutes: "13 minutes",
    comments: "Three bright red lights witnessed floating stationary over San Diego New Years Day 2010"
  }
```
The page also has a form in which the visitor can input different values that are then used to filter the data of the table.

After the values of the form are entered, a Javascript file called `app.js` controls the behavior of the page. 

# :two: Results

The two main files that control the website are `index.html` and `app.js`.  These files will be explained in detail as shown below:

## `index.htm` File.  [The complete code of the file can be found here](https://github.com/Peteresis/UFOs/blob/9ee7249a47ac2c387fc3490e130e4ecf8b66d866/index.html)

Following is the Storyboard of the page.

![data-11-2-4-2-storyboard-of-the-website-with-components-neatly-organized](https://user-images.githubusercontent.com/98360572/165630723-20f72e15-db2e-4e31-88c1-68389514fcf0.png)

The code for each part is shown below:

### Initial Dependencies
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UFO Finder</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous" />
    <link rel="stylesheet" href="static/css/style.css">
</head>
```

### Navigation Bar
```
<div class="wrapper">
        <nav class="navbar navbar-dark bg-dark navbar-expand-lg">
            <a class="navbar-brand" href="index.html">UFO Sightings</a>
        </nav>
    </div>
```

### Page Header
```
<div class="jumbotron">
        <h1 class="display-4">The Truth is Out There</h1>
    </div>
```

### Article Title
```
<div class="container-fluid">
        <div class="row">
            <div class="col-md-3">
                <div>
                    <h3>UFO Sightings: Fact or Fancy?</h3>
                </div>
                <div>
                    <h3><small>Ufologists Weigh In</small></h3>
                </div>
            </div>
```

### Article Paragraph
```
<div class="container-fluid">
    .
    .
    .
    <div class="col-md-9">
                <p>Are we alone in the universe? For millennia, humans have turned to the sky to answer this question.
                    Now, thanks to research generously funded by W. Avy, a UFO-enthusiast and amateur ufologist, we can
                    supplement our sky-searching with data analysis.

                    "The release of this analysis is well-timed: It coincides with the celebration of World UFO Day,
                    which is a moment for ufologists around the world to connect, relax, and sample a range of
                    UFO-themed snacks," said Dr. Ursula F. Olivier, the world's preeminent expert on circular sightings.
                    "Citizen-scientists can be especially helpful in both cataloguing sightings—which is hugely helpful
                    for us in our search for aliens—and in helping us celebrate the work that has already been done,
                    such as this data visualization project, which will help us raise awareness of the ubiquity of
                    sightings!"

                    Not everyone is ready to celebrate, however. Local CEO and vocal anti-alien activist V. Isualize
                    reached out to our reporters to go on record as firmly opposed to any attempts to provide access to
                    this data. "If there are aliens, they certainly would like to be left alone," she stated, before
                    directing us to the Leave Aliens Alone (LAA) community engagement initiative she founded and funds.

                    So what do YOU think? Are we alone in the universe? Are aliens trying to contact us, or do they want
                    to be left alone? Dig through the data yourself, and let us know what you see.</p>
            </div>
```            

### Filters for the table
```
<div class="container-fluid">
        <div class="row">
            <div class="col-md-3">
                <form class="bg-dark">
                    <p>Filter Search</p>
                    <!-- Date Filter Field -->
                    <li class="list-group-item bg-dark">
                    <label for="date">Enter Date</label>
                    <input type="text" placeholder="1/10/2010" id="datetime" />
                    </li>
                    <!-- City Filter Field -->
                    <li class="list-group-item bg-dark">
                    <label for="city">Enter City</label>
                    <input type="text" id="city" />
                    </li>
                    <!-- State Filter Field -->
                    <li class="list-group-item bg-dark">
                    <label for="state">Enter State</label>
                    <input type="text" id="state" />
                    </li>
                    <!-- Country Filter Field -->
                    <li class="list-group-item bg-dark">
                    <label for="country">Enter Country</label>
                    <input type="text" id="country" />
                    </li>
                    <!-- Shape Filter Field -->
                    <li class="list-group-item bg-dark">
                    <label for="shape">Enter Shape</label>
                    <input type="text" id="shape" />
                    </li>
                </form>
            </div>
```
### Table of Sightings Data
```
<div class="col-md-9">
                <div class="col-md-9">
                    <table class="table table-striped">
                        <thead>
                            <tr>
                                <th>Date</th>
                                <th>City</th>
                                <th>State</th>
                                <th>Country</th>
                                <th>Shape</th>
                                <th>Duration</th>
                                <th>Comments</th>
                            </tr>
                        </thead>
                        <tbody></tbody>
                    </table>
                </div>
            </div>
```
### Final Dependencies
```
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/4.11.0/d3.js"></script>
<script src="static/js/data.js"></script>
<script src="static/js/app.js"></script>
```

## `app.js` File.  [Click here for the complete code of this file](https://github.com/Peteresis/UFOs/blob/09fd29a955358c362800db133666d4b8bfe8cb0b/static/js/app.js) 

This file is the brain behind the dynamic table.  It has several parts, but the most important are the three functions that do the heavy lifting to modify the dynamic table.

The file reads the data array from `data.js` using the following line:
```
// from data.js
const tableData = data;
```

### The `buildTable` function
This function uses the `data` variable and populates the rows of the HTML table with the unfiltered data from `data.js`. 

```
function buildTable(data) {
  // First, clear out any existing data
  tbody.html("");

  // Next, loop through each object in the data
  // and append a row and cells for each value in the row
  data.forEach((dataRow) => {
    // Append a row to the table body
    let row = tbody.append("tr");

    // Loop through each field in the dataRow and add
    // each value as a table cell (td)
    Object.values(dataRow).forEach((val) => {
      let cell = row.append("td");
      cell.text(val);
    });
  });
}
```

### The `updateFilters` function
This function 'listens' to changes done to the HTML page and records each change using this line of code:
```
// 2. Attach an event to listen for changes to each filter
d3.selectAll("input").on("change", updateFilters);
```
The IDs of the elements that were changed are saved into the variable 'filters'.  Then those IDs will be passed to the `filterTable` function used to filter the data of the table 
```
// 1. Create a variable to keep track of all the filters as an object.
var filters = {};

// 3. Use this function to update the filters. 
function updateFilters() {

  // 4a. Save the element that was changed as a variable.
  let element = d3.select(this);
  // 4b. Save the value that was changed as a variable.
  let elementValue = element.property("value");
  // 4c. Save the id of the filter that was changed as a variable.
  let elementId = element.attr("id");

  // 5. If a filter value was entered then add that filterId and value
  // to the filters list. Otherwise, clear that filter from the filters object.
  if (elementValue) {
    filters[elementId] = elementValue;
  }
  else {
    delete filters[elementId];
  }
  // Display the filters list on the console.
  console.log(filters);
  // 6. Call function to apply all filters and rebuild the table
  filterTable();

}
```
### The `filterTable` function
This function takes the IDs of each of the values recorded in the `filters` variable and uses them to check each row of the table to validate if the row contains the values in the filters.  If so, the row is added to the 'refreshed' version of the table, else the row is ignored.  The part of the code that creates the filtered table is
```
  // 10. Finally, rebuild the table using the filtered data
  buildTable(filteredData);
```

This is the complete code of the `filterTable` function
```
// 7. Use this function to filter the table when data is entered.
function filterTable() {

  // 8. Set the filtered data to the tableData.
  let filteredData = tableData;

  // 9. Loop through all of the filters and keep any data that
  // matches the filter values
  Object.entries(filters).forEach(([key, value]) => {
    filteredData = filteredData.filter(row => row[key] === value);
  });

  // 10. Finally, rebuild the table using the filtered data
  buildTable(filteredData);

}
```

# :three: Summary

The final product of the combination of the HTM and Java Script files produces this page:

## Unfiltered Version

![Unfiltered](https://user-images.githubusercontent.com/98360572/165642085-3c4b85ad-9a9f-4fdc-9aaf-da99a9750ffb.png)

## Filtered Version



# :four: References




