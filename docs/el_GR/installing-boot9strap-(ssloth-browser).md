# Εγκατάσταση του boot9strap (SSLoth-Browser)

:::details Τεχνικές λεπτομέρειες (προαιρετικό)

Για να εκμεταλλευτούμε την εφαρμογή «Internet Browser», πρέπει να παρακάμψουμε τον έλεγχο έκδοσης του προγράμματος περιήγησης, ο οποίος έχει σχεδιαστεί για να αποτρέπει τη χρήση του χωρίς ενημέρωση στην πιο πρόσφατη έκδοση του συστήματος.

Διατίθεται ένας δημόσιος διακομιστής μεσολάβησης, ο οποίος, με τη βοήθεια του exploit «SSLoth», μπορεί να παρακάμψει αυτόν τον έλεγχο.

Μόλις ενεργοποιηθεί η παράκαμψη, θα έχετε τη δυνατότητα πρόσβασης σε μια ιστοσελίδα του exploit που θα κάνει τα υπόλοιπα.

Για τεχνικές λεπτομέρειες σχετικά με τα exploit που θα χρησιμοποιήσετε σε αυτήν τη σελίδα, δείτε [εδώ](https://github.com/MrNbaYoh/3ds-ssloth) (SSLoth) και [εδώ](https://github.com/TuxSH/universal-otherapp) (universal-otherapp).

:::

## Σημειώσεις συμβατότητας

Το SSLoth επιτρέπει στους χρήστες της έκδοσης 11.13.0 και παλαιότερων να παρακάμψουν τον έλεγχο έκδοσης του προγράμματος περιήγησης, επιτρέποντας τη χρήση του new-browserhax ή του old-browserhax (συμβατό με τις εκδόσεις 11.4.0 έως 11.13.0, σε όλες τις περιοχές), τα οποία μπορούν να χρησιμοποιηθούν στη συνέχεια σε συνδυασμό με το universal-otherapp.

## Τι χρειάζεστε

- Την πιο πρόσφατη έκδοση του [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/download/v0.0.7/SafeB9SInstaller-20170605-122940.zip) (απευθείας λήψη)
- Την πιο πρόσφατη έκδοση του [boot9strap](https://github.com/SciresM/boot9strap/releases/download/1.4/boot9strap-1.4.zip) (απευθείας λήψη)
- Την πιο πρόσφατη έκδοση του [Luma3DS](https://github.com/LumaTeam/Luma3DS/releases/latest) (το αρχείο `.zip` του Luma3DS)
- Την πιο πρόσφατη έκδοση του [universal-otherapp](https://github.com/TuxSH/universal-otherapp/releases/latest) (`otherapp.bin`)

## Οδηγίες

### Ενότητα I - Προετοιμασία

Σε αυτήν την ενότητα, θα αντιγράψετε τα αρχεία που απαιτούνται για την ενεργοποίηση τόσο του browserhax όσο και του universal-otherapp.

1. Απενεργοποιήστε την κονσόλα σας
2. Εισαγάγετε την κάρτα SD στον υπολογιστή σας
3. Αντιγράψτε το `otherapp.bin` στη ρίζα της κάρτας SD σας και μετονομάστε το σε `arm11code.bin`
    - Η ρίζα της κάρτας SD είναι ο αρχικός κατάλογος της κάρτας SD σας, όπου μπορείτε να δείτε τον φάκελο «Nintendo 3DS», χωρίς να βρίσκεστε μέσα σε αυτόν
    - Εάν δεν βλέπετε την επέκταση `.bin`, μην την προσθέσετε στο τέλος του ονόματος του αρχείου
4. Αντιγράψτε τα πάντα από το αρχείο `.zip` του Luma3DS στη ρίζα της κάρτας SD σας
5. Δημιουργήστε έναν φάκελο με το όνομα `boot9strap` στη ρίζα της κάρτας SD σας
6. Αντιγράψτε τα `boot9strap.firm` και `boot9strap.firm.sha` από το αρχείο `.zip` του boot9strap στον φάκελο `/boot9strap/` της κάρτας SD σας
7. Αντιγράψτε το `SafeB9SInstaller.bin` από το αρχείο `.zip` του SafeB9SInstaller στη ρίζα της κάρτας SD σας
8. Εισαγάγετε ξανά την κάρτα SD στην κονσόλα σας
9. Ενεργοποιήστε την κονσόλα σας

### Ενότητα II - SSLoth

Σε αυτήν την ενότητα, θα αλλάξετε τις ρυθμίσεις σύνδεσης στο διαδίκτυο για να χρησιμοποιήσετε ένα δίκτυο διακομιστών μεσολάβησης, σχεδιασμένο έτσι, ώστε να παρακάμπτει τον έλεγχο της έκδοσης του προγράμματος περιήγησης, επιτρέποντας τη λειτουργία του χωρίς ενημέρωση του συστήματος. Αυτό θα σας επιτρέψει να αποκτήσετε πρόσβαση στην ιστοσελίδα του exploit στην επόμενη ενότητα.

<!--@include: ./_include/addproxy.md -->

1. Πατήστε «Back» δύο φορές και έπειτα, «Close» για να επιστρέψετε στο μενού «HOME»

### Ενότητα III - Εκκίνηση του SafeB9SInstaller

Σε αυτήν την ενότητα, θα επισκεφτείτε την ιστοσελίδα του exploit, το οποίο θα χρησιμοποιήσει το universal-otherapp για την εκκίνηση του προγράμματος εγκατάστασης του boot9strap (custom firmware).

1. Στο μενού «HOME», πατήστε ταυτόχρονα τα κουμπιά (L) και (R) για να ανοίξετε την κάμερα
    - Εάν δεν μπορείτε να ανοίξετε την κάμερα, ανοίξτε την εφαρμογή «Internet Browser» και πληκτρολογήστε το URL (`https://zoogie.github.io/web/nbhax/`)

2. Πατήστε το κουμπί κωδικού QR και σαρώστε [αυτόν τον κωδικό QR](http://api.qrserver.com/v1/create-qr-code/?color=000000&bgcolor=FFFFF&data=https%3A%2F%2Fzoogie.github.io%2Fweb%2Fnbhax&qzone=1&margin=0&size=400x400&ecc=L)

    - Όταν λάβετε ένα μήνυμα με κωδικό σφάλματος `012-1511`, `032-1809` ή `032-1820`, πατήστε το (A) για να επιτρέψετε τη σύνδεση
    - Εάν προκύψει απρόσμενη διακοπή λειτουργίας ή αν λάβετε άλλο κωδικό σφάλματος, [ακολουθήστε αυτόν τον οδηγό επίλυσης προβλημάτων](troubleshooting-ssloth-browser)

    ::: danger

    Εάν λάβετε ένα μήνυμα που σας προτρέπει να ενημερώσετε την κονσόλα σας, ΣΤΑΜΑΤΗΣΤΕ! Επαναλάβετε τα βήματα της Ενότητας II από την αρχή και βεβαιωθείτε ότι έχετε ρυθμίσει σωστά τον διακομιστή μεσολάβησης.

    :::

3. Πατήστε το κουμπί «PROCEED TO HAXX»

4. Εάν το exploit ήταν επιτυχές, θα έχει γίνει εκκίνηση στο SafeB9SInstaller
    - Εάν λάβετε κάποιο σφάλμα, [ακολουθήστε αυτόν τον οδηγό επίλυσης προβλημάτων](troubleshooting-ssloth-browser)

### Ενότητα IV - Εγκατάσταση του boot9strap

Σε αυτήν την ενότητα, θα εγκαταστήσετε custom firmware στην κονσόλα σας.

1. Όταν ζητηθεί, εισαγάγετε τον συνδυασμό πλήκτρων που θα εμφανιστεί στην πάνω οθόνη, ώστε να εγκαταστήσετε το boot9strap
    - Εάν το κείμενο κάποιου βήματος στην κάτω οθόνη έχει κόκκινο χρώμα και δεν σας ζητείται να εισαγάγετε κάποιον συνδυασμό πλήκτρων, [ακολουθήστε αυτόν τον οδηγό επίλυσης προβλημάτων](troubleshooting-ssloth-browser)
2. Μόλις ολοκληρωθεί, πατήστε το (Α) για να επανεκκινήσετε την κονσόλα σας

<!--@include: ./_include/configure-luma3ds.md -->

### Ενότητα V - Επαναφορά προεπιλεγμένου διακομιστή μεσολάβησης

<!--@include: ./_include/rmproxy.md -->

<!--@include: ./_include/luma3ds-installed-note.md -->

___

::: tip

Συνέχεια στην [Ολοκλήρωση εγκατάστασης](finalizing-setup)

:::
