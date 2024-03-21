# gedcom
starting point for all things gedcom

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

