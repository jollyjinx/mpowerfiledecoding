# Decoding BMW laptimer application mpower files

I came accross the BMW laptimer software which can export it's data, but I found no quick way to decode them. 

Information I gathered so far:
- mpower files are in fact zip archives. Rename them to .zip and you can open the archive.
- the archive itself consists of many .far files
- far files are binary encoded in the following form:

    speed.far:          8bytes float speed          , 8bytes float time
    acceleration.far:   8bytes float acceleration   , 8bytes float time

