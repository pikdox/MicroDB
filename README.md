MicroDB
=======

MicroDB is a simple, lightweight database implementation in Python. It allows you to save and retrieve key-value pairs from a JSON file stored on disk.

Usage
-----

### Instalation

To install MicroDB, you can clone the repository and add it as a submodule to your project by running the following command in your project directory:

```bash
    git add submodule https://github.com/kleber-code/MicroDB
```

### Instantiation

To create a new MicroDB instance, simply call its constructor with the desired database name and directory path (optional, default is './'). If the database file does not exist yet, it will be created.

```python
    from MicroDB import MicroDB
    
    db = MicroDB('my_database')
```

### Saving and loading

To save the current state of the database to disk, call the `save()` method.

```python
    db.save()
```

To load the database from disk, call the `load()` method.

```python
    db.load()
```

### Getting, setting, and removing values

To retrieve a value from the database, call the `get(key)` method with the desired key.

```python
    value = db.get('my_key')
```

To set a value in the database, call the `set(key, value)` method with the desired key and value.

```python
    db.set('my_key', 'my_value')
```           

To remove a value from the database, call the `rem(key)` method with the desired key.

```python
    db.rem('my_key')
```          
#### Real World examples

```python
    db = MicroDB('huge_db')

    db.set('users:alice:like','python')
    _ = db.get('users:alice:like')
    
    print(_)
```

```python
    db = MicroDB('users_db','./databases/')

    db.set('alex:email','alex@user.com')
    _ = db.get('alex:email')
    print(_)
    
    db.set('9213:email','nice.email@very.good')
    _ = db.get('9213:email')
    print(_)
```
Attributes
----------

The following attributes are available on a MicroDB instance:

*   `_db_dir`: the directory where the database file is stored.
*   `_db_name`: the name of the database.
*   `_data`: a dictionary containing the key-value pairs in the database.

License
-------

This project is licensed under the terms of the GPL-3.0 license. See the [LICENSE](LICENSE) file for details.

Author
------

This project was created by Kleber Lucas de Santana Costa (pikdox on GitHub). You can contact him at kleber.code@gmail.com.

