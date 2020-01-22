# ILWIS 3.8.6

## Changes
The following features were added/restored:
- Restored the on-screen digitizer (create and edit point map, create and edit segment map)
- Restored the MapView functionality (the composition of several layers can be stored as a MapView, in order to be re-opened at a later time)
- Added support for grid-like georeferences with thousands of control points; for now, such a georeference can only be imported from external data
- Added Triple Collocation application
- The mouse wheel now zooms in / out the MapWindow; if the previous behavior is required, this can be set in the ILWIS Preferences

## Bug fixes

- Revision of the annotations to make them work correctly: grid, graticule, class legend, value legend, map border, scale bar, north arrow, whitespace tool
- Revised the Georeference Tiepoints editor
- Revised the Hovmoller, Track Profile and Cross Section tools
- Revised the animations and the Animation Management tool
- Improved robustness and correctness of CSV file importing
- A maplist can now be exported as multiband GeoTiff, ERDAS or ENVI format
- Added a spatial index to speed up selection in feature maps (segments, polygons)
- Added light options to 3D Extrusion
- In 3D view, objects are no longer disappearing when zooming in too much
- In 3D view, polygons no longer blend with each other when they are too near
- Restored the 3D cursor in the 3D Stack tool
- In 3D view, when zooming close, the rotation point changes to the viewpoint instead of the gravity center, which makes navigation easier
- Pixel size of submap georefs of latlonwgs84 maps is now expressed in degrees (previously in meters)
- Many consistency improvements in the Create GeoReference forms
- Pixelinfo can now be re-opened after it is closed
- Now it is possible to change the line style for polygon boundaries and for segment maps
- Restored the 3D self-height option in Maplist animation
- GDAL-Importing a single file with a single layer no longer results in an object collection
- Added "Lambert Conformal Conic 1972", "Lambert Conformal Conic 2008" and "Lambert Conformal Conic 1SP"
- Now opening a MapList that is inside an ObjectCollection works
- Enabled coloring Bool layers (previously the defaults could never be changed)
- Importing data where the source and destination folders differ from the current catalog now works
- When the display attribute of a pointmap/segmentmap/polygonmap is set to a column that has undefineds, now the undefined objects are hidden
- In 3D view, after setting a map to use 3D-heights, it is now possible to set it back to "None"
- Table import is now protected against duplicate column names
- Added North Arrow
- Export via GDAL (e.g. GTiff) in a folder with spaces now works properly
- The DEM hydro processing functions are now able to work with raster images larger than 6000x6000 pixels, without giving "Out of Memory" errors
- Edit->Copy on a MapWindow with a Legend now also copies the legend-texts
- Added support for Edit->Copy on a MapWindow containing a Space Time Cube and related elements (Space Time Path, Stations, 3D Windrose and Flocks)
- Choosing "black" as the symbol color for single colored maps now makes the symbols black instead of transparent
- The order of the SEBS applications menu is now the working order, instead of alphabetic
- The Table to Pointmap operation now gives correct values to the output map
- Solved occasionally showing '*' instead of the projected coordinates in the statusbar of the MapWindow
- In WMS/OSM services, added support for tiles with color palette, support for https, and support for additional request parameters
- The WMS/OSM tiles now connect seamlessly, if the available OpenGL version is at least 1.2
- Revised the Iso-lines application; now all contour levels are generated, and the "intervals" option works
- Solved: fonts (labels, annotations, space time cube axes and coordinates) did not display correctly on some graphics cards, looking transparent
- Viewing a classmap or a class attribute and turning classes on/off through the representation legend now works properly
- Revised the polygon to raster and the raster to polygon applications
- Solved: The Unique ID application was forgetting the first point
- The grid on curved images (using a tiepoint georeference set to "Full Second Order") is now drawn "curved"
- Graticule spacing is now expressed in Degrees, Minutes, Seconds (instead of Decimal Degrees)
- MapCalc now also works with images that are more than 32768 pixels wide; the limit is increased to 2 billion pixels wide(!)
- Added the Random Colors option to the possible color schemes for class maps
- Added option "Break Dependencies" on a "Dependent" Georeference like SubMap, which will replace it with a standalone Georeference Corners when possible
- Restored the ilwis.exe option –CR <command> to start ILWIS in hidden-mainwindow mode; to start it without a command, the option is "–CR hide"; this is different than the -C option which will execute the command and close ILWIS
- Value images with very few values (e.g. 2 values) will now display with the correct colors
- SegmentMapGlue is now able to correctly glue segment maps that have different coordinate systems
- Importing tiff files with data type "unsigned integer" now works correctly (the range is 0-65535 instead of 0-32767)
- Operations "Iso Lines", "Voronoi" and "Point to Segment" are now properly categorized in the Right-mouse-button menu
- Wildcards are now allowed in command "crmaplist", for easier creation of maplists on the command-line
- It is now possible to use an attribute of domain "Color" to color a layer
- The Aggregate Maplist application is now also able to work with large maplists (previously it crashed after a certain threshold)
- Re-added the operations MapKrigingSimple, MapKrigingOrdinary, MapKrigingAnisotropic and MapKrigingUniversal
- The export of Color images into GeoTiff via the ILWIS export method is made faster
- The default color for single colored maps can now be set in the ILWIS Preferences
- Added more representations for value maps
- Many other minor bugs and glitches are solved

# ILWIS 3.8.5

## Changes
The following features were added:

- Map Window selections: added the option to select polygons (previously only points and segments could be selected)
- Ellipsoidal Plate Carree coordinate system added
- Table Join operation: added the missing option to join a column of type Coord, making it possible to e.g. join the coordinates of a pointmap to its attribute table
- Space Time Cube: added the 3D windrose option; added XT, XY, YT lines
- Applications: added Parallax Correction of clouds for MSG images (under Image Processing), and Probability Density raster generation (frmprobabilitydensity)

## Bug fixes

- Improved compatibility on computers with Intel HD Graphics or combo-graphics hardware (potential crashes when opening a Map Window). Therefore the "Software Rendering" option in the ILWIS Preferences can be disabled for those who enabled it as a workaround.
- Restored Epipolar Stereopair functionality (both creation and viewing in the stereoscope window)
- Restored Import->ILWIS->TIFF functionality (message DATUM.DEF was not found)
- Improved stability and usability in the Import functionality for both maps and tables, and recognition of more projections (all Import methods, including ILWIS, GDAL and PostgreSQL)
- Improved stability in the Export functionality (both ILWIS and GDAL)
- Calling external commands works again (message Exit Code 1)
- Restored rectangle-based Zoom-Out functionality
- Restored No-Zoom option for raster images that maps each raster pixel to an on-screen pixel. Use the "Global Tools->Geometry->GeoReference" tool and select the georeference that corresponds to the raster image, in order to display it unprojected.
- Improved table Window summary statistics for boolean columns and for selected records
- Improved interactive slicing application
- Solved the problem whereby the Representation Editor showed a wrong color ramp in the preview
- Solved potential crashes and wrong results in the vector operations Union and Intersect
- Solved "vector<T> too long" error when opening corrupted polygon maps
- Improved per-class hatching and transparency for polygon layers
- Solved potential crashes when opening "Use As" data
- Color Composite: the application now creates 24 bits files when this option is selected (previously it was always 8 bits)
- MapGlue: gluing large images is now possible
- Open Street Map: corrected the zoom level making the labels readable, and solved potential deadlocks and crashes. Known issue: OSM may not show in 3D-view, depending on the viewing angle.
- DEM Hydro-Processing functions: solved potential "vector <T> too long" and "Find Error" problems, and the menu is now arranged in the recommended workflow order.
- Maplist Statistics: solved the "Encountered an improper argument" error so it works again
- Solved inconsistent behavior in iff statement when one of the parameters is undef (?): iff (a,b,?) is now the same as iff (not a,?,b)
- Solved crashes or empty results in copying a map to the clipboard when using WMS and Open Street Map, or when using Software Rendering
- Solved crashes and inconsistent behavior in the Cross Section, Hovmoeller and Track Profile tools
- Solved many random crashes in ILWIS

# ILWIS 3.8.4

## Bug fixes

- improvements in the SEBS application set
- improvements to real time animations
- improvements in the SMCE application
- improved copying of unicode string to clipboard
- removal of 2 GB limit on rasters
- improved recognition of projections from the gdal driver
- export using gdal works properly again
- solved several issues with the creation of coordinate systems
- missing edit fields on the script window (parameter tab) are accessible
- segment maps with real values as segment value are now stored correctly
- .smc files are now copied correctly
- use-as original source data is not deleted when a delete command is done on the ILWIS-proxy
- Due to some licensing issues, the triangulation code used to draw polygons was replaced.

## Changes
The following new features were added:

- a break dependency option to dependent georefs (e.g. submap), for proper exporting georeferenced data
- support for opening/storing data from Postgres/Postgis databases
  - tables
  - vector maps
  - rasters
  - Use the import form to enter the location of the database as http://servername:port/databasename and use the options form for logging in.
- new application PointMapCross
- new application MapColorFromRpr
- experimental WFS support (through import form --> OGC option)
- variable DPI option when copying mapwindow to clipboard
- copy coordinate value under the mouse through the right mouse menu
- synchronization between space-time cube and animated mapwindow
- PCP (Parralel Coordinate Plot), accessible through the display options of a point layer
- time profile graph for space-time cube
- Script : Colored hill shade from a DEM

# ILWIS 3.8.3

## Bug fixes

- local mapwindow histogram functions again
- legend in layer tree updates properly when stretch ranges change
- map window legend updates properly when stretch ranges change
- views work again, however the (new) view system is not backward compatible with the earlier version
- legend remains at the same place when legend property form is opened
- copy view works properly again, all relevant files are also copied
- resolved conflicts between point properties by rpr and global point properties
- resolved conflicts between line properties by rpr and global line properties
- re-enabled stretching for attribute maps
- resolved raster visualization problems on low-end Intel on board graphic chip. An option in the preferences now to switch to software-based OpenGL. Although it is slower, it doesn't have the Intel chips' OpenGL problems.
- proper animation information update to mapwindow
- solved synchronization rounding bug when synchronizing animations with different index resolutions
- solved several issues in the interactive representation
- correct sorting of the columns druing table selections
- ILWIS skips corrupt polygons when reading data

## Changes
New features:

- header information is added to csv/ssv files when importing
- layer tree now has user defined step and ranges in addition to the auto mode
- map window legend allows user defined step and ranges in addition to the auto mode
- legend background (if enabled) incorporates title
- new Zoom to feature(s) - now it is possible to zoom to selected features in feature maps
- rpr properties changes in mapwindow are partially copied
- a track can now be saved as a segment map and tracks can also be loaded as segment map for getting identical tracks on different maps
- labels added (again) for points and polygons

# ILWIS 3.8.2

## Changes
New features:

- extended selection options for vector maps and attribute tables
- ID/Unique ID maps may have their own color scheme when rendering
- new IsoCluster application

Improvements:

- improved import shape file multi shapes
- removal of import errors about coordinate system
- improved focus of drawer tools status: active/inactive
- corrected storage of user options for point symbolization
- improved map view save function
- largely increased performance for clean up/close large vector maps
- increased performance for displaying vector maps with attributes
- removed several 3D grid issues
- fixed 3D panning

# ILWIS 3.8.1

## Changes
New features include

- access to OpenStreetMap (Internet access required) - add OSM layer to ILWIS layer
- hatching for polygons,
- Space Time Cube - tool for 3D analysis of spatial, temporal events,
- coupling of attribute table selection and map selection - selection of attribute table rows also selects corresponding feature,
- batch import (use wild cards in import names).

## Bug fixes

- fixed various bugs when importing any vector file (including shape files),
- improved handling of WMS servers,
- resolved bug when importing raster file (crashed when opening the file, but was fine when ILWIS was reopened),
- resolved bug when two display tools where trying to capture the mouse at the same time,
- removed layers from the pixel info when the layer is removed from the layer tree,
- dates are now correctly read in the date form.

# ILWIS 3.8

ILWIS 3.8 represents a major upgrade from ILWIS 3.7. Changes and improvements have mainly focussed on visualization, however, additional issues have been addressed.

## Changes

Visualization

- General
  - Display options form has been replaced by an extended and improved Layer tree on the left side of the map window.
  - Pixel info has a permanent location on the lower left side of the map window.
  - The map window has a command line which works the same as the main window’s command line. Maps calculated in this command line are automatically added to the map window.
  - Map window menus have been substantially reduced. Much of their functionality has been moved to the Layer tree.
  - LatLon maps can show their coordinates as decimal coordinates. This toggle can be found in the Options/Metric Coordinates menu.
  - Visualizations can be shown full screen without any UI elements. This toggle can be found in the Options/Full Screen menu.
  - Automatic reprojection and resampling is available. The map window can display maps of different geometries (both raster and vector) and will automatically morph the maps to a target geometry. The geometry of the map can be changed on-the-fly.
  - Annotation is available in the map window for legends (per layer), boundaries and scale bar.
  - The tree node "Display Tools" has a context menu that controls the visibility of tools.
  - Base maps have been added to the system folder. This (small) set of maps can be used as background/context layers. Each base map acts as a system object.
  - Map backgrounds and surroundings can be changed with respect to color and transparency.
  - The distance measurer can be used on paths (multiple line segments) with the help of the the ctrl button.

- Layer tree
  - The previous layer tree has been massively extended. It now replaces part of the main menu. "Tools" that control a coherent subset of visualization properties are available at all levels of the tree. They can be global or have effect on only one layer.

- 2D maps
  - Raster maps
    - Enhanced performance
    - Interactive representation value creation
  - Polygon maps
    - Enhanced performace. The first time a polygon map is shown it generates a support file (triangulation) which it uses subsequently.
    - Boundaries and Areas are separate entities with separate properties.
  - Segment maps
    -  Enhanced performance. All vector maps now use a spatial indexing scheme to quickly retrieve the relation between a coordinate and its features. This speeds up the retrieval of segment values at a particular location.
  - Point maps
    - Symbolization has been completely changed. There is now one consistent system that uses small "svg-like" text files to define the symbolization.
  - Object collections
    - An object collection of maps of the same type and domain can function as a single layer. As a result, all maps are stretched in the same way.
  - Map lists
    - Dedicated tools for map lists. Apart from animations, a set of dedicated tools has been implemented specifically for map lists.
    - Cross section. A graph can be displayed for a point location. It shows all the values of the map list for that point. Multiple points can be defined with the help of the ctrl button.
    - Hovmoeller diagram. A pattern detection representation of lines drawn on a map can be combined with a map list to produce a Hovmoeller diagram.
- Tools
  - Track profile. This displays a profile graph of a path on the map. A multi-segment path can be created with the help of the ctrl button. Multiple maps can be added to the profile graph to demonstrate relationships between the profiles of these maps.
  - Transparency. This can be added at many levels and mostly on-the-fly. Transparency follows a 0 (no transparency) to 100 (fully transparent) scale. It can be applied to the following objects/properties:
    - Layers: raster, polygon, segment, point
    - Areas and/or boundaries of polygons
    - Lines of grid
    - Extrusions (3D)
    - partial transparent interactive representation ???
    - Selections of polygon maps based on class
    - Selections of raster maps based on numerical value
  - Interactive value stretching. Dymamically adapts stretch values based on a set of sliders (min,max).
  - Attribute tool. The display attribute (column) can be changed on the fly.
  - Layer applications. All applications relevant for a certain layer type can be started from the Layer tree. Any maps produced here are immediately added to the map window.
  - Point editor and segment editor. These tools have been rewritten and are now part of the Layer tree.

- 3D Maps
  - All layers can be shown in 3D via a simple toggle.
  - Z coordinates can be any numerical value source; e.g. raster maps, attribute columns.
  - Rotation can be carried out by pressing the ctrl button and the left mouse button simultaneously, zooming via ctrl button and the mouse wheel, and panning with the ctrl button and the right mouse button.
  - All 3D properties are controlled by the 3D properties tool which is activated by the context menu of the display options node.
  - 3D grid creation is possible.
  - Tools
    - 3D properties. Controls Z-data source, scaling and offsets and the use of extrusions (and properties).

- Animations (formerly slide show)
  - Animations can be made from map lists (raster) or object collections (vector).
  - Animations function as a normal layer in the map window. Tools applicable for single layers, work for animations.
  - Animations work in 3D
  - Multiple Animations can run in one or more map windows (however, there may be performance issues).
  - Animations may use index information or real time information. Real time information is derived from a time column in a map list's attribute table.
  - Several animations may be synschronized according to index information or real time.
  - Animations can be saved as .avi files.
  - Tools
    - Highlight tool. Singles out a selection on the map to highlight during animation
    - Threshold tool. Changes display colors of pixels above and/or below a certain threshold based on an attribute table. This tool can be accessed from the animation management form.


## New applications

  - MapListCondense: Condenses a map list into a smaller map list, i.e. aggregates maps into one map according to a step size and specific aggregation rules.
  - MapListExpand: Expands the map list and creates intermediate maps based on certain interpolation rules, i.e. the reverse of MapListCondense.
  - MapListChangeDetection: Makes use of a number of simple change detection schemes to determine changes in map lists.
  - MapAggregateMaplist: Aggregates a map list in a single map based on certain aggregation rules.
  - TableAttributeFromMapList: Creates an attribute table for a map list based on aggregated numbers from maps in a map list
  - ColumnAttributeFromMapList: Creates an attribute column for a map list based on aggregated numbers from maps in an existing map list table
  - TableCreateTimeColumn: Creates a time column in a table. The time column is derived from a map list based on a (user-defined) pattern in the name of the map list.


## General

  - Map list and Object collection can have an attribute table. Each record matches the corresponding index in the list/collection.
  - The Operation list has been extended to include a "finder" which filters the list.
  - A Spanish UI translation has been included.
  - The help system has been decompiled and now uses html files instead of the bundled (chm) format.
  - The domain "time" has been included. This handles date/time information based on an ISO standard.
  - ILWIS now has a server component that can run as an (ILWIS-specific) application server. A WPS server has been implemented.
