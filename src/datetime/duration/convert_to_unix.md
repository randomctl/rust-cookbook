## Convert `SystemTime` to Unix timestamp

[![std-badge]][std] [![cat-time-badge]][cat-time]

```rust,edition2021
use std::time::{SystemTime, Duration, SystemTimeError};

fn main() -> Result<(), SystemTimeError> {
    let now = SystemTime::now();
    let now_unix = now.duration_since(SystemTime::UNIX_EPOCH)?;
    let now_from_unix = SystemTime::UNIX_EPOCH + now_unix;

    println!("Unix timestamp: {:?}", now_unix);
    println!("Back to SystemTime: {:?}", now_from_unix);

    Ok(())
}
```
