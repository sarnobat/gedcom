# gedcom
starting point for all things gedcom

I am not sure if gedcom2csv exists.
```
[ged] -- gedcom2csv --> [parent_child.csv] -- csv2path.java --> [paths.txt] -- path2indented.py --> [indented.txt]
```
```
[ged] -- gedcom2mwk.java --> [parent_child.csv] -- csv2path.java --> [paths.txt] -- path2indented.py --> [indented.txt]
```


### example
```
  ./gedcom.osx edges  | /Volumes/git/github/graalvm_aotc_java/9_csv2path/csv2path.osx | path2indent.osx --absolute
```
