How to generate these files
===========================

Make sure you enable the autostuff as an available module when answering
the questions:
```shell
$ sphinx-quickstart
$ sphinx-apidoc  . -o doc -f
$ cd doc/
$ export PYTHONPATH=.:..:$PYTHONPATH
$ make clean
$ make html
$ cd _build/html
$ zip -r api.zip *
$ cp api.zip /what/ever
```

In case of problems, check your PYTHONPATH which give Sphinx access to
the modules. Also check the `conf.py` for the extension:
```
extensions = ['sphinx.ext.autodoc', 'sphinx.ext.viewcode']
```

`__init__` methods are not documented by default, so you may have to
customize the `conf.py`.
