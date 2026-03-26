# FreeRTOS Rust

Wrapper library to use FreeRTOS API in Rust.

> **Note:** This is a fork of [freertos-rust](https://github.com/lobaro/FreeRTOS-rust) updated for use with [Picodroid](https://github.com/shivrajora/picodroid-rs). Published on crates.io as `freertos-rust-pd`.

To build an embedded application with FreeRTOS please refer
to [freertos-rust home](https://github.com/lobaro/FreeRTOS-rust).

## Additions over upstream

- **Cortex-M0/M0+ support** — integrates `portable-atomic` for software atomics on targets without hardware atomics (e.g. RP2040)
- **Event groups** — full support for FreeRTOS event group synchronization primitives
- **Semaphore ISR methods** — semaphore give/take from interrupt service routines
- **`xTaskAbortDelay`** — abort a delayed task to wake it early
- **`SuspendScheduler` type** — RAII guard for safely suspending and resuming the scheduler
- **Raw handle APIs** — convert to/from raw FreeRTOS handles for Mutex, Queue, Semaphore, Task, and Timer to ease interop with C code
- **Broader type bounds** — Queue and Mutex now accept `Send` types instead of requiring `Copy`
- **`delete_task` feature flag** — opt out of `vTaskDelete()` for targets that disable it
- **Periodic timer fix** — fixed bug where periodic timers fired only once
- **ISR yield fix** — `InterruptContext` drop now correctly calls `portYIELD_FROM_ISR()` instead of `portYIELD()`

## Usage

The crate is published on [crates.io](https://crates.io/crates/freertos-rust-pd)

    [dependencies]
    freertos-rust-pd = "*"
