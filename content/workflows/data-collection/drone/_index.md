---
title: Drone data collection workflow
summary: "Guidelines for drone data collection"
type: book

show_date: false

---

## Overview

The OFO drone data collection workflow is designed to yield data for detecting, mapping, and characterizing individual trees, including species classification. It was developed for relatively low-cost drones with standard RGB (red-green-blue visual light) cameras, following extensive testing, including [published](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210X.13860) and unpublished work, primarily in dense, multi-layered coniferous forests in the western United States.

We recommend flying two missions over each study site:
- High-elevation flight with a nadir (downward-facing) camera, for developing 3D structure models, canopy height models, point clouds, and orthomosaics
- Lower-elevation flight with an oblique (angled) camera, for species classification and (in some specific contexts) better modeling and detection of understory trees

## Aircraft & flight controller

Our protocol was developed for quadcopter drones with a 20 MP RGB camera with an aspect ratio of 4:3 and a diagonal field of view of approximately 84 degrees. Drones matching these specifications that have worked well for us include the DJI Phantom 4 Pro, DJI Phantom 4 RTK, and the DJI Mavic 3 Enterprise/Multispectral (using its RGB camera). Drones with higher resolutions (all else equal) will yield equivalent or better results. Drones with lower resolutions or other differences may or may not require adjustments to the workflow. If you have tested drones with other specifications, share your experience!

We have had success using the DJI flight planner app on the standard DJI Mavic 3E/3M and Phantom 4 RTK controllers, as well as the Map Pilot app run from a tablet or installed onto the Mavic 3E controller. The Drone Deploy app appears to have similar functionality. If you wish to fly a clearly defined flight area, it is important that the flight controller allow for import of KML polygons for defining the mission footprint.

## Mission parameters

In areas with significant topography, use a "terrain awareness" mode that maintains a consistent altitude above ground level. The flight speed and mission duration can be set to the maximum values that accommodate the other mission parameters and allow for safe operation. Ensure that the selected camera exposure parameters allow for minimal motion blur (the movement the subject across multpile pixels during the time the shutter is open). Additionally, we have found that some drone models' auto exposure modes (particularly with the Mavic 3E/3M) can result in underexposed images, so we recommend inspecting a preliminary set of images and adjusting exposure compensation (EV) as needed. If autofocus does not appear to be focusing properly, it should work to use manual focus set to infinity.

### High-altitude nadir mission

- Altitude: 120 m AGL
  - 100 m to 140 m is likely acceptable, though note that US FAA regulations prohibit flight beyond 120 m above ground level (or the tops of structures) without a waiver
- Gimbal pitch: +0 degrees from straight down (-90 degrees from horizontal)
  - A gimbal pitch up to +10 degrees from straight down is likely acceptable
- Mission type: Normal (serpentine, as opposed to grid)
- Overlap: 90% front and 90% side

### Low-altitude oblique mission

- Altitude: 80 m AGL
  - 60 m to 90 m is likely acceptable, though be sure your altitude will clear all obstacles with sufficient safety buffer in the event of imprecise terrain following
- Gimbal pitch: +35 degrees from straight down (-55 degrees from horizontal)
  - A gimbal pitch between +25 and +40 degrees from straight down is likely acceptable
- Mission type: Grid (two perpendicular serpentine paths) or DJI "Smart Oblique"
- Overlap:
  - For grid missions: 80% front and 70% side (though higher will improve results)
  - For Smart Oblique missions: 80% front and 60% side (though higher will improve results)

## Metadata records

In addition to keeping a pilot's flight log in the field to track mission details including metadata, relevant  metadata should be recorded digitally in a standardized format. We recommend creating a copy of the [<i class="fa-solid fa-table"></i> OFO metadata template](https://docs.google.com/spreadsheets/d/16Q7no7NfrmWJ3uSNG2dzTIMBMyWBmbM391hOk6mgy84/edit?usp=sharing). This template includes fields for the date, drone model, flight app, mission type, flight altitude, gimbal pitch, overlap, and other relevant details.

## Flight preparation & execution checklist

Checklists are important for ensuring that important steps are not overlooked. The checklist below may be used as a starting point, but it should be tailored to the specific equipment and other nuances of a given project, in particular to  account for site-specific safety considerations.

### Well before trip

* If required by your institution, file flight requests 
* Identify candidate piloting locations  
* Complete site-specific field safety plan for field location

### Before trip

* Charge batteries, controller, and tablet (if using)  
* Ensure SD cards are cleared (and previous data has been uploaded) and all accounted for  
* Make sure controller is set up properly  
  * KMLs for flight footprints loaded (e.g. by loading to SD card and inserting into controller)  
* Plan and save missions in controller (including loading/downloading elevation data for terrain following if required)  
  * Prepare missions with the parameters defined above  
  * Alternatively, plan one or more dummy missions that cover all potential flight areas so that elevation data and basemap imagery are saved (if this is a function of your flight planner), then plan actual missions later on site  
* Check weather (NOAA NWS)  
* Check NOTAMs

### Before flight mission

* Set up RTK base station (if using)
  * Set up tripod in a clearing with a clear sky view and mount base station
  * Power on base station and allow it to obtain its position coordinates
  * Confirm appropriate configuration for connection to drone
  * Record base station position coordinates
  * Optionally, install permanent marker at base station location
  * If reusing a previously marked base station location, set the base coordinates to those previously recorded
* Remove drone gimbal stabilizer; mount propellers  
* Insert empty SD card, noting card number on log  
* If using tablet: remove covers from tablet, mount tablet on controller, mount sun shield, connect USB  
* Inspect aircraft, batteries, and propellers for damage  
* Dust off camera lens
* If using RTK, confirm drone connection to RTK base and drone position fix    
* Load saved flight mission and check parameters

### First mission flight

* Clear the takeoff area
* Tap “Start” to begin mission

### Remaining mission flights

* Swap for new battery; turn on drone  
* Put old battery in the shade to cool
* If using RTK, confirm drone connection to RTK base and drone position fix
* Tap to upload new flight waypoints if prompted  
* Clear the takeoff area  
* Tap “Start” to begin mission

### During flight

* Takeoff: Look up to make sure aircraft remains in canopy opening  
* Bring up camera view  
* Ensure camera exposure settings and gimbal angle are correct  
  * If necessary, re-adjust camera exposure settings 
* Verify the image count is rising  
* Return home by 20% battery or before. Consider manually piloting the drone home.

### After mission

* Record SD card number and area flown  
* Remove and store SD card  
  * If you will use the same SD card for more missions, record any data you will need (e.g., flight date time range) to sort photos into different missions
* Power off and store all equipment
* At camp/housing:  
  * Charge batteries, controller, tablet
  * Copy imagery from SD cards to external SSD and sort into folders by mission
  * Spot-check the imagery collected on a computer or tablet to make sure images were recorded, exposure was good, focus was good, etc. Check at least a few images per folder.  
  * Map the image points to ensure complete spatial coverage using the “import geotagged photos” tool in QGIS.

### After trip

* Enter mission metadata into the mission metadata spreadsheet  
  * There should be one log row for each flight mission  
  * The mission name recorded in the spreadsheet should be the same as the name given to the folder of imagery  
* Transfer imagery to local data storage and upload to cloud storage  
  * Each mission should be stored in a separate folder. The name of the folder should be the same as the “mission name” in the corresponding imagery log entry (described above)  
    * An example is if you fly polygon A101 at 80 m, mission name should be A101-80 (in both the imagery log and the folder name)  
  * Beneath that folder, the default drone folder structure should be left intact; do not copy all images into a single folder. So for example: A101-80/100MEDIA/DJI1001.jpg  
    * If the mission was split between two SD cards, you need to add an additional folder level specifying the card ID. For example: A101-80/card-01/100MEDIA/DJI1001.jpg  
  * If your records were insufficient for determining which photos were from which flight area, you can probably resolve it by mapping the locations of the images in QGIS using the tool “import geotagged photos.”  
  * Sort out any landscape photos or videos and put them in a folder named {site name}\_landscape. Example: yuba\_landscape. This folder should be in the root drone-imagery folder. This folder will accumulate landscape photos from multiple missions. If there are file name conflicts, it is OK to rename the files (rather than overwriting the existing photos). This applies only to landscape photos. Normal mission photos should never have filename conflicts.  
* Clear SD cards (after making sure that all photos are transferred to local and cloud storage)  
* Allow flight controller to sync mission logs to online logging platforms (if applicable)  
* If required by your institution, file post-flight reports
* Charge batteries, remote, and tablet (if using) for storage (ideally to 50%, but more is OK)
