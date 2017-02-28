# Ανεβάστε!

> **Σημείωση** Το ακόλουθο κεφάλαιο μπορεί να είναι μερικές φορές λίγο δύσκολο να ολοκληρωθεί. Επιμένετε και τελειώστε το, το ανέβασμα είναι ένα σημαντικό μέρος της διαδικασίας ανάπτυξης της ιστοσελίδας. Το κεφάλαιο αυτό τοποθετείται στη μέση του εκπαιδευτικού εγγράφου, έτσι ώστε να μέντορας σας να μπορεί να σας βοηθήσει με την ελαφρώς πιο περίπλοκη διαδικασία "ανεβάσματος" της ιστοσελίδας στο διαδίκτυο. Αυτό σημαίνει ότι μπορείτε να ολοκληρώσετε την εκπαίδευση μόνοι σας ακόμα και αν σας τελειώσει ο χρόνος.

Μέχρι τώρα σας ιστοσελίδα ήταν διαθέσιμη μόνο στον υπολογιστή σας, τώρα θα μάθετε πώς να την ανεβάσετε στο διαδίκτυο! "Ανεβάζω στο διαδίκτυο" είναι η διαδικασία της δημοσίευσης την εφαρμογής σας στο διαδίκτυο, έτσι ώστε οι άνθρωποι τελικά να πάνε και να δουν την εφαρμογή σας :) .

Όπως μάθατε, μια ιστοσελίδα πρέπει να βρίσκεται σε ένα διακομιστή. Υπάρχουν πολλοί πάροχοι διακομιστή που είναι διαθέσιμοι στο διαδίκτυο. Θα χρησιμοποιήσουμε έναν που έχει μια σχετικά απλή διαδικασία ανεβάσματος: τον [PythonAnywhere][1]. Ο PythonAnywhere είναι δωρεάν για μικρές εφαρμογές που δεν έχουν πάρα πολλούς επισκέπτες, οπότε σίγουρα θα είναι αρκετό για σας τώρα.

 [1]: http://pythonanywhere.com/

Η άλλη εξωτερική υπηρεσία που θα χρησιμοποιήσουμε είναι το [GitHub][2], το οποίο είναι μια υπηρεσία φιλοξενίας κώδικα. Υπάρχουν και άλλοι διαθέσιμοι έξω, αλλά σχεδόν όλοι οι προγραμματιστές έχουν λογαριασμό GitHub αυτές τις μέρες, και έτσι και εσείς θα έχετε τώρα!

 [2]: http://www.github.com

Θα χρησιμοποιήσουμε το GitHub ως σκαλοπάτι για τη μεταφορά μας κώδικα και προς το PythonAnywhere.

# Git

Το Git είναι ένα «σύστημα ελέγχου έκδοσης» και χρησιμοποιείται από πολλούς προγραμματιστές. Αυτό το λογισμικό μπορεί να παρακολουθήσει τις αλλαγές στα αρχεία με την πάροδο του χρόνου έτσι ώστε να μπορείτε να ανακαλέσετε συγκεκριμένες εκδόσεις σε μεταγενέστερο στάδιο. Είναι κάτι σαν την δυνατότητα "παρακολούθησης αλλαγών" στο Microsoft Word, αλλά πολύ πιο ισχυρό.

## Εγκαθιστώντας το Git

> **Σημείωση** Αν κάνατε ήδη τα βήματα εγκατάστασης, δεν χρειάζεται να το επαναλάβετε - μπορείτε να μεταβείτε στην επόμενη ενότητα και να ξεκινήστε δημιουργώντας το αρχείο αποθήκευσης του Git.

{% include "deploy/install_git.md" %}

## Ξεκινώντας το αρχείο αποθήκευσής μας του Git

Το Git παρακολουθεί τις αλλαγές σε ένα συγκεκριμένο σύνολο αρχείων που αποκαλείται αρχείο αποθήκευσης κώδικα (ή «ρεπό» εν συντομία). Ας ξεκινήσουμε ένα για την εφαρμογή μας. Ανοίξτε την κονσόλα σας και να εκτελέσετε αυτές τις εντολές, στον φάκελο`djangogirls`:

> **Σημείωση** Ελέγξτε τον τρέχοντα κατάλογό εργασίας σας με την εντολή `cd` (Windows) ή `pwd` (OSX/Linux) πριν από την προετοιμασία του φακέλου αποθήκευσης. Θα πρέπει να βρίσκεστε στο φάκελο `djangogirls`.

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Το όνομά σας"
    $ git config --global user.email you@example.com
    

Η αρχικοποίηση του αρχείου αποθήκευσης του git είναι κάτι που πρέπει να κάνουμε μόνο μία φορά ανά πρόγραμμα (και δεν θα πρέπει να πληκτρολογήσετε ξανά το όνομα χρήστη και το e-mail ποτέ).

Το Git θα παρακολουθείσει τις αλλαγές σε όλα τα αρχεία και τους φακέλους σε αυτόν τον κατάλογο, ωστόσο υπάρχουν ορισμένα αρχεία που θέλουμε να τα αγνοήσει. Το κάνουμε αυτό δημιουργώντας ένα αρχείο που ονομάζεται `.gitignore` στον αρχικό κατάλογο. Ανοίξτε το πρόγραμμα επεξεργασίας κειμένου και δημιουργήστε ένα νέο αρχείο με το ακόλουθο περιεχόμενο:

    *.pyc
    __pycache__
    myvenv
    db.sqlite3
    .DS_Store
    

Και αποθηκεύστε το ως `.gitignore` στον αρχικό φάκελο "djangogirls".

> **Σημείωση** Η τελεία στην αρχή του ονόματος του αρχείου είναι σημαντική! Εάν αντιμετωπίζετε οποιαδήποτε δυσκολία κατά τη δημιουργία του (Στα λειτουργικά Macs δεν αρέσει να δημιουργούνται αρχεία που αρχίζουν με τελεία μέσω του Finder, για παράδειγμα), τότε χρησιμοποιήστε τη δυνατότητα "Αποθήκευση ως" στο πρόγραμμα επεξεργασίας κειμένου, έχει σίγουρα αποτελέσματα.

Είναι καλή ιδέα να χρησιμοποιήσετε την εντολή `git status` πριν από την εντολή`git add` ή όποτε δεν είστε βέβαιοι για το τι έχει αλλάξει. Αυτό θα αποτρέψει οποιεσδήποτε εκπλήξεις από να συμβούν, όπως λάθος αρχεία που προστίθενται ή οριστικά αποθηκεύονται. Η εντολή `git status` επιστρέφει πληροφορίες σχετικά με οποιαδήποτε αρχεία ανεξακρίβωτα/τροποποιημένα/διαβαθμιζόμενα, διακλαδωμένη κατάσταση και πολλά άλλα. Το αποτέλεσμα πρέπει να είναι παρόμοιο με:

    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    
            .gitignore
            blog/
            manage.py
            mysite/
    
    nothing added to commit but untracked files present (use "git add" to track)
    

Και τέλος σώζουμε τις αλλαγές μας. Πηγαίνετε στην κονσόλα σας και να εκτελέσετε αυτές τις εντολές:

    $ git add -A .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## Προωθώντας το κώδικά μας στο GitHub

Επισκεφθείτε την ιστοσελίδα [GitHub.com][2] και κάντε δωρεάν εγγραφή για έναν νέο λογαριασμό χρήστη. (Αν το έχετε ήδη κάνει στο προπαρασκευαστικό εργαστήριο, αυτό είναι υπέροχο!)

Στη συνέχεια, δημιουργήστε ένα νέο αρχείο αποθήκευσης κώδικα, δίνοντας του το όνομα "my-first-blog". Μην κάνετε κλικ στο κουτί επιλογής "initialise with a README", αφήστε την επιλογή .gitignore κενή (το έχουμε κάνει μόνοι μας) και αφήστε την άδεια χρήστης ως "None".

![][3]

 [3]: images/new_github_repo.png

> **Σημείωση** Το όνομα `my-first-blog` είναι σημαντικό -- θα μπορούσατε να επιλέξετε κάτι άλλο, αλλά πρόκειται να το συναντήσουμε πολλές φορές στις παρακάτω οδηγίες και θα πρέπει να το κάνετε αντικατάσταση κάθε φορά. Είναι πιθανώς ευκολότερο να κρατήσετε το όνομα `my-first-blog`.

Στην επόμενη οθόνη, θα εμφανιστεί ο κλώνος του αρχείου αποθήκευσής σας ως διεύθυνση URL. Επιλέξτε την έκδοση "HTTPS", αντιγράψτε το, και θα το επικολλήσετε στο τερματικό σύντομα:

![][4]

 [4]: images/github_get_repo_url_screenshot.png

Τώρα πρέπει να συνδέσετε το αρχείο αποθήκευσης κώδικα που βρίσκεται στο Git του υπολογιστή σας με το αντίστοιχο που βρίσκεται αποθηκευμένο στο GitHub.

Πληκτρολογήστε τα ακόλουθα στην κονσόλα σας (αντικαταστήστε `< your-github-username >` με το όνομα χρήστη που δηλώσατε κατά τη δημιουργία του λογαριασμού σας στο GitHub, αλλά χωρίς τις αγκύλες ):

    $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
    $ git push -u origin master
    

Εισάγετε στο GitHub το όνομα χρήστη και τον κωδικό πρόσβασης και θα πρέπει να δείτε κάτι σαν και αυτό:

    Username for 'https://github.com': hjwp
    Password for 'https://hjwp@github.com':
    Counting objects: 6, done.
    Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/hjwp/my-first-blog.git
     * [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    

<!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extention -->

Ο κώδικάς σας βρίσκεται τώρα στο GitHub. Πηγαίνετε και τσεκάρετέ το! Θα ανακαλύψετε πως μέσα εκεί βρίσκεται η εταιρία - [Django][5], το [Django Girls Tutorial][6] και άλλες πολλές εφαρμογές ανοικτού λογισμικού που επίσης φιλοξενούν τον κώδικά τους στο GitHub :)

 [5]: https://github.com/django/django
 [6]: https://github.com/DjangoGirls/tutorial

# Εγκαθιστώντας το blog μας στο PythonAnywhere

> **Σημείωση** Μπορεί να έχετε ήδη δημιουργήσει ένα λογαριασμό στο PythonAnywhere νωρίτερα κατά τη διάρκεια των βημάτων εγκατάστασης - Εάν ναι, δεν χρειάζεται να το κάνετε ξανά.

{% include "deploy/signup_pythonanywhere.md" %}

## "Τραβώντας" τον κώδικά μας στο PythonAnywhere

Όταν εγγραφείτε στο PythonAnywhere, θα οδηγηθείτε στο ταμπλό σας ή στη σελίδα "Consoles". Κάντε χρήση της επιλογής να ξεκινήσετε μια κονσόλα "Bash" -- η οποία είναι η PythonAnywhere έκδοση της κονσόλας, ακριβώς όπως αυτή στον υπολογιστή σας.

> **Σημείωση** Το PythonAnywhere βασίζεται σε Linux, έτσι εάν είστε στα Windows, η κονσόλα θα φαίνεται λίγο διαφορετική από εκείνη στον υπολογιστή σας.

Ας τραβήξουμε μας κώδικά μας από το GitHub στο PythonAnywhere, δημιουργώντας έναν «κλώνο» του αρχείου αποθήκευσής μας. Πληκτρολογήστε τα παρακάτω στην κονσόλα PythonAnywhere (μην ξεχάσετε να χρησιμοποιήσετε το όνομα χρήστη που έχετε στο GitHub στη θέση του `< your-github-username >`):

    $ git clone https://github.com/<your-github-username>/my-first-blog.git
    

Αυτό θα σε τραβήξει ένα αντίγραφο του κώδικά σας στο PythonAnywhere. Τσεκάρετέ το, πληκτρολογώντας `tree my-first-blog`:

    $ tree my-first-blog
    my-first-blog/
    ├── blog
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── migrations
    │   │   ├── 0001_initial.py
    │   │   └── __init__.py
    │   ├── models.py
    │   ├── tests.py
    │   └── views.py
    ├── manage.py
    └── mysite
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
    

### Δημιουργώντας ένα εικονικό περιβάλλον - virtualenv - στο PythonAnywhere

Όπως ακριβώς κάνατε στον υπολογιστή σας, μπορείτε να δημιουργήσετε ένα εικονικό περιβάλλον στο PythonAnywhere. Στην κονσόλα Bash, πληκτρολογήστε:

    $ cd my-first-blog
    
    $ virtualenv --python=python3.4 myvenv
    Running virtualenv with interpreter /usr/bin/python3.4
    [...]
    Installing setuptools, pip...done.
    
    $ source myvenv/bin/activate
    
    (mvenv) $  pip install django whitenoise
    Collecting django
    [...]
    Successfully installed django-1.8.2 whitenoise-2.0
    

> **Σημείωση** Το `pip install` βήμα μπορεί να διαρκέσει μερικά λεπτά. Υπομονή, υπομονή! Αλλά αν διαρκέσει περισσότερο από 5 λεπτά, κάτι δεν πάει καλά. Ρωτήστε τον εκπαιδευτή σας.

<!--TODO: think about using requirements.txt instead of pip install.-->

### Συλλέγοντας στατικά αρχεία.

Αναρωτιόσασταν τι ήταν ακριβώς το "whitenoise"; Είναι ένα εργαλείο για την εξυπηρέτηση των λεγόμενων «στατικών αρχείων". Τα στατικά αρχεία είναι αυτά που δεν αλλάζουν συχνά ή δεν τρέχουν κώδικα προγραμματισμού, όπως είναι τα αρχεία HTML ή CSS. Λειτουργούν διαφορετικά σε διακομιστές σε σύγκριση με το δικό μας υπολογιστή και χρειαζόμαστε ένα εργαλείο όπως το "whitenoise" για να τα εξυπηρετούν.

Θα μάθουμε λίγο περισσότερα για τα στατικά αρχεία αργότερα στο εγχειρίδιο, όταν θα επεξεργαστούμε το CSS για την ιστοσελίδα μας.

Για την ώρα απλά πρέπει να εκτελέσουμε μία επιπλέον εντολή που ονομάζεται `collectstatic`, στο διακομιστή. Λέει στο Django να συγκεντρώσει όλα τα στατικά αρχεία που χρειάζεται στο διακομιστή. Για την ώρα αυτά είναι ως επί το πλείστον αρχεία που κάνουν την admin ιστοσελίδα να φαίνεται όμορφη.

    (mvenv) $ python manage.py collectstatic
    
    You have requested to collect static files at the destination
    location as specified in your settings:
    
        /home/edith/my-first-blog/static
    
    This will overwrite existing files!
    Are you sure you want to do this?
    
    Type 'yes' to continue, or 'no' to cancel: yes
    

Πληκτρολογήστε «Ναι», και ξεκινά! Δεν σας αρέσει να κάνετε τους υπολογιστές να εκτυπώνουν σελίδες και σελίδες αδιαπέραστου κειμένου; Εγώ πάντα κάνω μικρούς ήχους να το συνοδεύουν. BRP, brp brp...

    Copying '/home/edith/my-first-blog/mvenv/lib/python3.4/site-packages/django/contrib/admin/static/admin/js/actions.min.js'
    Copying '/home/edith/my-first-blog/mvenv/lib/python3.4/site-packages/django/contrib/admin/static/admin/js/inlines.min.js'
    [...]
    Copying '/home/edith/my-first-blog/mvenv/lib/python3.4/site-packages/django/contrib/admin/static/admin/css/changelists.css'
    Copying '/home/edith/my-first-blog/mvenv/lib/python3.4/site-packages/django/contrib/admin/static/admin/css/base.css'
    62 static files copied to '/home/edith/my-first-blog/static'.
    

### Δημιουργώντας τη βάσης δεδομένων στο PythonAnywhere

Υπάρχει και ένα άλλο στοιχείο που είναι διαφορετικό μεταξύ του δικού σας υπολογιστή και του διακομιστή: χρησιμοποιεί μια διαφορετική βάση δεδομένων. Έτσι οι λογαριασμοί χρηστών και οι αναρτήσεις μπορεί να είναι διαφορετικές στο διακομιστή και στον υπολογιστή σας.

Μπορούμε να αρχικοποιήσουμε τη βάση δεδομένων στο διακομιστή όπως ακριβώς κάναμε στον υπολογιστή σας, με τις εντολές `migrate` και `createsuperuser`:

    (mvenv) $ python manage.py migrate
    Operations to perform:
    [...]
      Applying sessions.0001_initial... OK
    

## Δημοσίευση του blog μας ως μία εφαρμογή διαδικτύου

Τώρα ο κώδικάς μας είναι στο PythonAnywhere, το εικονικό περιβάλλον μας είναι έτοιμο, τα στατικά αρχεία έχουν συλλεχθεί και η βάση δεδομένων έχει αρχικοποιηθεί. Είμαστε έτοιμοι να το δημοσιεύσουμε ως μία εφαρμογή διαδικτύου!

Κάντε κλικ πίσω στον πίνακα εργαλείων του PythonAnywhere επιλέγοντας το λογότυπό του και στη συνέχεια κάντε κλικ στην καρτέλα **Web**. Τέλος, πατήστε **Add a new web app**.

Αφού επιβεβαιώσετε το όνομα του τομέα σας, επιλέξτε **manual configuration** (*όχι* την επιλογή «Django») στο παράθυρο διαλόγου. Στη συνέχεια επιλέξτε **Python 3.4** και κάντε κλικ στο κουμπί Next για να ολοκληρώσετε τον οδηγό.

> **Σημείωση** Βεβαιωθείτε ότι έχετε επιλέξει "Manual configuration", και όχι την επιλογή "Django". Είμαστε πάρα πολύ άνετοι για το προεπιλεγμένο πρόγραμμα εγκατάστασης PythonAnywhere Django ;-)

### Ρύθμιση του virtualenv

Θα οδηγηθείτε στην οθόνη ρυθμίσεων του PythonAnywhere για την εφαρμογή σας, όπου θα πρέπει να πάτε κάθε φορά που θέλετε να κάνετε αλλαγές στην εφαρμογή σας στο διακομιστή.

![][7]

 [7]: images/pythonanywhere_web_tab_virtualenv.png

Στην περιοχή "Virtualenv", κάντε κλικ στο κόκκινο κείμενο που λέει "Enter the path to a virtualenv" και πληκτρολογήστε: `/home/<your-username>/my-first-blog/myvenv/`. Κάντε κλικ στο μπλε πλαίσιο με το σημάδι τσεκαρίσματος για να αποθηκεύσετε τη διαδρομή πριν προχωρήσουμε.

> **Σημείωση** Αντικαταστήστε το δικό σας όνομα χρήστη ανάλογα με την περίπτωση. Εάν κάνετε κάποιο λάθος, το PythonAnywhere θα σας εμφανίσει μια μικρή προειδοποίηση.

### Ρυθμίζοντας το αρχείο WSGI

Το Django λειτουργεί χρησιμοποιώντας το «πρωτόκολλο WSGI», ένα πρότυπο για την εξυπηρέτηση ιστοσελίδων που χρησιμοποιούν την Python, η οποία υποστηρίζεται από το PythonAnywhere. Ο τρόπος που εμείς ρυθμίζουμε το PythonAnywhere να αναγνωρίζει το Django blog μας είναι τροποποιώντας ένα αρχείο ρύθμισης παραμέτρων WSGI.

Κάντε κλικ στο σύνδεσμο "WSGI configuration file" (στην περιοχή «Code», κοντά στην κορυφή της σελίδας -- η ονομασία θα μοιάζει σαν `/var/www/<your-username>_pythonanywhere_com_wsgi.py`) και θα οδηγηθείτε σε ένα πρόγραμμα επεξεργασίας κειμένου.

Διαγράψτε όλα τα περιεχόμενα και κάντε αντικατάσταση με κάτι σαν αυτό:

    python
    import os
    import sys
    
    path = '/home/<your-username>/my-first-blog'  # use your own username here
    if path not in sys.path:
        sys.path.append(path)
    
    os.environ['DJANGO_SETTINGS_MODULE'] = 'mysite.settings'
    
    from django.core.wsgi import get_wsgi_application
    from whitenoise.django import DjangoWhiteNoise
    application = DjangoWhiteNoise(get_wsgi_application())
    

> **Σημείωση** Μην ξεχάσετε να αντικαταστήσετε το δικό σας όνομα χρήστη όπου λέει `< your-username >`

Η δουλειά αυτού του αρχείου είναι να πει στο PythonAnywhere που ζει η εφαρμογή μας και πως ονομάζεται το αρχείο ρυθμίσεων του Django. Επίσης ρυθμίζει το εργαλείο "whitenoise" που αφορά τα στατικά αρχεία.

Πατήστε **Save** και στη συνέχεια, επιστρέψτε στην καρτέλα **Web**.

Είμαστε καθ'όλα έτοιμοι! Κλικάρετε το μεγάλο πράσινο κουμπί **Reload** και θα είστε σε θέση να δείτε την εφαρμογή σας. Θα βρείτε έναν σύνδεσμο σε αυτό στην κορυφή της σελίδας.

## Συμβουλές για τον εντοπισμό σφαλμάτων

Εάν εμφανιστεί ένα σφάλμα κατά την προσπάθειά σας να επισκεφθείτε την ιστοσελίδα σας, το πρώτο μέρος για να ψάξετε ορισμένες πληροφορίες εντοπισμού σφαλμάτων είναι στο αρχείο **error log**. Θα βρείτε ένα σύνδεσμο προς αυτό στην καρτέλα [Web][8] του PythonAnywhere. Δείτε εάν υπάρχουν κάποια μηνύματα σφάλματος εκεί. Τα πλέον συχνά εμφανίζονται στο κάτω μέρος. Τα πιο συνηθισμένα προβλήματα περιλαμβάνουν:

 [8]: https://www.pythonanywhere.com/web_app_setup/

*   Παράλειψη ενός από τα βήματα που κάναμε στην κονσόλα: τη δημιουργία του virtualenv, την ενεργοποίησή του, την εγκατάσταση του Django σε αυτό, την εκτέλεση της εντολής collectstatic, τη μετεγκατάσταση της βάσης δεδομένων.

*   Κάποιο λάθος στη διαδρομή προς το virtualenv στην καρτέλα Web -- συνήθως εκεί θα βρίσκεται ένα μικρό κόκκινου χρώματος μήνυμα σφάλματος, αν υπάρχει πρόβλημα.

*   Κάποιο λάθος στο αρχείο ρύθμισης παραμέτρων WSGI -- πήρατε σωστά τη διαδρομή προς το φάκελο my-first-blog;

*   Πήρατε την ίδια έκδοση της Python για το virtualenv, όπως κάνατε για την εφαρμογή διαδικτύου; Και οι δύο θα πρέπει να είναι 3.4.

*   Υπάρχουν μερικές γενικές συμβουλές εντοπισμού σφαλμάτων στο σύνδεσμο [ general debugging tips ][9] του PythonAnywhere wiki.

 [9]: https://www.pythonanywhere.com/wiki/DebuggingImportError

Και να θυμάστε, ο εκπαιδευτής σας είναι εδώ να βοηθήσει!

# Είστε συνδεδεμένοι!

Η προεπιλεγμένη σελίδα για τον ιστότοπό σας, πρέπει να λέει «Welcome to Django», ακριβώς όπως συμβαίνει στον τοπικό υπολογιστή σας. Δοκιμάστε να προσθέσετε το `/admin/` στο τέλος του URL, και θα μεταφερθείτε στην ιστοσελίδα διαχείρισης. Συνδεθείτε με το όνομα χρήστη και τον κωδικό πρόσβασης, και θα δείτε ότι μπορείτε να προσθέσετε νέες αναρτήσεις στο διακομιστή.

Δώστε στον εαυτό σας ένα *ΜΕΓΑΛΟ* ελαφρύ χτύπημα στην πλάτη! Η εγκατάσταση σε έναν διακομιστή είναι ένα από τα πιο πολύπλοκα κομμάτια της ανάπτυξης εφαρμογών διαδικτύου και παίρνει συχνά αρκετές ημέρες στους ανθρώπους προτού να τις κάνουν λειτουργικές. Αλλά έχετε την ιστοσελίδα σας ζωντανή, στο πραγματικό Διαδίκτυο, ακριβώς όπως αυτό!