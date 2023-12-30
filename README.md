# Post Application

1) Περιγραφή της εφαρμογής

-Με την συσγκεκρημένη εφαρμογή οι διάφοροι χρήστες αφού έχουν πρώτα κάνει εγγραφή στην βάση δεδομένων του προγράμματος και στην συνέχεια έχουν κάνει και
 επιτυχημένο login μπορούν να καταχωρούν οποιοδήποτε post με ένα μοναδικό τίτλο ανά χρήστη κάθε φορά και να το μοιράζονται μεταξύ τους. Δηλαδή μπορούν στον
 μοναδικό αυτό τίτλο να προσθέσουν ελεύθερο κείμενο καθώς και εικόνα (με την μορφή διευθύνσεως url). Ο χρήστης έχει την δυνατότητα να βλέπει σε λίστα μόνο τα δικά του
 posts τα οποία μπορεί και να τα επεξεργαστεί άμεσα αλλά και μια μαζική λίστα με τα posts από όλους τους χρήστες. Η ιδέα της εφαρμογής είναι να λειτουργεί ως ένα είδος
 ενημερωτικού site.

-Επίσης μπορεί να κάνει και διάφορες ενέργειες που αφορούν το προφίλ του, όπως ενημέρωση στοιχείων, αλλαγή password κοκ.

-Τέλος όλοι οι χρήστες που δημιουργούνται είναι απλοί χρήστες (όχι admin). Αυτό σημαίνει πρακτικά ότι μπορούν:
  - επεξεργασία μόνο του profile του (delete και update).
  - Προβολή μόνο του profile του.
  - Επεξεργασία μόνο των δικών του posts (delete και update).
  - Προβολή όλων των posts

 Ο μοναδικός admin χρήστης δημιουργείται κατά την εκτέλεση της εφαρμογής όπως θα δούμε στην συνέχεια και είναι αυτός που έχει περισσότερες δυνατότητες, όπως:
  - επεξεργασία των profile χρηστών (delete και update).
  - Προβολή των profile όλων των χρηστών.
  - διαγραφή των posts όλων των χρηστών.
  - Προβολή όλων των posts.

 2) Τεχνικές Προδιαγραφές
 
 # BackEnd

 -Για να μπορέσουμε να εγκαταστήσουμε και να 'τρέξουμε' την εφαρμογή μας όσο αφορά το backend θα πρέπει να γίνουν τα εξής:

 2.1) Η εφαρμογή λειτουργεί και τρέχει μέσω docker. Οπότε έχοντας εγκαταστήσει το docker desktop (windows λειτουργικό) ακολουθούμε τα παρακάτω:

   Η πόρτα στην οποία τρέχει το backend είναι στην 3001. Φροντίζουμε ώστε να μην τρέχει κάποιο άλλο service σε αυτήν την πόρτα. Στην συνέχεια στον φάκελο του backend αντιγράφουμε το .env αρχείο και το mongo-init.js έτσι ώστε κατά την εκτέλεση του να δημιουργηθεί αυτόματα η βάση (postDb) και ο admin χρήστης με όλα τα δικαιώματα για την βάση μας. Η βάση δεδομένων είναι σε mongo και η πόρτα στην οποία 'τρέχει' είναι 27017:27017 με τους κωδικούς του χρήστη να είναι στο .env αρχεία. Άρα έχουμε:
   -localhost:27017
   -Authentication Mode: Legacy(SCRAM-SHA-1)
   -admin
   -password (από .env αρχείο)
   -Authentication DB: postDb

   Γνωρίζοντας αυτά σε ένα terminal εκτελούμε τις εντολές με την σειρά:
   a) npm install (ώστε να εγκατασταθούν όλα τα απαραίτητα dependencies)
   b) docker-compose up-d (ώστε να τρέξουμε το docker)
   c) npm run start:dev (ώστε να τρέξουμε το backend και επίσης σε κάθε αλλαγή να εκτελείτε ξανά αυτόματα)



 # FrontEnd

 -Για να μπορέσουμε να 'τρέξουμε' την εφαρμογή μας όσο αφορά το frontend θα πρέπει να γίνουν τα εξής:

 2.2) Η πόρτα στην οποία τρέχει το frontend είναι στην http://localhost:4200/

  Γνωρίζοντας αυτά σε ένα terminal εκτελούμε τις εντολές με την σειρά:
  a) npm install (ώστε να εγκατασταθούν όλα τα απαραίτητα dependencies)
  b) npm start (ώστε να τρέξουμε το frontend και επίσης σε κάθε αλλαγή να εκτελείτε ξανά αυτόματα)




 
