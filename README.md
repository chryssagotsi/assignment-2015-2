# Το Πρόβλημα των Σταθερών Γάμων

Στο πρόβλημα των σταθερών γάμων αναζητούμε ένα σταθερό ταίριασμα (stable matching) μεταξύ ανδρών και γυναικών, έχοντας ως δεδομένο τις προτιμήσεις κάθε άνδρα και κάθε γυναίκας. Εσείς καλείστε να γράψετε πρόγραμμα στη γλώσσα Python που θα επιλύει το πρόβλημα των σταθερών γάμων για τα δεδομένα, δηλαδή τις προτιμήσεις, που δίνει ο χρήστης. Το πρόγραμμα θα χρησιμοποιεί τον αλγόριθμο Gale-Shapley.

Στην περίπτωσή μας, οι προτιμήσεις αυτές δίνονται μέσω αρχείων τύπου JSON. Τα αρχεία αυτά έχουν τη μορφή:

```
{
  "men_rankings": {
    "abe": ["cat", "bea", "ada"],
    "bob": ["ada", "cat", "bea"],
    "cal": ["ada", "bea", "cat"]
  },

  "women_rankings": {
    "ada": ["abe", "cal", "bob"],
    "bea": ["bob", "abe", "cal"],
    "cat": ["cal", "abe", "bob"]
  }
}
```

Όπως βλέπετε, δίνονται οι προτιμήσεις σε ένα ενιαίο αρχείο, ξεχωριστά για τους άνδρες και τις γυναίκες.

Αφού το πρόγραμμα επεξεργαστεί τη λύση, θα πρέπει να την εμφανίζει στην έξοδο και πάλι στη μορφή JSON. Για παράδειγμα, αν ο χρήστης δώσει την παραπάνω είσοδο το πρόγραμμα θα εμφανίζει έξοδο όπως:

```
{"abe": "cat", "bob": "bea", "cal": "ada"}
```
Προσέξτε ότι τα αποτελέσματα θα εμφανίζονται σε αλφαβητική σειρά ως προς τους άνδρες.

Αν ξεκινάμε την επίλυση του προβλήματος από τη μεριά των ανδρών, η λύση που προκύπτει είναι βέλτιστη για τους άνδρες, όπως η παραπάνω. Αν ξεκινάμε την επίλυση του προβλήματος από τη μεριά των γυναικών, η λύση που προκύπτει είναι βέλτιστη για τις γυναίκες. Στην περίπτωση του παραδείγματός μας, αυτή είναι:

```
{"ada": "abe", "bea": "bob", "cat": "cal"}
```
Προσέξτε ότι τα αποτελέσματα θα εμφανίζονται σε αλφαβητική σειρά ως προς τις γυναίκες.


Το πρόγραμμά σας θα πρέπει να μπορεί να βρει όποια από τις δύο λύσεις ζητηθεί. 

## Απαιτήσεις Προγράμματος

Κάθε φοιτητής θα εργαστεί στο προσωπικό του αποθετήριο στο GitHub. Για να αξιολογηθεί μια εργασία θα πρέπει να πληροί τις παρακάτω προϋποθέσεις:

1. Όλη η εργασία θα πρέπει να βρίσκεται σε έναν κατάλογο `assignment-2015-2` μέσα στο αποθετήριο του φοιτητή.

2. Το πρόγραμμα θα πρέπει να έχει όνομα `stable_marriage.py`.

3. Το πρόγραμμα θα μπορεί να καλείται με τους εξής τρόπους:
  * `python3 stable_marriage.py -m <input_filename>`, οπότε θα εμφανίζει τη λύση που είναι βέλτιστη για τους άνδρες. Το πρόγραμμα παράγει στην έξοδο JSON της μορφής `{ "man": "woman", "another_man": "another_woman", ...}`.
  * `python3 stable_marriage.py -m <input_filename> -o <output_filename>`, οπότε βρίσκει τη λύση που είναι βέλτιστη για τους άνδρες. Τη λύση θα τη σώζει στο πρόγραμμα `output_filename`.
  * `python3 stable_marriage.py -w <input_filename>`, οπότε θα εμφανίζει τη λύση που είναι βέλτιστη για τις γυναίκες. Το πρόγραμμα παράγει στην έξοδο JSON της μορφής `{ "woman": "man", "another_woman": "another_man", ...}`.
  * `python3 stable_marriage.py -w <input_filename> -o <output_filename>`, οπότε βρίσκει τη λύση που είναι βέλτιστη για τις γυναίκες. Τη λύση θα τη σώζει στο πρόγραμμα `output_filename`.

Παραδείγματα αρχείων εισόδου του προγράμματος:

* [example_1.json](example_1.json).
* [example_2.json](example_2.json).
* [example_3.json](example_3.json).

## Μπόνους Βαθμού

Ο αλγόριθμος Gale-Shapley βρίσκει κάθε φορά *ένα* σταθερό ταίριασμα, είτε για τους άνδρες, είτε για τις γυναίκες. Υπάρχουν τρόποι να βρίσκονται *όλα* τα σταθερά ταιριάσματα. Όσοι φοιτητές επιθυμούν να λύσουν και αυτό το πρόβλημα θα έχουν μπόνους βαθμού. Θα πρέπει να επικοινωνήσουν εκ των προτέρων με τον διδάσκοντα για να τους δωθεί το απαραίτητο υλικό που θα τους καθοδηγήσει στην επίλυση.

