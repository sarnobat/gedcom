# gedcom
Starting point for all things gedcom


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

## Sample runs


* gedcom2csv.awk
* ✔️ gedcom2mwk.go
* ✔️ gedcom2mwk
* gedcom
* gedcom_tree.go
* gedcom2csv.sh
* gedcom_list.groovy
* gedcom_indent.go

### gedcom2mwk
```
/Volumes/git/2023/github/2023/graalvm_aotc_java/8_gedcom_sharp_tools/gedcom2mwk.osx | head** Bhimka Rao Rohidekar (-- Radhabai)
```
```
** Anand Rao Rohidekar
** Venkawwa Rohidekar
** Laxman Rao Rohidekar (-- Renubai) (-- Sitabai)
*** Venkatesh Rohidekar (-- Rangubai Padki)
*** Raghunath Rao Rohidekar (-- Janaki Kodagli)
**** Ramachandra Rao Rohidekar (-- Sitabai Anikhindi)
```
### gedcom2mwk.go
```
go run /Volumes/git/2023/github/2023/repos.git/golang/3_gedcom/gedcom2mwk.go 2>/dev/null | grep '^*' | head
```
```
* Bhimka Rao Rohidekar (d. 1920)
* Anand Rao Rohidekar (d. 1895)
* Venkawwa Rohidekar
* Laxman Rao Rohidekar (b. 1847, d. 1934)
* Venkat Rao Rohidekar (b. 1825)  (-- Tarabai)
** Bhimka Rao Rohidekar (d. 1920)  (-- Radhabai)
** Anand Rao Rohidekar (d. 1895)
** Venkawwa Rohidekar
** Laxman Rao Rohidekar (b. 1847, d. 1934)  (-- Renubai)
*** Venkatesh Rohidekar (b. 1889, d. 1906)  (-- Rangubai Padki)
```
