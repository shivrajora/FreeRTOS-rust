# FreeRTOS Rust

Wrapper library to use FreeRTOS API in Rust.

> **Note:** This is a fork of [freertos-rust](https://github.com/shivrajora/FreeRTOS-rust) updated for use with [Picodroid](https://github.com/shivrajora/picodroid-rs). Published on crates.io as `freertos-rust-pd`.

To build an embedded application with FreeRTOS please refer
to [freertos-rust home](https://github.com/shivrajora/FreeRTOS-rust).

## Additions over upstream

- **Cortex-M0/M0+ support** — integrates `portable-atomic` for software atomics on targets without hardware atomics (e.g. RP2040)
- **`xTaskAbortDelay`** — abort a delayed task to wake it early

## Usage

The crate is published on [crates.io](https://crates.io/crates/freertos-rust-pd)

    [dependencies]
    freertos-rust-pd = "*"
