# Firmware-Flasher provenance & checksums

This folder contains the pre-compiled firmware images and the third-party
flashing tools used to write them. This repository
(`LxveAce/BlueJammer-V2`) is a fork of the upstream project
[`EmenstaNougat/BlueJammer-V2`](https://github.com/EmenstaNougat/BlueJammer-V2)
by @emensta, which is the origin of all firmware and tooling here.

The SHA-256 values below describe every file **exactly as committed to this
repository**. They let you confirm a clone or download has not been altered in
transit or by a third party before you flash it. They are a provenance record
only - none of these binaries has been modified, replaced, scanned, or executed
in producing this manifest.

## How to verify

**Windows (PowerShell):**

```powershell
Get-FileHash .\esptool.exe -Algorithm SHA256
```

**Windows (cmd):**

```bat
certutil -hashfile esptool.exe SHA256
```

**Linux / macOS / Git Bash (verify everything at once):**

```sh
cd Firmware-Flasher
sha256sum -c SHA256SUMS.txt
```

A machine-readable copy of every hash is in [`SHA256SUMS.txt`](SHA256SUMS.txt).

## Project firmware - ESP32 (compiled BlueJammer-V2)

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `BlueJammer-V2.ino.bin` | 315440 | `d8aa2ef364135709b18e2872547712edd43e44d50e4bfc049b692faa442d5c83` |
| `BlueJammer-V2.ino.bootloader.bin` | 18992 | `3d97b71a61331ebaddef2a74e090c35299650f395f1387f85130010e84e46563` |
| `BlueJammer-V2.ino.partitions.bin` | 3072 | `148b959cbff1c38aa8e1d5c0ba9d612c54997b945e56a63f41223eef650653a1` |

## Project firmware - Ai-Thinker BW16 / RTL8720DN (compiled)

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `km0_boot_all.bin` | 4500 | `453c880307fc389009aa8a39c63da3d715b207ad797206c896cc691426daaa64` |
| `km4_boot_all.bin` | 4456 | `05fbf808d43113eaf7c11b75091c986b817135f0c52eb9fa94bb9fe9f34b062c` |
| `km0_km4_image2.bin` | 782336 | `c1e76f87be9afd3d98f923eda5ab323669dde5d190609a8aa2037d7a1ca185b2` |

## Third-party flashing tools (Windows executables)

These are bundled utilities, not authored as part of this project. `esptool`
is the Espressif ESP32 flasher; the Ameba/`amebatool`/`ImageTool`/`uartfwburn`
tools and the `Auto_Flash_Pro2` runner are Realtek AmebaD (BW16) flashing
utilities.

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `esptool.exe` | 6614264 | `f8ea417fc1449e6ce2fd782dba4469abf00037ef0b94545bf2192a9daef1bdc1` |
| `amebatool.exe` | 2420472 | `0dc86f3c3dd32075c088810fd81ac475fdc4e0fc425f4bf1c2619ede25d8859d` |
| `ImageTool.exe` | 288768 | `a4b5c879e87a297cadd8c7dbd2e6981e09b59562325b27445fa5f62aa8444077` |
| `uartfwburn.exe` | 135568 | `5612033b2d3e69c8a666f76cbbe805a8f42691f33efcb0e90833f247678b8bb0` |
| `Auto_Flash_Pro2_V3.3_win.exe` | 1078688 | `72ef8f0455f6c4c929bc39ced2f5a4532c351e6637bfb2007147fbdc8e8d7cd7` |

## Third-party flash loaders / stubs (binary)

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `flash_loader_nor.bin` | 81920 | `5fdcf7938a3baeb4b155c23aaddee00ba579bec2f9dbc582c4b81d909ab5451d` |
| `imgtool_flashloader_amebad.bin` | 4688 | `9307121385cb390dfd2da64da2c6c515f17b5a9556b3d04021487c9b9f220b55` |

## Flasher script & config (text)

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `BlueJammer-V2-Flasher_RUN_THIS.bat` | 1040 | `e69c550c10d72594fed6c1b4acfbbbfb6a2d707f2575d243b9c9b9c3de38ae78` |
| `Download.ini` | 1218 | `a5343e0edc4d03a696e255c2cf77299d7533b345972b95825ae89b882379883e` |
| `Encrypt.ini` | 148 | `4c602bc296b20c2506d090ffebad7f715455f127fa61efcb3a18f19b77b26be5` |

> The bundled flashing tools listed above are Windows executables. Flashing from
> Linux or macOS requires the equivalent upstream tools and is not covered by
> the included `.bat` runner.
