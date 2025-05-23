# Ολοκλήρωση εγκατάστασης

## Απαραίτητη ανάγνωση

Στην προηγούμενη σελίδα, εγκαταστήσατε το boot9strap, ένα λογισμικό φόρτωσης του custom firmware, το οποίο φορτώνει το αρχείο `boot.firm` από την κάρτα SD ή τη NAND (εσωτερική μνήμη). Σε αυτήν την περίπτωση, χρησιμοποιούμε το Luma3DS της [LumaTeam](https://github.com/LumaTeam/) ως το `boot.firm` μας για να τροποποιήσουμε την κονσόλα, επιτρέποντάς της να εκτελεί λογισμικό homebrew.

Σε αυτήν τη σελίδα, θα δημιουργήσουμε σημαντικά αντίγραφα ασφαλείας των αρχείων του συστήματος και θα εγκαταστήσουμε μερικές εφαρμογές homebrew. Τα περισσότερα από αυτά τα βήματα θα γίνουν αυτόματα με ένα script που θα εκτελέσετε στην κονσόλα σας.

::: info

Το script θα εγκαταστήσει τις ακόλουθες εφαρμογές:

- Το **FBI** του Steveice10 _(εγκαθιστά εφαρμογές της μορφής CIA)_
- Το **Homebrew Launcher Loader** του PabloMK7 _(εκτελεί το Homebrew Launcher, για εφαρμογές homebrew της μορφής 3DSX)_
- Το **Anemone3DS** του astronautlevel2 _(εγκαθιστά προσαρμοσμένα θέματα, οθόνες εκκίνησης και εμβλήματα)_
- Το **Checkpoint** του BernardoGiordano/FlagBrew _(διαχειρίζεται αποθηκευμένα δεδομένα παιχνιδιών 3DS/DS)_
- Το **ftpd** του mtheall _(επιτρέπει την ασύρματη πρόσβαση στην κάρτα SD του 3D μέσω FTP)_
- Το **Universal-Updater** της Universal-Team _(κατάστημα εφαρμογών για τη λήψη homebrew μέσω Wi-Fi)_
- Το **GodMode9** του d0k3 _(εργαλείο πολλαπλών χρήσεων για την εξαγωγή δεδομένων από την εσωτερική μνήμη ή τις κασέτες)_

Εάν δεν θέλετε κάποια από αυτές τις εφαρμογές, μπορείτε να την αφαιρέσετε αφού ολοκληρώσετε τα βήματα αυτής της σελίδας, από την εφαρμογή «System Settings» -> «Data Management» -> «Nintendo 3DS» -> «Software». (Δεν είναι δυνατή η αφαίρεση του GodMode9 με αυτόν τον τρόπο, το οποίο απαιτείται γενικά για άλλες λειτουργίες.)

::: details Σύνδεσμοι πηγαίου κώδικα (προαιρετικό)

Όλες οι εφαρμογές που σας βοηθά να εγκαταστήσετε ο παρών οδηγός είναι ανοικτού κώδικα. Εάν σας ενδιαφέρει να δείτε πώς λειτουργούν ή θέλετε να αφήσετε μια θετική αξιολόγηση για να δείξετε την εκτίμησή σας, θα βρείτε συνδέσμους για τον πηγαίο κώδικά τους στην παρακάτω λίστα:

- [FBI](https://github.com/lifehackerhansol/FBI)
- [Homebrew Launcher Loader](https://github.com/PabloMK7/homebrew_launcher_dummy)
- [Anemone3DS](https://github.com/astronautlevel2/Anemone3DS)
- [Checkpoint](https://github.com/bernardogiordano/checkpoint/releases)
- [ftpd](https://github.com/mtheall/ftpd)
- [Universal-Updater](https://github.com/Universal-Team/Universal-Updater/)
- [GodMode9](https://github.com/d0k3/GodMode9)

:::

## Σημειώσεις συμβατότητας

::: info

Εάν η προηγούμενή σας εγκατάσταση CFW βασιζόταν στην EmuNAND και επιθυμείτε να μετακινήσετε τα περιεχόμενα της EmuNAND/RedNAND σας στη SysNAND, ακολουθήστε τα βήματα για [Μετακίνηση της EmuNAND](move-emunand) πριν ακολουθήσετε αυτήν τη σελίδα. Εάν δεν γνωρίζετε τι είναι μια EmuNAND, αυτό δεν ισχύει για εσάς.

:::

## Τι χρειάζεστε

- Το [x_finalize_helper.firm](https://github.com/hacks-guide/finalize/releases/latest/download/x_finalize_helper.firm) (απευθείας λήψη)
- Το [finalize.romfs](https://github.com/hacks-guide/finalize/releases/latest/download/finalize.romfs) (απευθείας λήψη)

## Οδηγίες

### Ενότητα I - Προετοιμασία

Σε αυτήν την ενότητα, θα αντιγράψετε τα αρχεία που απαιτούνται για τις υπόλοιπες οδηγίες αυτής της σελίδας.

1. Απενεργοποιήστε την κονσόλα σας
2. Εισαγάγετε την κάρτα SD στον υπολογιστή σας
3. Αντιγράψτε το `finalize.romfs` στη ρίζα της κάρτας SD σας
4. Ανοίξτε τον φάκελο `luma` στην κάρτα SD και, μέσα σε αυτόν, δημιουργήστε έναν φάκελο με το όνομα `payloads`, εφόσον δεν υπάρχει ήδη
5. Αντιγράψτε το `x_finalize_helper.firm` στον φάκελο `payloads`
6. Εισαγάγετε ξανά την κάρτα SD στην κονσόλα σας

Το παρακάτω στιγμιότυπο οθόνης υποδεικνύει τη βασική διάταξη κάρτας SD που απαιτείται για να ακολουθήσετε τις οδηγίες αυτής της σελίδας. Ενδέχεται να έχετε επιπλέον αρχεία ή φακέλους στην κάρτα SD, ανάλογα με την προηγούμενη εγκατάσταση ή τη μέθοδο που ακολουθήσατε.

::: info

![](/images/screenshots/finalizing-root-layout.png)

:::

::: info

![](/images/screenshots/finalizing-luma-payloads.png)

:::

### Ενότητα II - Ενημέρωση του συστήματος

Σε αυτήν την ενότητα, θα ενημερώσετε το σύστημά σας στην πιο πρόσφατη έκδοση, κάτι που μπορείτε να κάνετε με ασφάλεια με το custom firmware.

<!--@include: ./_include/sysupdate.md -->

### Ενότητα III - Ρύθμιση RTC και DSP

Σε αυτήν την ενότητα, θα συγχρονίσετε το εσωτερικό ρολόι του 3DS σας με τον πραγματικό χρόνο και θα αποτυπώσετε το firmware ήχου (το οποίο είναι απαραίτητο για τη σωστή χρήση του ήχου σε ορισμένες εφαρμογές homebrew).

1. Πατήστε τα (L) + (Κάτω) + (Select) ταυτόχρονα ώστε να εκκινήσετε το μενού Rosalina
    - Εάν κάποιο από αυτά τα κουμπί δεν λειτουργεί, κάντε λήψη του [config.ini](/assets/config.ini) και τοποθετήστε το στον φάκελο `luma`, αντικαθιστώντας το υπάρχον αρχείο. Αυτή η ενέργεια θα αλλάξει τον συνδυασμό πλήκτρων για το μενού Rosalina σε (X) + (Y)
2. Επιλέξτε «Miscellaneous options»
3. Επιλέξτε «Dump DSP firmware»
4. Πατήστε το (Β) για να συνεχίσετε
5. Επιλέξτε «Nullify user time offset»
6. Πατήστε το (Β) για να συνεχίσετε
7. Πατήστε το (B) για να επιστρέψετε στο κύριο μενού Rosalina
8. Πατήστε το (B) για να κλείσετε το μενού Rosalina

### Ενότητα IV - Script ρυθμίσεων

Σε αυτήν την ενότητα, θα χρησιμοποιήσετε μια σειρά από script για την αυτοματοποίηση της εγκατάστασης του homebrew, τον καθαρισμό της κάρτας SD και τη δημιουργία αντιγράφου ασφαλείας του συστήματος.

1. Απενεργοποιήστε την κονσόλα σας
2. Κρατήστε πατημένο το (X) και ταυτόχρονα, ενεργοποιήστε την κονσόλα σας. Με αυτόν τον τρόπο, θα εκκινηθεί ο βοηθός ολοκλήρωσης εγκατάστασης
    - Εάν γίνει εκκίνηση στο μενού «HOME», ο φάκελος `payloads` ενδέχεται να έχει λάθη στο όνομά του ή να μη βρίσκεται στη σωστή τοποθεσία
    - Εάν αντιμετωπίσετε κάποιο σφάλμα, συμβουλευτείτε τη σελίδα [Επίλυση προβλημάτων](troubleshooting-finalizing-setup)
3. Εάν η διαδικασία ήταν επιτυχής, η κονσόλα σας θα εκκινηθεί στο GodMode9
    - Από εδώ και στο εξής, μπορείτε να έχετε πρόσβαση στο GodMode9 κρατώντας πατημένο το START κατά την ενεργοποίηση της κονσόλας σας
4. Εάν σας ζητηθεί να δημιουργήσετε ένα απαραίτητο αντίγραφο ασφαλείας, πατήστε το (A) ώστε να πραγματοποιηθεί και έπειτα, πατήστε το (A) για να συνεχίσετε μόλις ολοκληρωθεί η διαδικασία
5. Εάν σας ζητηθεί να διορθώσετε την ημερομηνία και την ώρα RTC, πατήστε το (A) για να το κάνετε και έπειτα, ορίστε την ημερομηνία και την ώρα. Τέλος, πατήστε το (A) για να συνεχίσετε
6. Πατήστε το (Home) για να εμφανιστεί το μενού ενεργειών
7. Επιλέξτε «Scripts...»
8. Επιλέξτε «finalize»
9. Ακολουθήστε τις οδηγίες του script, απαντώντας σε όποιες ερωτήσεις σάς γίνουν
    - Εάν δείτε το «Information #05: No title database», πατήστε το (A) για να γίνει εισαγωγή και εισαγάγετε τα κουμπιά που αναγράφονται στην οθόνη για να συνεχίσετε
    - Εάν αντιμετωπίσετε κάποιο σφάλμα, ακολουθήστε τις οδηγίες στο μήνυμα σφάλματος ή συμβουλευτείτε τη σελίδα [Επίλυση προβλημάτων](troubleshooting-finalizing-setup)
10. Μόλις το script δηλώσει «Setup complete!», πατήστε το (A) για να απενεργοποιήσετε την κονσόλα σας
    - Εάν ΔΕΝ βλέπετε το μήνυμα «Setup complete!», το script δεν ήταν επιτυχές και θα χρειαστεί να επαναλάβετε αυτήν την ενότητα από το Βήμα 3
11. Εισαγάγετε την κάρτα SD στον υπολογιστή σας
12. Αντιγράψτε τον φάκελο `/gm9/backups/` σε μια ασφαλή τοποθεσία του υπολογιστή σας
    - Αυτός ο φάκελος περιέχει σημαντικά αντίγραφα ασφαλείας αρχείων και θα πρέπει να διατηρείτε αντίγραφά του σε πολλαπλές τοποθεσίες (π.χ. αποθηκευτικό χώρο cloud) αν είναι εφικτό
    - Τα δύο αρχεία SysNAND αποτελούν το αντίγραφο ασφαλείας της NAND και μπορούν να χρησιμοποιηθούν για την επαναφορά της κονσόλας σας σε λειτουργική κατάσταση εάν αυτή καταστεί μη λειτουργική εξαιτίας κάποιου ζητήματος λογισμικού
    - Το αρχείο `essential.exefs` περιέχει τα μοναδικά αρχεία του συστήματός σας και μπορεί να χρησιμοποιηθεί για την ανάκτηση των δεδομένων σας σε περίπτωση αστοχίας του υλικού
13. Εάν τα έχετε ακόμα, διαγράψτε τα δύο αρχεία `SysNAND` από τον φάκελο `/gm9/backups/` της κάρτας SD σας
    - Το αρχείο `essential.exefs` είναι μικρό και μπορεί να διατηρηθεί στην κάρτα SD σας για ευκολία πρόσβασης

___

::: tip

Αυτό ήταν! Η ρύθμιση του custom firmware στην κονσόλα σας έχει πλέον ολοκληρωθεί.

:::

::: info

Σκέφτεστε τι μπορείτε να κάνετε με την τροποποιημένη σας συσκευή; Επισκεφτείτε [το wiki μας](https://wiki.hacks.guide/wiki/3DS:Things_to_do)!

:::

### Πληροφορίες και σημειώσεις

::: info

Ακολουθούν ορισμένοι συνδυασμοί πλήκτρων που θα πρέπει να γνωρίζετε:

- Εάν κρατήσετε πατημένο το (Select) κατά την εκκίνηση, θα ανοίξει το μενού ρυθμίσεων του Luma3DS.
- Εάν κρατήσετε πατημένο το (Start) κατά την εκκίνηση, θα ανοίξει το GodMode9, ενώ αν έχετε πολλαπλά payload στον φάκελο `/luma/payloads/`, θα εκκινηθεί το chainloader του Luma3DS.
- Από προεπιλογή, πατώντας τα (L) + (Κάτω) + (Select) στη λειτουργία 3DS, θα ανοίξει το μενού Rosalina, όπου μπορείτε να ελέγξετε τις πληροφορίες του συστήματος, να δημιουργήσετε στιγμιότυπα οθόνης, να ενεργοποιήσετε τα cheat και πολλά άλλα. Μπορείτε να αλλάξετε αυτόν τον συνδυασμό πλήκτρων από το μενού Rosalina.
- Κρατώντας πατημένα τα (Start) + (Select) + (X) κατά την εκκίνηση, το LED ειδοποιήσεων θα εμφανίσει ένα χρώμα για σκοπούς εντοπισμού σφαλμάτων. Δείτε το [αρχείο καταγραφής αλλαγών](https://github.com/SciresM/boot9strap/releases/tag/1.4) για μια λίστα.

:::

::: info

Για πληροφορίες σχετικά με τη χρήση των διάφορων λειτουργιών του GodMode9, ανατρέξτε στις σελίδες [Χρήση του GodMode9](godmode9-usage) και [Αποτύπωση τίτλων και κασετών παιχνιδιών](dumping-titles-and-game-cartridges).

:::
