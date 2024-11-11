# Collections
These collections are free to use.
I appreciate your improvements and bug reports.

## How to test your changes/prepare your test environment
-------------------

Before submitting a pull request, make sure to test your changes:

1. Run the ansible linter:

Install prerequisits and run
    python3 -m pip install --upgrade pip
    pip3 install virtualenv
    virtualenv molecule

    # For fish users:
    source molecule/bin/activate.fish
    # For Bash users:
    source molecule/bin/activate

    pip3 install -r requirements.txt  # Install project dependencies


2. Run molecule test on your local:

.. code-block:: bash

    cd user_ssh_toolbox/roles/${ROLE_NAME}
    molecule test
