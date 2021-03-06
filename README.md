# Sprint-Challenge--Django-II

For this sprint challenge, you'll be exploring some test data in a Django RPG.
Fork this repo, and use it to add your work (`queries.py` described later) to
turn in via a pull request. You will also need to clone the
[Django RPG repo](https://github.com/lambdaschool/django-rpg) but you just have
to run the app and don't need to turn it in (even if you do change it some).

In the RPG, install dependencies from the `Pipfile` using `pipenv`, and set up
the database schema using `./manage.py migrate`. At this point the app should
work, and you can try a few other `./manage.py` commands to verify this.

But you don't have any data yet - there is test data that has been serialized
and saved to a file `testdata.json` at the base of the RPG repo. You can load
this with `./manage.py loaddata testdata.json`, but note that this may conflict
with any existing data so if you made your own earlier you should remove it.

This test data has dozens-to-hundreds of randomly generated characters across
the base classes (Fighter, Mage, Cleric, and Thief) as well as a few
Necromancers. Also generated are Items, Weapons, and connections from characters
to them. Note that, while the name field was randomized, the numeric and boolean
fields were left as defaults.

You should familiarize yourself a bit with these classes and objects - read the
`models.py` files in the `armory/` and `charactercreator/` apps, and interact
with the data using the Django shell (`./manage.py shell`). Use the `dir()` and
`help()` functions to see what fields and methods are accessible. The
[official documentation](https://docs.djangoproject.com/en/2.0/topics/db/queries/)
steps through how to query using the Django ORM, including how to filter and
span relationships (the equivalent of `JOIN` in SQL).

Your main goal is to write Python code that uses the Django ORM to answer:

- How many total Characters are there?
- How many of each specific subclass?
- How many total Items?
- How many of the Items are weapons? How many are not?
- On average, how many Items does each Character have?
- On average, how many Weapons does each character have?

You can experiment/execute your code using the Django shell. Please turn in a
file `queries.py` in this repo with your code along with comments for your
answers.

Stretch goals:

- Answer the same questions using the Django db shell/SQL (turn in `queries.sql`)
- Do queries that filter/group on substrings (e.g. how many item names contain
"quid")
- Add views/templates for a "dashboard" that reports the stats (pulling data
from the database, so it updates if that data changes)
- Using tables or charts, ssummarize answers to the above
- Slice the Items/Weapon distribution by Character subclass
- Play with populating your own test data - this data was generated using
https://github.com/volrath/django-autofixture (this fork is compatible with
Django 2.0 and is installed by the `requirements.txt` in the `testdata` branch,
but you may still need dependencies such as `gdal-bin` (search for how to
install this for your specific platform))

In general, this exercise is meant to test your ability to navigate and
investigate data in a Django application. If you get to the stretch goal of
using autofixture, the practical application here is testing - you can have
tests that generate unique random data each time, ensuring the robustness of
your application.
