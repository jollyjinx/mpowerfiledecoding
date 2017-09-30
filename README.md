# Decoding BMW laptimer application mpower files

I came accross the BMW laptimer software which can export it's data, but I found no quick way to decode them. 

Information I gathered so far:
- mpower files are in fact zip archives. Rename them to .zip and you can open the archive.
- the archive itself consists of many .far files
- far files are binary encoded in the following form:


    acceleration.far:       8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float acceleration ?
                            8bytes float acceleration left-right ?
                            8bytes float acceleration up-down ?

    acceleratorPedal.far:   8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float (0-100)? pedal state

    brakeContact.far:       8bytes version hex
                            entries:
                            8bytes float time
                            8bytes (hex?) brakestate


    speed.far:              8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float speed 
                        
    consumption.far:        8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float consumption
                            This file seems to be empty for my car (i3-BEV)
                        
    currentConsumption.far: 8bytes version hex
                            entries:    
                            This file is empty except for the version for my car (i3-BEV)
                            
    distance.far:           8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float distance in meters
    
    filteredAcceleration.far: 8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float acceleration ?
                            8bytes float acceleration left-right ?
                            8bytes float acceleration up-down ?
                            
    filteredLocation.far:   8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float latitude
                            8bytes float longitude

    gear.far:               8bytes version hex
                            8bytes float time
                            8bytes hex gear number

    location.far:           8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float latitude
                            8bytes float longitude

    locationExtended.far:   8bytes version hex
                            entries:
                            8bytes float time
                            8bytes float height of earth surface    (65492)
                            8bytes float                      (281.25)
                            8bytes float                      (0)
                            8bytes float                      (418)
                            
    metadata.plist          


    rpm.far:                8bytes version hex
                            8bytes float time
                            8bytes float rpm

    speed.far:              8bytes version hex
                            8bytes float time
                            8bytes float speed in ?

    steering.far:           8bytes version hex
                            8bytes float time
                            8bytes float steering angle?

    vehicletype.far:        8bytes hex
                            8bytes float
                            8bytes hex
                            8bytes hex
                            
    waypointStartCrossing.far:8bytes version hex
                          entries:
                          8bytes float time

