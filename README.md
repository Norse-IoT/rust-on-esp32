# rust-on-esp32
Steps to run Rust on ESP32, for use in the [Norse IoT club](https://norseiot.club/).

Thanks to the [esp-rust](https://github.com/esp-rs) community for making this an easy process.

**These instructions are mirrored on [the wiki page](https://wiki.norseiot.club/projects/rust-on-esp32/).**

----------------

## Installation Instructions

The following instructions were taken from <https://github.com/esp-rs/rust-build#rust-build>.

## Using Rust for ESP32

Step 0: install Rust & Cargo from RustUp
- Go to <https://rustup.rs/>

Step 1:  [Install espup](<https://github.com/esp-rs/rust-build#espup-installation>)
```bash
cargo install espup
espup install # To install Espressif Rust ecosystem
# [Unix]: Source the following file in every terminal before building a project
. $HOME/export-esp.sh
```
Step 2: [RISC-V Installation](<https://github.com/esp-rs/rust-build#risc-v-installation>)

```bash
rustup target add riscv32imc-unknown-none-elf
```
Step 3: [The Cargo First Approach](<https://github.com/esp-rs/rust-build#cargo-first-approach>)
```bash
cargo install cargo-generate
```
```bash
# STD Project
cargo generate esp-rs/esp-idf-template cargo
# NO-STD (Bare-metal) Project
cargo generate esp-rs/esp-template
```
```bash
cargo espflash flash <SERIAL>
# for me, this was cargo espflash flash --port /dev/ttyUSB0 
```

# Internal Blink project

The standard sanity check after creating a new project is to create a project that blinks the internal led.

See [main.rs](/src/main.rs) for the sample code.

