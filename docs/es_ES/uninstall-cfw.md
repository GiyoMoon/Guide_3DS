# Desinstalar CFW

## Lectura requerida

Esto quitará completamente el CFW de tu consola, incluyendo boot9strap y Luma3DS, con el propósito de restaurar la consola a su estado original.

Any unsigned (illegitimate) games will be rendered unusable and will be removed during this process. Usa un [gestor de datos de guardado](https://github.com/FlagBrew/Checkpoint/releases/latest) para respaldar los datos de guardado que te importen.

::: danger

Si estás desinstalando CFW porque:

- Quieres reinstalarlo
- Necesitas cambiar la tarjeta SD
- La tarjeta SD se perdió o se corrompió
- Uno de tus juegos no funciona
- Uno de los programas del sistema no funciona
- Your console is unable to boot to HOME Menu

<u>**STOP!!!**</u> Uninstalling custom firmware is an unnecessary risk that will at best waste your time and at worst <u>**BRICK**</u> your console. A better idea would be to ask for help at [Nintendo Homebrew on Discord](https://discord.gg/MWxPgEp).

:::

::: danger

If you have done ANY of the following:

- [Cambiar la región](region-changing) de la consola
- Instalar un teclado personalizado
- Instalar un menú HOME personalizado (_no_ un tema personalizado)
- Manually changed the encryption key (`movable.sed`) of the console
- Unbanned the console

then uninstalling CFW <u>**WILL BRICK YOUR CONSOLE**</u>. If this applies to you, [restore a clean NAND backup](godmode9-usage#restoring-a-nand-backup) before continuing.

:::

::: warning

These instructions will only work on consoles with a Luma3DS version of 8.0 or higher. If you have an older version of Luma, you must upgrade your setup before following these instructions. Follow [this page](checking-for-cfw) to find your upgrade instructions.

:::

## Lo que necesitas

- La última versión de [Luma3DS](https://github.com/LumaTeam/Luma3DS/releases/latest) (el archivo `.zip` de Luma3DS)
- - La última versión de [GodMode9](https://github.com/d0k3/GodMode9/releases/latest) (el archivo GodMode `.zip`)
- The latest release of [DSiWare Uninstaller](https://github.com/MechanicalDragon0687/DSiWare-Uninstaller/releases/latest)
- [safety_test.gm9](/gm9_scripts/safety_test.gm9)
- [uninstall_cfw.gm9](/gm9_scripts/uninstall_cfw.gm9)

## Instrucciones

### Sección I - Preparativos

1. Apaga la consola
2. Inserta la tarjeta SD en tu computadora
3. Copia todo lo que está dentro del `.zip` de Luma3DS a la raíz de tu tarjeta SD
4. Copia `Godmode9.firm` desde Godmode9 `.zip` a la carpeta `/luma/payloads/` en la tarjeta SD
5. Copia la carpeta `gm9` de GodMode9 `.zip` a la raíz de la tarjeta SD
6. Copy `DSiWareUninstaller.3dsx` to the `/3ds/` folder on your SD card
7. Copy `safety_test.gm9` and `uninstall_cfw.gm9` to the `/gm9/scripts/` folder on your SD card
8. Reinserta la tarjeta SD en la consola

### Section II - DS Mode Tests

The purpose of this section is to check whether built-in DS mode applications will continue to work once CFW is uninstalled. If you skip this section, DS mode or its functions may be inaccessible until CFW is reinstalled.

#### DS Connection Settings Test

1. Enciende tu consola
2. Inicia la configuración de la consola
3. Navigate to `Internet Settings` -> `Nintendo DS Connection Settings`, then click OK
4. You should boot into the Nintendo DS Connection Setup menu
    - If your console displays the Japanese version of Flipnote Studio, a black screen, or an error message, the test has failed
5. Apaga la consola

#### DS Download Play Test

1. Enciende tu consola
2. Launch the Download Play application (![](/images/download-play-icon.png){height="24px" width="24px"})
3. Select "Nintendo DS"
4. If your console loads into a "Download software via DS Download Play" menu, the test was successful
    - If your console displays the Japanese version of Flipnote Studio, a black screen, or an error message, the test has failed
5. Apaga la consola

::: warning

If either of these tests has failed, DS mode, DS Download Play, and/or DS Connection Settings may be inaccessible once CFW is uninstalled! You should [fix DS mode](troubleshooting-post-install) before continuing.

:::

### Section III - Safety Test

The purpose of this section is to verify that the console will boot and that critical system functions, like System Settings and the keyboard, will work once CFW is uninstalled. **If you skip this section, you may BRICK your console!**

1. Presiona y mantén (Start), luego enciende la consola mientras lo mantienes. Esto abrirá GodMode9
2. If you are prompted to create an essential files backup, press (A) to do so, then press (A) to continue once it is complete
3. Si se te pide establecer la fecha y hora RTC, presiona (A) para hacerlo, después establece la fecha y hora, y después presiona (A) para continuar
    - Note that, if you had to fix the RTC date and time, you will have to fix the time in the System Settings as well after following this guide
4. Presiona el botón (HOME) para abrir el menú de acciones
5. Selecciona "Scripts..."
6. Select "safety_test"
7. Read the text on-screen and press (A) to continue
8. You should boot into the regular 3DS HOME Menu (any custom theme is irrelevant). If you do, continue these instructions
    - If you do not boot into the regular 3DS HOME Menu (black screen, error screen, etc.), uninstalling CFW **WILL BRICK YOUR CONSOLE!**
9. Inicia la configuración de la consola
    - If the console crashes at this point, the test has failed
10. Selecciona "Otras opciones"
11. Select "Profile"
12. Select "User Name"
13. If you are able to enter a new user name, the test was successful
    - If the keyboard does not appear, the screen freezes, or the console crashes, the test has failed
14. Apaga la consola

::: danger

If you do NOT boot into the regular 3DS HOME Menu, or System Settings / your keyboard is inaccessible, **DO NOT continue with these instructions**! Join [Nintendo Homebrew on Discord](https://discord.gg/MWxPgEp) and ask (in English) for someone there to assist you.

:::

### Sección IV - Copia de seguridad de la NAND

1. Presiona y mantén (Start), luego enciende la consola mientras lo mantienes. Esto abrirá GodMode9
2. Presoina (Home) para abrir el menú de acciones
3. Selecciona "Scripts..."
4. Selecciona "GM9Megascript"
5. Selecciona "Backup Options"
6. Selecciona "SysNAND Backup"
7. Presiona (A) para confirmar
    - Este proceso tomará un tiempo
    - Si aparece un error, asegúrate de que tienes al menos 1,3GB de espacio libre en la tarjeta SD
8. Presiona (B) para regresar al menú principal
9. Selecciona “Exit”
10. Presiona (Home) para abrir el menú de acciones
11. Selecciona "Poweroff system" para apagar tu consola

### Section V - Removing illegitimate content

::: warning

This section will remove illegitimate content, like homebrew and dumped cartridges. If you have save data that you care about, back it up with a save manager before continuing!

:::

1. Enciende tu consola
2. Inicia la configuración de la consola
3. Navigate to Data Management > Nintendo 3DS > Software
4. In this list of software, delete any non-Nintendo content you installed while using CFW
    - This includes common system software such as FBI, Anemone3DS, Luma Updater, Homebrew Launcher, Checkpoint, and others, along with any games and titles that you did _not_ install from the eShop
5. Navigate to `Data Management` -> `DSiWare`
6. In this list of software, delete any non-Nintendo content you installed while using CFW
    - This includes software such as TWiLightMenu++, along with any games and titles that you did _not_ install from the eShop
    - Failure to remove all CFW software from both the 3DS and DSiWare sections before uninstalling CFW may prevent or disable access to the Data Management menu after uninstalling CFW, which will make it difficult to re-install CFW in the future
7. Sal de Configuración de la Consola
8. Launch the Download Play application (![](/images/download-play-icon.png){height="24px" width="24px"})
9. Wait until you see the two buttons
10. Oprime (L) + (Abajo) + (SELECT) a la vez para abrir el menú Rosalina
11. Selecciona "Miscellaneous options"
12. Select "Switch the hb. title to the current app."
13. Presiona (B) para continuar
14. Presiona (B) para volver al menú principal de Rosalina
15. Presiona (B) para salir del menú de Rosalina
16. Press (Home), then close Download Play
17. Launch the Download Play application (![](/images/download-play-icon.png){height="24px" width="24px"})
18. Your console should load the Homebrew Launcher
19. Launch DSiWare Uninstaller from the list of homebrew
20. Follow the prompts and allow the program to uninstall
21. Once the process has succeeded, exit the Homebrew Launcher and power off your console

### Section VI - System Format

This section will ensure that all illegitimate tickets are removed, allowing eShop to work normally. This will remove all content from the 3DS and log you out of your NNID. Keep in mind that your console's encryption key will be shuffled, meaning that any old data will be rendered inaccessible, even if you have a backup of your SD contents.

1. Enciende tu consola
2. Inicia la configuración de la consola
3. Navigate to Other Settings -> Next Page (until the final page) -> Format System Memory
4. Follow the prompts to format your 3DS

### Section VII - Running Uninstall Script

::: warning

This is your final opportunity to verify that all safety steps above have been followed! Please ensure that you have followed all sections on this page, **especially** `Section III - Safety Test`, before continuing.

:::

::: danger

Si estás desinstalando CFW porque:

- Quieres reinstalarlo
- Necesitas cambiar la tarjeta SD
- La tarjeta SD se perdió o se corrompió
- Uno de tus juegos no funciona
- Uno de los programas del sistema no funciona
- Your console is unable to boot to HOME Menu

<u>**STOP!!!**</u> Uninstalling custom firmware is an unnecessary risk that will at best waste your time and at worst <u>**BRICK**</u> your console. A better idea would be to ask for help at [Nintendo Homebrew on Discord](https://discord.gg/MWxPgEp).

:::

1. Presiona y mantén (Start), luego enciende la consola mientras lo mantienes. Esto abrirá GodMode9
    - If you instead see the Luma3DS chainloader, use the D-Pad and the (A) button to select GodMode9
2. Presiona el botón (HOME) para abrir el menú de acciones
3. Selecciona "Scripts..."
4. Select "uninstall_cfw"
5. When prompted, press (A) to proceed
6. Press (A) again to proceed
7. Press (A) to unlock SysNAND (lvl3) writing, then input the key combo given
8. Presiona (A) para continuar
9. Press (A) to relock write permissions if prompted
10. Presiona (Start) para reiniciar tu consola

___

::: tip

All custom firmware has been removed from your console.

:::

::: info

You can now remove any extra files and folders from the root of your SD card that are _not_ the `Nintendo 3DS`, `DCIM`, or `private` folders.

:::
