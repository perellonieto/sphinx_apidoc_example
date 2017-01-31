# sphinx_apidoc_example
A really simple example of using the sphinx-apidoc

To try this example just clone the package

```sh
git clone git@github.com:perellonieto/sphinx_apidoc_example.git
```

And then go into the created folder

```sh
cd sphinx_apidoc_example
```

And follow the next steps.

In order to create the documentation first it is necessary to generate all the
configuration files. The easiest way is just to run the following script.

```sh
sphinx-apidoc -o docs -E -H PackageName -A "Author Name" -V 0.1 -f -F package/
```

where

- **-o** Directory to place the output files.
- **-E** Put each module file in its own page.
- **-H** Project name to put into the configuration.
- **-A** Author name(s) to put into the configuration.
- **-V** Project version.
- **-f** Usually, apidoc does not overwrite files, unless this option is given.
- **-F** If given, a full Sphinx project is generated using sphinx-quickstart.

Then you need to modify the file _docs/conf.py_ by adding the path to the root
folder with the package.

```python
import os
import sys
sys.path.insert(0, os.path.abspath('../'))
```

Now it is possible to generate the documentation by going to the docs folder
and running the sphinx code. The easiest way is

```sh
cd docs
make html
```

It will generate an index.html in _docs/\_build/index.html_ and it should look somethink similar to this [index.html](https://htmlpreview.github.io/?https://github.com/perellonieto/sphinx_apidoc_example/blob/master/docs/_build/html/index.html)
