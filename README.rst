=================
setuptools-parcels
=================

An alternative syntaxt to setuptools package_data argument.

Improvements over package_data include:

* simple way to include all non-python files found in packages

.. warn::

   An alternative way to work around specifying package_data is to
   specify the files you would like in distutil's MANIFEST.in, and use the
   include_package_data argument:

   http://setuptools.readthedocs.io/en/latest/setuptools.html#including-data-files

   If your goal is to include whatever MANIFEST.in specifies into the
   installed package, this alternative will work fine.

-----
Usage
-----

You can use setuptools-parcels by including it in your setup.py, as an
additional argument to setup`s setup_requires function, and an
additional parcels parameter:

.. code:: python

    setup(...
          # add it here
          setup_reqires=["setuptools-parcels", "vcver"],
          parcels={}
    )

Without any configuration, parcels will search through all packages,
find any non-python files, and include those.

If the package_data is present, parcels will merge it's additions with
the existing values.
