# Our Short  URL
`pipenv shell` <br>
`pipenv install -r requirements.txt`

For our database, we have used SQLite, so to create this database:
```Python

#in settings.py
Replace this:
SQLALCHEMY_DATABASE_URI = os.environ.get('DATABASE_URL')

With this:
SQLALCHEMY_DATABASE_URI = 'sqlite:///db.sqlite3'
```
Next, in the terminal, enter python:<br>
`>>> from url_shortner import create_app`<br>
`>>> from url_shortner.extensions import db`<br>
`>>> from url_shortner.models import Link`<br>
`>>> db.create.all(app=create_app())`<br>
`>>> exit()`<br>



This creates a db.sqlite3 file in the folder. To check if you've been successful, in the terminal, follow these commands:<br>
`sqlite3 url_shortner/db.sqlite3`

`sqlite> .tables`<br>
This should show you a table: link <br>
`.exit`

Now that the database exits, go back to settings.py and change:
```Python

#in settings.py
SQLALCHEMY_DATABASE_URI = 'sqlite:///db.sqlite3'

back to its original code:

SQLALCHEMY_DATABASE_URI = os.environ.get('DATABASE_URL')

```

You can now run `flask run` command and open `localhost:5000` to enjoy our website!




