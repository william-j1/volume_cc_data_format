# Data File String Example

The string begins with the tab name, for non web application purposes, this may be omitted. Next is the delimitor []. Followed is the internal geometric shape, the "cube" followed by the next delimitor type ':'. The delimitor ':' is used to separate geometric properties. In the case of this cube, only two properties need be provided, these include its label and its edge length defined in millimeters.

The initial form is always SHAPE_TYPE:LABEL. The LABEL is a base64 encoding. The properties which follow are numerics exclusively relative to the shape type. For an example, a cube will have less properties than a cylinder and indeed the cylinder lesser properties than a stadium frustum.

The '#' delimitor is used to split shape types. The @ delimitor splits the shapes from the scaling constants. The order of these scales is mapped on a 1-to-1 basis with the geometric shapes. These scaling constants allow subtractive manipulation to represent more complex volumes. This option persists for power users whom require this cutting edge precision.

Each scaling constant is separated by the '=' delimitor. Its data type is that of a floating point and its interval is equal to [-1, 1]. By default, all objects have a scale set to 1.

# File Data Format IO

The clear text file format is described here.

# List of Delimitors

| Delimitor | Description                                                                           | Priority |
|:---------:|---------------------------------------------------------------------------------------|:--------:|
| ~         | (reserved) splits multiple tabs iff export is a workspace export (not always present) | 5        |
| []        | splits name of tab (title), dataset (middle or right) and comments (optional right)   | 4        |
| @         | splits scales (right) from dataset (left), the order is equal to the object ordering  | 3        |
| \#        | splits volumetric object types                                                        | 2        |
| :         | splits object properties, first field is object type id followed by properties        | 1        |
| =         | splits each scaling constant                                                          | 0        |

# Volumetric Objects

| ID | Type |
|:---|------|
| 1  | barrel |
| 2  | capsule |
| 3  | cone |
| 4  | conical_frustum |
| 5  | cube |
| 6  | cylinder |
| 7  | ellipsoid |
| 8  | heptagonal_prism |
| 9  | heptagonal_pyramid |
| 10 | hexagonal_prism |
| 11 | hexagonal_pyramid |
| 12 | octagonal_prism |
| 13 | octagonal_pyramid |
| 14 | pentagonal_prism |
| 15 | pentagonal_pyramid |
| 16 | rectangular_pyramid |
| 17 | pyramid_frustum |
| 18 | rectangular_tank |
| 19 | sphere |
| 20 | spherical_cap |
| 21 | stadium_frustum |
| 22 | surplus |
| 23 | trapezoidal_prism |
| 24 | triangular_prism |
| 25 | triangular_pyramid |
| 26 | torus |

# Metric Used

The numeric metric used in the file data format is always the millimeter. The application is responsible for converting between the distinct types of cubic metrics.
