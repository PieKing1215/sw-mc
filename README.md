# sw-mc
A WIP library for working with Stormworks microcontrollers

The main feature is full two-way (de)serialization of microcontroller XML files.<br>
You can also use `sw_mc::util::find_microcontroller_folder()` to locate the microcontroller data folder.

### Example
```rust
use sw_mc::Microcontroller;

pub fn main() {
    let fname = "samples/blank.xml";

    // read file
    let src: String = std::fs::read_to_string(fname).unwrap();

    // deserialize
    let mc: Microcontroller = Microcontroller::from_xml_str(&src).unwrap();

    // could modify `mc` here

    // serialize to String
    let out: String = mc.to_xml_string().unwrap();

    // check that output was identical
    if src == out {
        println!("Matches!");
    }
}
```

### This is a WIP, expect breaking changes.
