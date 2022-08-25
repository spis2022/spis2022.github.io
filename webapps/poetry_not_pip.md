# For repl.it, use `poetry`, not `pip`

If you are trying to incorporate some third party library into your project, sometimes the instructions will say to use

```
pip install xyz 
```

For example these instructions: [https://bootstrap-flask.readthedocs.io/en/stable/basic/](https://bootstrap-flask.readthedocs.io/en/stable/basic/)
which specify to do

```
pip install bootstrap-flask
```

But if you are using repl.it, **don't do that**.

* `pip` is a Python package manager
* But repl.it doesn't use `pip`.  
* repl.it uses a different package manager called `poetry`.


So, instead of `pip install foo` use:

(this all goes in the Shell window):

```
python3 -m poetry add foo
python3  -m poetry lock
python3 -m poetry install
```

