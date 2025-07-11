# modbus-core

A no-std Rust modbus library.

[![Crates.io version](https://img.shields.io/crates/v/modbus-core.svg)](https://crates.io/crates/modbus-core)
[![Docs](https://docs.rs/modbus-core/badge.svg)](https://docs.rs/modbus-core/)
[![Security audit](https://github.com/slowtec/modbus-core/actions/workflows/security_audit.yaml/badge.svg)](https://github.com/slowtec/modbus-core/actions/workflows/security_audit.yaml)
[![Continuous integration](https://github.com/slowtec/modbus-core/actions/workflows/continuous_integration.yaml/badge.svg)](https://github.com/slowtec/modbus-core/actions/workflows/continuous_integration.yaml)

## Installation

Add this to your `Cargo.toml`:

```toml
[dependencies]
modbus-core = "*"
```

If you like to use Modbus TCP only:

```toml
[dependencies]
modbus-core = { version = "*", default-features = false, features = ["tcp"] }
```

If you like to use Modbus RTU only:

```toml
[dependencies]
modbus-core = { version = "*", default-features = false, features = ["rtu"] }
```

## Protocol-Specification

- [MODBUS Application Protocol Specification v1.1b3 (PDF)](http://modbus.org/docs/Modbus_Application_Protocol_V1_1b3.pdf)
- [MODBUS over serial line specification and implementation guide v1.02 (PDF)](http://modbus.org/docs/Modbus_over_serial_line_V1_02.pdf)
- [MODBUS Messaging on TCP/IP Implementation Guide v1.0b (PDF)](http://modbus.org/docs/Modbus_Messaging_Implementation_Guide_V1_0b.pdf)


## Logging / defmt

This crate has the option to do logging through the [log crate](https://docs.rs/log/latest/log/), 
or using [defmt](https://defmt.ferrous-systems.com/) for embedded environments.

The default behavior is to include and use log, but you can use defmt instead, using the following:

```toml
[dependencies]
modbus-core = { version = "*", default-features = false, features = ["rtu", "defmt"] }
```

Defmt will only be included when running on a system with no OS, even when explicitly included.
Including both defmt and log will default to defmt if there is no OS, as defmt must be explicitly included.
Disabling the default feature (log), and not using the defmt feature will not compile.

## License

Copyright 2018-2025 [slowtec GmbH](https://www.slowtec.de)

MIT/Apache-2.0
