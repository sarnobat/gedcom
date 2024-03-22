# gedcom
Starting point for all things gedcom

-   [gedcom](#gedcom)
    -   [To tree](#to-tree)
    -   [To html bullets](#to-html-bullets)
        -   [example](#example)
    -   [Other](#other)
    -   [Misc](#misc)
    -   [Sample runs](#sample-runs)
        -   [gedcom2csv.awk](#gedcom2csvawk)
        -   [gedcom_indent.go](#gedcom_indentgo)
        -   [gedcom.go](#gedcomgo)
        -   [gedcom2mwk.java](#gedcom2mwkjava)
        -   [gedcom2mwk.go](#gedcom2mwkgo)
        -   [gedcom_tree.go](#gedcom_treego)
        -   [More examples](#more-examples)

TODO: create yEd from examples in `/Volumes/git/2023/repos_personal.git/computers.git/mac/bin/2023/gedcom2csv.sh`

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


* ✔️ gedcom2mwk.go
* ✔️ gedcom2mwk (GedcomCli.java)
* ✔️ gedcom (GedcomList.java - previously gedcom_list.groovy)
* ✔️ gedcom_tree.go
* ✔️ gedcom_indent.go
* ✔️ gedcom2csv.awk


### gedcom2csv.awk
```
cat ~/sarnobat.git/2022/genealogy/rohidekar.ged | awk -f /Volumes/git/computers.git/mac/bin/gedcom2csv.awk | tee /tmp/out.txt | grep gedcom_children.auto.csv | tee ~/sarnobat.git/2021/genealogy/gedcom_children.auto.csv
```
```
[gedcom_children.auto.csv] I4,I1::I2
[gedcom_children.auto.csv] I3,I1::I2
[gedcom_children.auto.csv] I5,I1::I2
[gedcom_children.auto.csv] I6,I1::I2
[gedcom_children.auto.csv] I7,I1::I2
[gedcom_children.auto.csv] I8,I1::I2
[gedcom_children.auto.csv] I74,I1::I2
[gedcom_children.auto.csv] I10,I3::I9
[gedcom_children.auto.csv] I11,I3::I9
[gedcom_children.auto.csv] I13,I12::I4
```
### gedcom_indent.go
```
go run /Volumes/git/2023/github/2023/repos.git/golang/3_gedcom/gedcom_indent.go | head
```
```
0 HEAD
	1 GEDC
		2 VERS 5.5.1
		2 FORM LINEAGE-LINKED
	1 CHAR UTF-8
	1 LANG English
	1 SOUR MYHERITAGE
		2 NAME MyHeritage Family Tree Builder
		2 VERS 8.2.0.8522
```

### gedcom.go
```
go run /Volumes/git/2023/github/2023/repos.git/golang/3_gedcom/main.go | head
```

```
File:	/Users/sarnobat/sarnobat.git/gedcom/rohidekar.ged
Name:	Prakash
positional args:  []
*gedcom.DocumentHanumanth Rao Rohidekar (b. 21 Aug 1921, d. 9 Feb 2000)
Sumitra/Geetabai Dani Dani/ (d. 16 Mar 2000)
Vinod Rohidekar (b. Apr 1957)
Vidya Rohidekar (b. 28 Sep 10)
Vilas Rohidekar (b. 2 Feb 1961)
Veena Rohidekar (b. 4 May 1964)
Vijay Rohidekar (b. 2 Feb 1966)
```

### gedcom2mwk.java
```
/Volumes/git/2023/github/2023/graalvm_aotc_java/8_gedcom_sharp_tools/gedcom2mwk.osx | head
```
```
** Bhimka Rao Rohidekar (-- Radhabai)
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

### gedcom_tree.go

```
go run /Volumes/git/2023/github/2023/repos.git/golang/3_gedcom/gedcom_tree.go | head
```
```
File:	/Users/sarnobat/sarnobat.git/gedcom/rohidekar.ged
Name:	Prakash
positional args:  []
*gedcom.Document(d2dbf014-f1ec-464e-b4dc-3da7300cb799)
*gedcom.StringSet
{{{0 0} {[] {} 0xc00036b390} map[] 0}}
[d2dbf014-f1ec-464e-b4dc-3da7300cb799]
(d2dbf014-f1ec-464e-b4dc-3da7300cb799)
null
```

### More examples

See `/Volumes/git/2023/repos_personal.git/computers.git/mac/bin/2023/gedcom2csv.sh`