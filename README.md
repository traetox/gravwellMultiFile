# gravwellMultiFile
one off of multifile to allow for some additional control over the source value

## Installation
go get -u github.com/traetox/gravwellMultiFile
go install github.com/traetox/gravwellMultiFile

## usage
setting -source-override 5 will place the 64bit unsigned value in the upper 64 bits of the source field.

This will allow you to find ingested entries using a subnet and mask


Setting the -source-file-hash flag will cause the ingester to create a CRC64 hash of the ingested file using the ECMA polynomial table.  This will allow you to identify the exact file that the entry came from


### Combined usage
Combining the -source-override and -source-file-hash directives will allow you to group entries with an ID AND tagging entries with the exact file that they came from.


### Examples

#### Ingesting files with an ID of 2 and the input hash of each intput file

```
gravwellMultiFile -i filelist.txt -source-override 2 -source-file-hash -clear-conns 172.17.0.2
```

#### Ingesting files with just an ID

```
gravwellMultiFile -i filelist.txt -source-override 2 -source-file-hash -clear-conns 172.17.0.2
```
