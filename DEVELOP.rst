Development
===========

If you are looking to get involved improving ``ninvoice2data``, this
guide will help you get started quickly.

Install
-------

1. Fork main repository (optional)
2. Clone repository: ``git clone https://github.com/m3nu/ninvoice2data``
3. Install as editable: ``pip install -e ninvoice2data``

Some little-used dependencies are optional. Like ``pytesseract`` and
``pdfminer``. Install if needed.

Organization
------------

Major folders in the ``ninvoice2data`` package and their purpose:

-  ``input``: Has modules for extracting plain text from files.
   Currently mostly PDF files.
-  ``extract``: Get useful data from plain text using templates. The
   main class – ``BaseInvoiceTemplate`` – is in ``base_template``. Other
   classes can add extra functions and inherit from it. E.g.
   ``LineInvoiceTemplate`` adds support for getting individual items.
-  ``extract/templates``: Keeps all supported template files. Add new
   templates here.
-  ``output``: Modules to output structured data. Currently only ``csv``
   is supported. JSON and XML may be added soon.

Documentation
-------------

This project uses
`numpydoc <https://numpydoc.readthedocs.io/en/latest/>`__ extension for
`Sphinx <http://sphinx-doc.org/>`__.

Testing
-------

Every new feature should have a test to make sure it still works after
modifications done by you or someone else in the future.

To run tests using the current Python version: ``pytest ninvoice2data``

To run tests using all supported Python versions: ``tox`` (needs
``pyenv`` and corresponding Python versions installed.)

Coverage
--------
To test coverage we recommend using ``pytest-cov``

::

   pip install pytest-cov
   pytest --cov-report html --cov ninvoice2data --verbose
   [yourbrowser] htmlconv/index.hml
