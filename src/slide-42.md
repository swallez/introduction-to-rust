
# The `Error` type

```rust
pub enum Result<T, E> {
    /// Contains the success value
    Ok(T),
    /// Contains the error value
    Err(E),
}
```

Reading a file with proper error handling:

```rust,editable
use std::fs::File;
use std::path::Path;
use std::io::Read;

fn read_file() -> Result<String, std::io::Error> {
    let mut text = String::new();
    let path = Path::new("file.txt");
    
    let mut file = File::open(path)?;
    file.read_to_string(&mut text)?;
    
    return Ok(text);
}

fn main() -> Result<(), std::io::Error>{
    let str = read_file()?;
    println!("Text is {}", str);
    Ok(())
}
```

