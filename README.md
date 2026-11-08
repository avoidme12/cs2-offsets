# 🧩 CS2 Offsets

Reverse-engineered **Counter-Strike 2** offsets and schema dumps, exported in three languages so they can be dropped straight into a C++, Rust or C# project.

[![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)](.)
[![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)](.)
[![C%23](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)](.)
[![CS2](https://img.shields.io/badge/CS2-offsets-8A89C0?style=flat-square)](.)

> Generated with [a2x/cs2-dumper](https://github.com/a2x/cs2-dumper) and refreshed after game updates.

---

## 📦 What's inside

Each game module is exported in four formats:

| File | Format | Purpose |
| --- | --- | --- |
| `<module>.json` | JSON | offsets, classes, enums, schemas — easy to parse from any language |
| `<module>.hpp` | C++ header | `constexpr` offsets + enums, ready to `#include` |
| `<module>.cs` | C# | constants and enums for .NET projects |
| `<module>.rs` | Rust | constants and enums for Rust projects |

Example modules: `client_dll`, `engine2_dll`, `buttons`, `animationsystem_dll`.

### C++

```cpp
#include "client_dll.hpp"

const auto offset = cs2_dumper::offsets::client_dll::dwEntityList;
```

### Rust

```rust
include!("client_dll.rs");

let offset = offsets::client_dll::DW_ENTITY_LIST;
```

### C#

```csharp
using cs2_dumper.offsets;

var offset = client_dll.dwEntityList;
```

---

## ⚠️ Disclaimer

Published for **reverse-engineering research and education** only. Game offsets change with every update, so always re-dump and verify before use. You are responsible for how you use this data.
