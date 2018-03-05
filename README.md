# Τεχνολογία πολυμέσων Εργασία
Αλέξανδρος Μόσχος 03113027

Υλοποίησα την γραφική διεπαφή όπως περιγράφεται 
στην εκφώνηση με τις εξής παραδοχές:

- Στο πάνω μέρος του παραθύρου έβαλα να φαίνονται 4
μεγέθη, ο χρόνος απο την αρχή της εκτέλεσης ο συνολικος αριθμός των
έγκυρων πτήσεων. Ο αριθμος των προσγειώσεων και των ατυχημάτων.
- Στο μεσαίο τμήμα του παραθύρου εκανα εναν χάρτη 30 γραμμών επι 60 στηλών
σύμφωνα με τις προδιαγραφές
- Στο δεξί τμήμα του παραθύρου υπάρχει χώρος για να βγαίνουν
μηνύματα για τα γεγονότα που συμβαίνουν κατα την προσομοίωση.
- Χρησιμοποίησα σε πολύ μικρό βαθμό το UI Designer του IntelliJ αλλα η
μεγαλύτερη λειτουργικότητα της γραφικής διεπαφής έχει υλοποιηθεί απο εμένα

Για την κίνηση των αεροπλάνων έκανα χρήση του αλγορίθμου του
Dijkstra. Η πρώτη και η τελευταία κίνηση που μπορεί να κανει το αεροπλάνο είναι
συγκεκριμένη σύμφωνα με την κατεύθυνση του αεροδιαδρόμου(όπως αναφέρεται στις προδιαγραφές).
Αποθηκεύω για κάθε πτήση ολόκληρο το μονοπάτι σε μια δομή ArrayList<Position>.
Για την κίνηση κάθε αεροπλάνο έχει εναν Timer που σε κατάλληλο χρόνο ανάλογο της ταχύτητας
αλλάζει την θέση του αεροπλάνου. Κάθε φορά που ο Timer αλλάζει την θέση του αεροπλάνου
γίνεται έλεγχος για Crash είτε απο έλλειψη καυσίμων είτε απο πολυ χαμηλό ύψος.
Παράλληλα ενα νήμα μόνιμα ελέγχει σε κάθε γύρο ενα νήμα κάθε ζεύγος 
αεροπλάνων για σύγκρουση μεταξύ τους. 

Για να αποφευχθούν τα race conditions οι μεταβλητές landed και crashed είναι AtomicIntegers
και η συνάρτηση που προσθέτει κείμενο στο δεξια πανελ είναι synchronized.

Στο πάνω μέρος του παραθύρου έχω τοποθετήσει Menu Bar με τις ζητούμενες επιλογές.
Έκανα την παραδοχή ότι ο χρόνος εκτέλεσης θα μετράει απο την αρχή της πρώτης προσομοίωσης
μέχρι τώρα.

Σχετικά με τις αρχές σχεδίασης του αντικειμενοστραφούς προγραμματισμού 
για τις κλάσεις Jet SingleEngine και TurboProp που κληρονομούν την κλάση 
Plane ισχύει η αρχή αντικατάστασης της Liskov. Κάθε κλάση σε γενικές γραμμές 
εξυπηρετεί έναν high level σκοπο για την εφαρμογή.

Κάθε public μέθοδος έχει περιγραφικό όνομα και κατάλληλο σχολιασμό 