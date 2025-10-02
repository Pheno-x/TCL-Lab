## Associative Array
```tch
set courses(DVD) 83612
set courses(VLSI) 83313
```

### Access individual elements
```tcl
puts $courses(DVD)     ;# 83612
puts $courses(VLSI)    ;# 83313
```
Output
```tcl
83612
83313
```

### Array info
```tcl
puts "Size: [array size courses]"
puts "Keys: [array names courses]"
puts "All:  [array get courses]"
```
Output 
```tcl
Size: 2
Keys: DVD VLSI
All:  DVD 83612 VLSI 83313
```

### Iterate using keys
```tch
foreach coursename [array names courses] {
    puts "$coursename → $courses($coursename)"
}
```
Output 
```tcl
DVD → 83612
VLSI → 83313
```

### Iterate using key-value pairs
```tcl
# Iterate using key-value pairs
foreach {coursename coursenum} [array get courses] {
    puts "$coursename : $coursenum"
}
```
Output
```tcl
DVD : 83612
VLSI : 83313
```

---
## Format Strings
```tcl
puts [format "%f" 43.5]
puts [format "%e" 43.5]

set courses(DVD) 83612
puts [format "%d\t%s" 5 $courses(DVD)]
```
Output 
```tcl
43.500000
4.350000e+01

5       83612
```

---
## File

### Write and Append

``` tcl
# Write to file
set fh [open "myfile.txt" w]
puts $fh "This is my file :)"
close $fh

# Append to file
set fh [open "myfile.txt" a]
puts $fh "line1"
puts $fh "line2"
close $fh
```
Output 
```tcl
#At this point, myfile.txt contains:

This is my file :)
line1
line2
```
### Read
```tcl
# Read entire file
set fh [open "myfile.txt" r]
set data [read $fh]
close $fh
puts "File content:\n$data"


# Read line by line
set fh [open "myfile.txt" r]
while {[gets $fh line] >= 0} {
    puts "Read line: $line"
}
close $fh

```
Output
```tcl
File content:
This is my file :)
line1
line2


Read line: This is my file :)
Read line: line1
Read line: line2
```
