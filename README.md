# Ueberzug-rs
[Ueberzug-rs](https://github.com/Adit-Chauhan/Ueberzug-rs) This project provides simple bindings to that [ueberzug](https://github.com/seebye/ueberzug) to draw images in the terminal.

This code was inspired from the [termusic](https://github.com/tramhao/termusic) to convert their specilized approach to a more general one.

**Note:** This project needs ueberzug to be installed and be in the system path.

## Examples
this example will draw image for 2 seconds, erase the image and wait 1 second before exiting the program.
```rust
use std::thread::sleep;
use std::time::Duration;
use ueberzug::{UeConf,Scalers};

let a = ueberzug::Ueberzug::new();
// Draw image
// See UeConf for more details
a.draw(&UeConf {
    identifier: "crab",
    path: "ferris.png",
    x: 10,
    y: 2,
    width: Some(10),
    height: Some(10),
    scaler: Some(Scalers::FitContain),
    ..Default::default()
});
sleep(Duration::from_secs(2));
// Only identifier needed to clear image
a.clear("crab");
sleep(Duration::from_secs(1));
```
