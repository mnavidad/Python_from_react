UFO Sighting Exploration with ArcGIS API

This Python script leverages the ArcGIS API to visualize UFO sighting data and search for the nearest sighting based on a user-entered city name.

Requirements:

ArcGIS API Python library (arcgis)
ipywidgets
IPython.display (for interactive display in notebooks)

Instructions:

Configure ArcGIS Connection:

Replace 'home' in gis = GIS("home") with your valid ArcGIS Online username or organization URL.
Alternatively, create a new ArcGIS Online project and share the UFO sightings feature layer publicly. Obtain the layer URL and update the ufo_layer_url variable.
Run the Script:

Execute the script in a Jupyter Notebook environment for interactive exploration.
The code will display a map and a search bar.
Search for UFO Sightings:

Enter a city name in the search bar.

Click the "Search" button.

The map will zoom to the specified city, and the script will search for the nearest UFO sighting.

If a sighting is found, a popup will display details like location, date, description, and distance from the city.

If no sightings are found, an informative message will be displayed.

Code Structure:

Import Libraries:

Essential modules for interacting with ArcGIS, performing geospatial operations, and creating a user interface are imported.
Initialize ArcGIS Connection:

Establishes a connection to your ArcGIS Online account using the provided username or organization URL.
Create a WebMap:

Creates a new WebMap object, which serves as the canvas for visualizing the UFO layer.
Define Basemap:

Sets the basemap style to "streets-navigation-vector" for a clear view of locations.
Load UFO Layer:

Defines the URL of the UFO sightings feature layer and creates a FeatureLayer object to interact with the data.
Includes a check to ensure the layer is loaded successfully.
Add Layer to the Map:

Adds the UFO sightings layer to the previously created WebMap.
Define Popup Template:

Creates a formatted popup template that displays informative details about each UFO sighting when clicked.
Set Popup Template:

Associates the designed popup template with the UFO sightings layer for enhanced visualization.
Create MapView Widget:

Initializes a MapView widget using the established GIS connection, webmap, and initial zoom level and center coordinates.
Search City Function:

Takes user input as the search city name.
Uses geocode to find the geolocation of the city.
If a city is found, queries the UFO layer within a certain radius of the city center.
Utilizes the find_nearest_feature helper function to identify the closest sighting.
Zooms the map to the city location and displays a popup with details of the nearest sighting (if found) or informs the user if no sightings exist.
Helper Function:

Iterates through UFO features and calculates the distance from the provided city point.
Identifies the closest sighting based on the minimum distance.
Create Search Box and Button:

Generates an interactive search bar using the Text widget for users to enter city names.
Creates a button using the Button widget labeled "Search" to trigger the search function upon clicking.
Display Widgets and Map:

Utilizes ipywidgets.HBox to display the search bar and button in a horizontal layout.
Employs IPython.display.display to render the widgets and map view in the notebook environment.
Additional Notes:

Feel free to adjust search radius, distance units, or map center coordinates as needed.
Remember to replace the placeholder ArcGIS connection details with your valid credentials.