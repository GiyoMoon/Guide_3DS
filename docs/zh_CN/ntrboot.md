# ntrboot

::: danger

NDS Card has [suspended outgoing packages to the United States](https://nds-card.com/NewsShow.asp?NewsID=1344). All product links listed below may not ship to the United States. For further support (in English), join [Nintendo Homebrew on Discord](https://discord.gg/MWxPgEp).

:::

::: tip

如果你的烧录卡里预先已经安装了 ntrboot（或者你已经将 ntrboot 漏洞写入了烧录卡），那么你可以直接转至[安装 boot9strap（通过 ntrboot）](installing-boot9strap-\(ntrboot\))来进行破解。

:::

## Required Reading

若想使用 ntrboot 漏洞来安装 boot9strap，那么你需要一张兼容的 NDS / DSi 烧录卡来将 ntrboot 写入烧录卡。 请注意，有一些烧录卡已经预先写入了 ntrboot。

3DS 在任何的系统版本下都可以使用 ntrboot 漏洞，不过在将 ntrboot 写入烧录卡之前不一定可以正常使用烧录卡。 This means that, depending on the versions and consoles supported by your flashcart, only certain methods may be available to you.

请注意带有 “Time Bomb” 的烧录卡在检测到主机的系统时间超过了烧录卡固件中设置的某一日期后，将无法正常运行并启动 `.nds` 文件。 绕过这一限制的方法之一是把系统时间调到较早日期。

| Flashcart Name                                                                                                              |          Current Price |                       "Time Bomb"?                       |                                 3DS Versions?                                 |                           DSi Versions?                           | Other Notes                                                                                                                                                                                                                                                                                                |
| --------------------------------------------------------------------------------------------------------------------------- | ---------------------: | :------------------------------------------------------: | :---------------------------------------------------------------------------: | :---------------------------------------------------------------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Ace3DS X**](https://www.nds-card.com/ProShow.asp?ProID=575)                                                              | $17.99 |                            No                            |                                      ALL                                      |                                ALL                                | **Comes pre-flashed with ntrboot** (external switch to switch between ntrboot ("3DS") and NDS modes); do not manually flash with ntrboot. This cart needs an SD card inserted to function for both ntrboot and regular NDS firmware. |
| [**R4i-SDHC B9S** (r4i-sdhc.com)](http://www.nds-card.com/ProShow.asp?ProID=574)         | $16.99 |                     September 3, 2024                    |                                      ALL                                      |                                ALL                                | **Comes pre-flashed with ntrboot**; can be flashed back to an NDS flashcart.                                                                                                                                                                                                               |
| [**DSTT** (ndstt.com)](http://www.nds-card.com/ProShow.asp?ProID=157)                    | $11.99 |                            No                            |                                      None                                     |                                None                               | Only models with [certain flash chips](https://gist.github.com/aspargas2/fa2a70aed3a7fe33f1f10bc264d9fab6) are compatible with ntrboot.                                                                                                                                                    |
| [**R4i-SDHC 3DS RTS** (r4i-sdhc.com)](http://www.nds-card.com/ProShow.asp?ProID=146)     | $15.99 | 1.85b: September 3, 2024 |                                      ALL                                      |                                ALL                                |                                                                                                                                                                                                                                                                                                            |
| [**R4iSDHC GOLD Pro 20XX** (r4isdhc.com)](http://www.nds-card.com/ProShow.asp?ProID=490) | $17.99 |  4.0b: September 3, 2024 |                                      ALL                                      |                                ALL                                | Only r4isdhc **.com** carts marked with a year of 2014 or later are compatible.                                                                                                                                                                                            |
| **Ace3DS Plus**                                                                                                             |                        |                            No                            |                                      ALL                                      |                                ALL                                | This cart needs an SD card inserted to function for both ntrboot and regular NDS firmware.                                                                                                                                                                                                 |
| **Acekard 2i**                                                                                                              |                        |                            No                            |       <= 4.3.0       | <= 1.4.4 |                                                                                                                                                                                                                                                                                                            |
| **Gateway Blue**                                                                                                            |                        |                            No                            | 4.1.0 - 4.5.0 |                                ALL                                |                                                                                                                                                                                                                                                                                                            |
| **Infinity 3 R4i** (r4infinity.com)                                                      |                        |                            No                            |                                      ALL                                      |                                ALL                                |                                                                                                                                                                                                                                                                                                            |
| **R4 3D Revolution**                                                                                                        |                        |                            No                            |                                      None                                     |                                None                               |                                                                                                                                                                                                                                                                                                            |
| **R4i Gold 3DS Plus** (r4ids.cn)                                                         |                        |                            No                            |                                      ALL                                      |                                ALL                                | **Comes pre-flashed with ntrboot** ([internal switch to switch between ntrboot and NDS modes](/images/screenshots/r4i-gold-3ds-plus.png)); do not manually flash with ntrboot.                                                                                          |
| **R4i Gold 3DS** (r4ids.cn)                                                              |                        |                            No                            |                                      ALL                                      |                                ALL                                | All carts are compatible.                                                                                                                                                                                                                                                                  |
| **R4i Ultra** (r4ultra.com)                                                              |                        |                            No                            |       <= 4.3.0       |                                ALL                                |                                                                                                                                                                                                                                                                                                            |
| **R4i-SDHC 3DS RTS Deluxe Edition**                                                                                         |                        |                          Unknown                         |                                      ALL                                      |                                ALL                                | Only the Deluxe Edition with the blue sticker is compatible.                                                                                                                                                                                                                               |
| **R4iSDHC RTS LITE 20XX** (r4isdhc.com)                                                  |                        |  4.0b: September 3, 2024 |                                      ALL                                      |                                ALL                                | Only r4isdhc **.com** carts marked with a year of 2014 or later are compatible.                                                                                                                                                                                            |
| **R4iSDHC Dual-Core 20XX** (r4isdhc.com)                                                 |                        |  4.0b: September 3, 2024 |                                      ALL                                      |                                ALL                                | Only r4isdhc **.com** carts marked with a year of 2014 or later are compatible.                                                                                                                                                                                            |

::: info

![](/images/screenshots/ntrboot-flashcarts.png)

:::

Ensure your flashcart is able to launch `.nds` files on your console before beginning. 某些烧录卡可能需要其 SD 卡内含有固件或“内核”文件。 请阅读你的烧录卡的说明书来了解更多细节。

请注意，某些方法可能有额外的兼容步骤供参阅。

The usage of this exploit, regardless of the flashing method, requires access to a small magnet if the target console is of a folding style (any 3DS family system that is not the old 2DS with a sleep switch). This is because the exploit requires your console to enter sleep mode while still having access to the buttons.

::: info

To test if a magnet will work, hold it on or around the (A)(B)(X)(Y) buttons while the console is powered on to see if it triggers sleep mode. 如果会的话，只要把磁铁在那个位置附近，主机的两个屏幕就应该都会变黑。

:::

请注意，在写入 ntrboot 漏洞后你将无法使用烧录卡的正常功能（除了Acekard 2i，其在 **NDS 和已破解的 3DS 上**仍能正常使用）。 也就是说大部分烧录卡在被写入 ntrboot 后在主菜单中都不会出现其图标。 在写入 ntrboot 后，你可以通过可选步骤将其从烧录卡中移除。

::: danger

请注意，极少见的情況下某些伪劣烧录卡有可能会在破解过程中坏掉且无法恢复。 这不太可能， 但无论如何我们只支持写在兼容表格中的烧录卡。 To reduce the chance of receiving a counterfeit card, it is recommended that you use a reputable site to buy your flashcart (such as [NDS Card](https://www.nds-card.com/)).

:::

___

## Methods

___

### Flashing ntrboot (3DS Single System)

本方法只需一台未破解的 3DS 和一张兼容的烧录卡。 本教程烧录卡将用于在你的 3DS 上运行 ntrboot flasher `.nds` 文件。 这也就是说，若想要在3DS上使用你持有的烧录卡运行 `.nds` 文件，烧录卡必须支持在你的 3DS 系统版本上运行。 请参阅上方的烧录卡兼容列表了解更多。

::: tip

继续至[写入ntrboot（通过单台 3DS）](flashing-ntrboot-\(3ds-single-system\))

:::

___

### Flashing ntrboot (3DS Multi System)

This method requires temporary access to a second 3DS family console that is already running boot9strap. 你的烧录卡在本方法中不受 3DS 系统版本的限制。

::: tip

继续至[写入 ntrboot（通过多台 3DS）](flashing-ntrboot-\(3ds-multi-system\))

:::

___

### Flashing ntrboot (NDS)

本方法将会暂时用到一台与你的烧录卡兼容的 Nintendo DS 或 Nintendo DS Lite 主机。 烧录卡将用于在你的 NDS 上运行 ntrboot 写入程序的 `.nds` 文件。

::: tip

继续至[写入 ntrboot（通过 NDS）](flashing-ntrboot-\(nds\))

:::

___

### Flashing ntrboot (DSi)

本方法需要暂时用到一台与你烧录卡兼容的 Nintendo DSi 主机。 烧录卡将用于在你的 DSi 上运行 ntrboot 写入程序的 `.nds` 文件。 这也就是说，若想要在 DSi 上使用你持有的烧录卡运行 `.nds` 文件，烧录卡必须支持在你的 DSi 系统版本上运行。 请参阅上方的烧录卡兼容列表了解更多。

::: tip

继续至[写入 ntrboot（通过 DSi）](flashing-ntrboot-\(dsi\))

:::
