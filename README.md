# CFA Samples

Contains small snippets of C-for-all code for my own testing and understanding of the features in the language.

### Sample Descriptions

- `traits`: Implements the sample program from the [docs](https://cforall.uwaterloo.ca/features/#Trait), but across multiple compilation units.
- `incr`: A simple incrementer (the ++ operation) that displays the use of traited coroutines.


## Issues

### **Ongoing**

- In `incr`, trait-based coroutines are producing some compilation problems. To reproduce errors, please open the `incr` directory, then compile the program with
```
$ cfa incr.cfa driver.cfa -o incr
```

### Resolved

- In `traits`, it was discovered that including either of the copy or copy assignment operators in a trait cause nasty problems with resolving the ast at runtime. My current solution was to avoid including these operators in traits, and assume they are implemented for a given type.
