# Nigeria Administrative Coordinates

A structured geospatial dataset containing geographic coordinates for Nigeria's administrative divisions, organised across states, Local Government Areas (LGAs) and wards.

## Overview

The **Nigeria Administrative Coordinates** project is a structured geographic reference dataset designed to make administrative location information in Nigeria more accessible to GIS professionals, software developers, researchers and organisations working with geographic information.

The dataset organises Nigeria's administrative divisions into a hierarchical JSON structure, with individual ward records containing their names and corresponding geographic coordinates (latitude and longitude).

It is intended to support the development of location-based applications, interactive mapping platforms, GIS workflows, spatial data analysis and other geospatial solutions that require structured administrative location information.

## Geographic Coverage

The dataset covers Nigeria's 36 states and the Federal Capital Territory (FCT), with the following administrative breakdown:

| Administrative Level | Coverage |
|---|---:|
| States and FCT | 37 |
| Local Government Areas (LGAs) | 774 |
| Wards | 8,809 |

Each ward record contains geographic coordinates expressed in decimal degrees.

## Data Structure

The dataset follows a hierarchical structure:

- **State:** The name of the state or Federal Capital Territory.
- **LGA:** The Local Government Area belonging to a state.
- **Ward:** The ward belonging to an LGA, including its geographic coordinates.

### JSON Structure

```json
[
  {
    "state": "Abia",
    "lgas": [
      {
        "name": "Aba North",
        "wards": [
          {
            "name": "Ariaria Market",
            "latitude": 5.114318609,
            "longitude": 7.343425561
          },
          {
            "name": "Eziama",
            "latitude": 5.123176577,
            "longitude": 7.367187473
          }
        ]
      }
    ]
  }
]
```

## Coordinate Reference

Ward locations are represented using geographic coordinates:

- **Latitude:** Geographic position north or south of the Equator.
- **Longitude:** Geographic position east or west of the Prime Meridian.
- **Coordinate format:** Decimal degrees.

The dataset provides coordinate-based ward locations. It does not contain polygon geometries defining the actual boundaries or spatial extents of wards, LGAs or states.

## Potential Applications

The dataset can serve as a geographic reference for a variety of geospatial and software development applications, including:

### 1. GIS and Spatial Analysis
- Administrative location identification and spatial referencing.
- Mapping and visualisation of Nigerian administrative locations.
- Geographic distribution and location-based analysis.
- Integration with GIS software and spatial data processing workflows.

### 2. Web and Mobile Mapping Applications
- Interactive maps displaying Nigerian states, LGAs and wards.
- Administrative area selection and location lookup.
- Ward-level location identification in mobile applications.
- Integration with mapping services and geospatial APIs.

### 3. Location-Based Services
- Administrative location search and filtering.
- Geographic classification of addresses and locations.
- Location-based service delivery and data organisation.
- Applications requiring ward-level geographic references.

### 4. Geospatial Software Development
- Integration into GIS platforms and custom mapping applications.
- Development of administrative location search tools.
- Geographic data processing and transformation.
- Use as a reference dataset in location-aware software systems.

## Usage

The dataset is provided in JSON format and can be integrated into applications built with JavaScript, Python, PHP and other programming languages that support JSON parsing.

### JavaScript Example

```javascript
fetch('./data/nigeria-administrative-coordinates.json')
  .then(response => response.json())
  .then(data => {
    data.forEach(state => {
      console.log('State:', state.state);

      state.lgas.forEach(lga => {
        console.log('LGA:', lga.name);

        lga.wards.forEach(ward => {
          console.log(
            ward.name,
            ward.latitude,
            ward.longitude
          );
        });
      });
    });
  });
```

### Python Example

```python
import json

with open(
    'data/nigeria-administrative-coordinates.json',
    'r',
    encoding='utf-8'
) as file:
    data = json.load(file)

for state in data:
    print('State:', state['state'])

    for lga in state['lgas']:
        print('LGA:', lga['name'])

        for ward in lga['wards']:
            print(
                ward['name'],
                ward['latitude'],
                ward['longitude']
            )
```

## Data Limitations and Accuracy

This dataset provides ward-level geographic coordinate information in a structured administrative hierarchy.

The coordinates should be treated as reference locations rather than verified legal boundary definitions or surveyed control coordinates.

The dataset does not currently provide polygon geometries, official boundary delineations or documented accuracy specifications.

Users intending to apply the data to surveying, cadastral mapping, electoral boundary determination, statutory planning or other precision-dependent applications should independently verify the coordinates against authoritative sources.

## Data Sources and Attribution

The geographic coordinates and location references in this dataset were compiled through the interpretation and cross-referencing of multiple geographic information sources, including:

- **Online Maps:** Geographic location references and coordinate observations obtained from digital mapping platforms.

- **Registered Land Parcels:** Geographic information associated with registered land parcels within the respective areas, used as additional spatial references.

- **Satellite Imagery:** Satellite imagery used to examine geographic features, identify locations and support coordinate referencing.

These sources were used collectively to organise and develop the ward-level geographic reference dataset.

## Contributions

Contributions are welcome from GIS professionals, geospatial developers, researchers and other interested contributors.

You can contribute by:

- Identifying coordinate inaccuracies or inconsistencies.
- Improving dataset completeness.
- Suggesting structural improvements.
- Providing documentation and usage examples.
- Developing integrations with GIS and mapping applications.

To contribute, fork the repository, make your changes and submit a pull request describing your contribution.

## Project Information

**Project:** Nigeria Administrative Coordinates  
**Format:** JSON  
**Domain:** Geospatial Data / GIS  
**Geographic Coverage:** Nigeria  
**Administrative Levels:** States, LGAs and Wards

---

Developed and maintained by **Akachukwu Okoro**.

If you find this dataset useful, consider starring the repository and contributing to its improvement.
