# ntrboot

::: danger

NDS Card has [suspended outgoing packages to the United States](https://nds-card.com/NewsShow.asp?NewsID=1344). All product links listed below may not ship to the United States. For further support (in English), join [Nintendo Homebrew on Discord](https://discord.gg/MWxPgEp).

:::

::: tip

If your flashcart comes pre-flashed with ntrboot (or you have already flashed ntrboot to your flashcart), you can skip to [Installing boot9strap (ntrboot)](installing-boot9strap-\(ntrboot\)) for instructions on how to use it.

:::

## Required Reading

התקנת boot9strap עם ntrboot דורשת כרטיס פריצה NDS / DSi תואם כדי לצרוב אליו את ntrboot. Note that some of these flashcarts are sold pre-flashed with ntrboot.

While the ntrboot exploit works independently of the system version, the ntrboot flasher (which installs the exploit to the cart) is not. This means that, depending on the versions and consoles supported by your flashcart, only certain methods may be available to you.

שימו לב שכרטיסים עם "פצצת זמן" לא יוכלו להפעיל קבצי `.nds` כשהם מגלים ששעון המערכת עבר תאריך שנקבע על ידי הקושחה של כרטיס הפריצה. דרך אחת לעקוף את זה זה להחזיר את שעון המערכת אחורה.

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

Ensure your flashcart is able to launch `.nds` files on your console before beginning. כרטיסי פריצה דורשים קבצי קושחה או "קרנל" מועתקים לכרטיס הSD של הכרטיס. תבדקו בהוראות של כרטיס הפריצה שלכם לעוד מידע.

שימו לב שלדרכים ספציפיות יכול להיות מידע תאימות נוסף.

The usage of this exploit, regardless of the flashing method, requires access to a small magnet if the target console is of a folding style (any 3DS family system that is not the old 2DS with a sleep switch). This is because the exploit requires your console to enter sleep mode while still having access to the buttons.

::: info

To test if a magnet will work, hold it on or around the (A)(B)(X)(Y) buttons while the console is powered on to see if it triggers sleep mode. אם הוא כן, שני המסכים יהיו שחורים כל עוד המגנט מוחזק במקום הזה.

:::

Note that the flashcart will not be able to be used for its standard functions while the ntrboot exploit is installed on it (except for in the case of the Acekard 2i, which remains functional _on NDS and custom firmware 3DS systems only_). This means that, for most flashcarts, it will not even display on the HOME Menu. יש שלבים אופטימלים בסוף הוראות צריבת ntrboot כדי למחוק אותו מכרטיס הפריצה אחרי שסיימתם.

::: danger

שימו לב שבמקרים נדירים, יתכן שתהליך הצריבה **ישבור** כרטיס פריצה מזוייף ויגרום לו לא לעבוד. This is unlikely, but nevertheless, only original listed flashcarts are supported. To reduce the chance of receiving a counterfeit card, it is recommended that you use a reputable site to buy your flashcart (such as [NDS Card](https://www.nds-card.com/)).

:::

___

## Methods

___

### Flashing ntrboot (3DS Single System)

שיטה זו דורשת כלום חוץ מה3DS הלא פרוץ שלכם וכרטיס פריצה תואם. שיטה זאת משתמשת בכרטיס פריצה כדי להריץ את קובץ ה`.nds` של צורב הNTRBOOT על ה3DS שלכם. זה אומר שכרטיס הפריצה שלכם חייב לתמוך בהרצת קבצי `.nds` על הגרסה של ה3DS שלכם. תסתכלו על הטבלה למעלה למידע נוסף.

::: tip

Continue to [Flashing ntrboot (3DS Single System)](flashing-ntrboot-\(3ds-single-system\))

:::

___

### Flashing ntrboot (3DS Multi System)

This method requires temporary access to a second 3DS family console that is already running boot9strap. זה לא מחייב את כרטיס הפריצה לתמוך בגרסה של אף אחד מה3DSים.

::: tip

Continue to [Flashing ntrboot (3DS Multi System)](flashing-ntrboot-\(3ds-multi-system\))

:::

___

### Flashing ntrboot (NDS)

דרך זו דורשת גישה זמנית לNintendo DS או Nintendo DS Lite שתומך בכרטיס פריצה שלכם. שיטה זאת משתמשת בכרטיס פריצה כדי להריץ את קובץ ה`.nds` של צורב הNTRBOOT על הNDS שלכם.

::: tip

Continue to [Flashing ntrboot (NDS)](flashing-ntrboot-\(nds\))

:::

___

### Flashing ntrboot (DSi)

דרך זו דורשת גישה זמנית לNintendo DSi שתומך בכרטיס פריצה שלכם. This method uses the flashcart to run the ntrboot flasher `.nds` file on your DSi. This means that your flashcart must support launching `.nds` files on your DSi's version. תסתכלו על הטבלה למעלה למידע נוסף.

::: tip

Continue to [Flashing ntrboot (DSi)](flashing-ntrboot-\(dsi\))

:::
