# Data File String Example

The string begins with the tab name, for non web application purposes, this may be omitted. Next is the delimitor []. Followed is the internal geometric shape, the "cube" followed by the next delimitor type ':'. The delimitor ':' is used to separate geometric properties. In the case of this cube, only two properties need be provided, these include its label and its edge length defined in millimeters.

The initial form is always SHAPE_TYPE:LABEL. The LABEL is a base64 encoding. The properties which follow are numerics exclusively relative to the shape type. For an example, a cube will have less properties than a cylinder and indeed the cylinder lesser properties than a stadium frustum.

The '#' delimitor is used to split shape types. The @ delimitor splits the shapes from the scaling constants. The order of these scales is mapped on a 1-to-1 basis with the geometric shapes. These scaling constants allow subtractive manipulation to represent more complex volumes. This option persists for power users whom require this cutting edge precision.

Each scaling constant is separated by the '=' delimitor. Its data type is that of a floating point and its interval is equal to [-1, 1]. By default, all objects have a scale set to 1.

# File Data Format IO

The clear text file format for imports / exports into live web application is described here.

# List of Delimitors

| Delimitor | Description                                                                           | Priority |
|:---------:|---------------------------------------------------------------------------------------|----------|
| ~         | (reserved) splits multiple tabs iff export is a workspace export (not always present) |--- 01 ---|
| @         | splits scaling constants, the order is equal to the object ordering                   |--- 02 ---|
| []        | splits name of tab (left) and volume list data (right)                                |--- 03 ---|
| \#        | splits volumetric object types                                                        |--- 04 ---|
| :         | splits object properties, first field is object type id followed by properties        |--- 05 ---|
| =         | splits each scaling constant (not always present)                                     |--- 06 ---|

# Volumetric Objects

| ID | Type |
|:---|------|
| 0  | barrel |
| 1  | capsule |
| 2  | cone |
| 3  | conical_frustum |
| 4  | cube |
| 5  | cylinder |
| 6  | ellipsoid |
| 7  | heptagonal_prism |
| 8  | heptagonal_pyramid |
| 9  | hexagonal_prism |
| 10 | hexagonal_pyramid |
| 11 | octagonal_prism |
| 12 | octagonal_pyramid |
| 13 | pentagonal_prism |
| 14 | pentagonal_pyramid |
| 15 | rectangular_pyramid |
| 16 | pyramid_frustum |
| 17 | rectangular_tank |
| 18 | sphere |
| 19 | spherical_cap |
| 20 | stadium_frustum |
| 21 | surplus |
| 22 | trapezoidal_prism |
| 23 | triangular_prism |
| 24 | triangular_pyramid |

# Metric Used

The numeric metric used in the file data format is always the millimeter. The application is responsible for converting between the distinct types of cubic metrics.
