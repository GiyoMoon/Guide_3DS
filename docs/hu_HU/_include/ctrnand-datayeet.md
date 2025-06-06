Ez a rész a rendszer beállítások alaphelyzetbe állítását szolgálja. **A telepített játékok és mentéseik nem érintettek.** Ez **szükséges**, hogy megelőzzük az ismert problémákat, amit a kibővített memória módhoz és appletekhez bizonyos konzolokon.

::: warning

Ez a folyamat alaphelyzetbe állítja a Mii adatot. Ha szeretnéd menteni Mii-ket amiket létrehoztál, either [generálj egy QR kódot](https://en-americas-support.nintendo.com/app/answers/detail/a_id/298/~/how-to-generate-a-qr-code%E2%84%A2-for-a-mii) minden Mii-hez, amit menteni szeretnél, vagy készíts egy mentést a `SYSNAND CTRNAND:/data/<ID0>/extdata/00048000/f000000b`-ről mielőtt folytatot ezeket a lépéseket. Visszaállíthatod ezt a fájlt ugyanebbe a könyvtárba _miután_ a konzolod végig ment a kezdeti telepítési folyamaton.

:::

1. Kapcsold ki a konzolod
2. Nyomd le és tartsd nyomva a (Start) gombot, és a (Start) nyomva tartása mellett kapcsold be a konzolod. Ez elindítja a GodMode9-et
3. Navigálj ide: `[1:] SYSNAND CTRNAND` -> `data` -> `<ID0>` -> `sysdata`
    - Az `<ID0>` egy 32 karakter hosszú nevű mappa
4. Használd a D-Pad-et a `00010017` kijelöléséhez
5. Nyomd meg a (jobb váll) + (A) gombokat a mappa opciók előhozásához
6. Válaszd ki ezt: "Copy to 0:/gm9/out"
7. Nyomd meg az (A) gombot a folytatáshoz
8. A `00010017`-et mg mindig kijelölve, nyomj (X)-et a törléséhez
9. Nyomd meg az (A) gombot a megerősítéshez
10. Nyomd meg az (A) gombot, hogy feloldd a SysNAND (lvl1) írást, majd sorban nyomd meg a kijelzett gombokat
11. Miután a fájl törlődött, nyomd meg az (A) gombot a folytatáshoz
12. Nyomd meg az (A) gombot az írási engedélyek visszavonásához
13. Nyomd meg a (Start) gombot a konzolod újraindításához
14. A konzolod be fog tölteni a kezdeti telepítési menübe
    - Ez az elvárt viselkedés. Valószínüleg nem vesztettél el játék adatot
15. Fejezd be a kezdeti telepítési menüt, követve az utasításokat a konzolod képernyőjén
