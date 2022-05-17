
# Automatic file closing

Ownership and lifetimes will automatically close files.

```rust,editable
use std::fs::File;
use std::path::Path;
use std::io::Read;

fn read_file() -> String {
    let mut text = String::new();
    let path = Path::new("file.txt");
    
    let mut file = File::open(path).unwrap();
    file.read_to_string(&mut text).unwrap();
    
    return text;
}

fn main() {
    let str = read_file();
    println!("Text is {}", str);
}
```

