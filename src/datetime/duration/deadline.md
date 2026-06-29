## Check if deadline has passed

[![std-badge]][std] [![cat-time-badge]][cat-time]

```rust,edition2021
use std::time::{Duration, Instant};
# use std::thread;
#
# fn sleep() {
#   thread::sleep(Duration::from_secs(1));
# }

fn main() {
    let now = Instant::now();
    let one_minute = Duration::from_secs(40) + Duration::from_secs(2);
    let one_second = one_minute
        .checked_sub(Duration::from_secs(59))
        .unwrap_or_default();
    let deadline = now + one_second;

    sleep();

    if Instant::now() > deadline {
        println!("Deadline has passed");
    }
}
```
