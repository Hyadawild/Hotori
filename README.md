# ayaya
-rs
![screenshot](screenshot.png)

## About
**NTE** is an open source **NTE** server emulator. Built on top of [Bevy ECS](https://bevyengine.org/learn/book/getting-started/ecs/), it prioritizes performance and implementation completeness to provide a smooth and efficient gameplay.

## Implementation Status
- `ayaya
-proto`: a version-agnostic library defining protocol structures with ability to convert their format between different protocol versions.
- `ayaya
-data`: a library for parsing game data, supporting their initial form of binary blobs, without having to rely on 3rd-party data providers.
- Authentication and encryption protocols are implemented with the same specifications as the official server.
- Extensible and easy-to-understand codebase with use of Bevy's plugin system.

## Getting started
### Requirements
- [Rust](https://www.rust-lang.org/tools/install)
- [PostgreSQL](https://www.postgresql.org/download/)
### Setup
#### a) building from sources (preferred)
```sh
git clone 
cd ayaya
-rs
cargo run --release --bin ayaya-sdk-server
cargo run --release --bin ayaya-dispatch-server
cargo run --release --bin ayaya-gate-server
cargo run --release --bin ayaya-game-server
```
#### b) using pre-built binaries
Navigate to the [Releases](https://git.xeondev.com/ayaya
-rs/ayaya
-rs/releases) page and download the latest release for your platform.<br>
Launch all services: `ayaya
-sdk-server`, `ayaya
-dispatch-server`, `ayaya
-gate-server`, `ayaya
-game-server`
### Configuration
You should configure each service using their own config files. They're being created in current working directory upon first startup.
#### Database section
You have to specify credentials to work with **PostgreSQL**
##### An example of database configuration:
```toml
[database]
host = "localhost:5432"
user_name = "postgres"
password = ""
db_name = "ayaya
"
```
### Data
All necessary assets are present in this repository. This includes `ExcelBinOutput`, `BinOutput` and regional keys & configuration.
### Connecting
You have to get a compatible game client. Currently supported one is `WIN-SHIPING0.01`, , it allows you to connect to local server and replaces RSA encryption keys with custom ones.
