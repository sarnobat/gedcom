# gedcom
Starting point for all things gedcom


* gedcom2csv.awk
* gedcom2mwk.go
* gedcom2mwk
* gedcom
* gedcom_tree.go
* gedcom2csv.sh
* gedcom_list.groovy
* gedcom_indent.go

## To tree
I am not sure if gedcom2csv exists.
```
[ged] -- gedcom2csv --> [parent_child.csv] -- csv2path.java --> [paths.txt] -- path2indented.py --> [indented.txt]
```

## To html bullets
```
[ged] -- gedcom2mwk.java --> [parent_child.csv] -- csv2path.java --> [paths.txt] -- path2indented.py --> [indented.txt]
```

### example
```
  ./gedcom.osx edges  | /Volumes/git/github/graalvm_aotc_java/9_csv2path/csv2path.osx | path2indent.osx --absolute
```

## Other
tree2fs is under golang/6_mwk2fs
```
+---------------+  gedcom2mwk   +--------------------------+  tree2fs   +----------------------------------------+  tree   +---------------------+  r/9_dendrogram_family_tree/plot.r   +------------------------------+
| rohidekar.ged | ------------> | rohidekar_tree.auto.mwk  | ---------> | /tmp/Venkatesh Rohidekar (-- Tarabai)" | ------> | rohidekar.auto.json | -----------------------------------> | radialTreefromRohidekar.html |
+---------------+               +--------------------------+            +----------------------------------------+         +---------------------+                                      +------------------------------+
                                  |
                                  | tree2fs
                                  v
                                +--------------------------+
                                | rohidekar_tree.auto.html |
                                +--------------------------+

```


## Misc
* trying to remember all the tools needed is tough. Create a monolith program once you know what your use cases are. Composable glue is best for prototyping.
