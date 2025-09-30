 ## Open terminal and run Tcl starting Command
 ```bash
tclsh  or 3>tclsh
```
## 1. Hello World 
 ```tcl
puts "Hello World!"
```
Output
```tcl
Hello World!
```
---
## 2.Variables
```tcl
set a 5
puts $a
puts "${a}4"
```
Output 
```tcl
5 -># $a
54 -=> ${a}4
```
---

## 3. Arithmetic
```tcl
set b [expr 10 - 8]
puts $b # it will print 2
puts [expr 2 + 2] # it will p[rint 4 but if you use puts "2+2" it will give you 2+2 only nopt the addition !. 
```
Output 
```tcl
2
4
```
Same for other arithmatic computations

## 4. List
```tcl
# In three ways we can set the list
set l1 {1 2 3}
set l2 {4 5 6}
set l3 [list 7 8 9]

puts "list 1 is $l1, list 2 is $l2, list 3 is $l3"
puts [llength $l1] # For length of line

# Ways tol find out index
puts [lindex $l2 1]  or
lindex $l2 1                #  both givs same output
puts [lindex $l3 end]
lindex $l3 end-1 # it will give you the last second value

set l4 "b c a"
sort $l4
```
Output
```tcl
list 1 is 1 2 3, list 2 is 4 5 6, list 3 is 7 8 9
3
5
9
8
b c a
a b c
```
---

## 5. Loops
```tcl
set i 0
while {$i < 10} {
    puts $i
    incr i
}

set l1 {1 2 3 4 5}
foreach item $l1 {
    puts $item
}
```
Output
```
 While loop -> It will print the values from 0 to 9 in a coloumn

```
---

## 6. Conditionals
```tcl
set a 5
if {$a == 5} {
    puts "5"
} elseif {$a == 4} {
    puts "4"
} else {
    puts "none"
}
```
Output
```tcl
5 || if set value is not 5 if it is a value like 3 it will print none
```

## 6. 
```tch
proc plus {a b} {
    return [expr $a + $b]
}

puts [plus 4 5]
```
Output
```tcl
9
```
