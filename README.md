# ocolca

### This crate provided various options for combining text.

- Without the ansi escpe sequences.
- With the ansi escpe sequences.
- Along the lines of the first text.
- Iteration on non empty lines.

### Examples

```rust
use :ocolca;

let first_txt = String::from("It's a\nit's raining\nnortherly wind.");
let second_txt = String::from("beautiful day,\nwith a\n\n");
let ocolca = ocolca::new().fill(' ').repeat(0);
let text = "It's a         beautiful day,\nit's raining   with a\nnortherly wind.\n";
let concatenated_txt = ocolca.combine_col(&first_txt, &second_txt).collect::<String>();

assert_eq!(concatenated_txt, text);

println!("{}", concatenated_txt);
//It's a         beautiful day,
//it's raining   with a
//northerly wind.
```

```rust
use ocolca::cat_to_col;

let first_txt = String::from("It's a\nit's raining\nnortherly wind.");
let second_txt = String::from("beautiful day,\nwith a\n\n");
let text = "It's a beautiful day,\nit's raining with a\nnortherly wind. \n";
let concatenated_txt = cat_to_col(&first_txt, &second_txt).collect::<String>();

assert_eq!(concatenated_txt, text);

println!("{}", concatenated_txt);
//It's a beautiful day,
//it's raining with a
//northerly wind.
```

```rust
use ocolca::by_pairs;w

let first_txt = "one horsepower\ntwo horsepower\nthree horsepower\nfour horsepower\n";
let second_txt = "per horse\ntwo horses\n";
let concatenated_txt = by_pairs(first_txt, second_txt).collect::<String>();

 assert_eq!( &concatenated_txt, "one horsepower per horse\ntwo horsepower two horses\n");
 
 println!("{}", concatenated_txt);
 //one horsepower per horse
 //two horsepower two horses
 ```
 
## License
GNU General Public License v3.0 

