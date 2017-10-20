Medical Spain Requirements
==========================

### Create a virtual environment
  `$ virtualenv -p python3 medical-spain-11`

### Activate virtual environment
  `$ source medical-spain-11/bin/activate`

*** Anytime you want to go out from virtual environment just type:
 `$ deactivate`

### Check if we are using virtualenv correctly
`$ which pip`	

`$ which python`

### Now make sure we have a recent pip version
`$ pip install --upgrade pip`

### Install the requirements.txt
`pip install -r https://raw.githubusercontent.com/Eficent/medical-spain-requirements/11.0/requirements.txt`

### Update the requirements.txt
You can install a python module from a git branch, e.g. install odoo 11:

`-e git+https://github.com/odoo/odoo.git@11.0#egg=odoo`

If you run again the pip install -r requirements.txt, all the modules in the requirements.txt that reference a specific git branch will be automatically upgraded to the latest commit.

You can choose to freeze the branch to a specific commit:

`-e git+https://github.com/odoo/odoo.git@<commit hash>#egg=odoo`
If you run again the pip install -r requirements.txt, it will always attempt to install to this commit.

### Specifics to odoo addons
For an odoo module to be considered a python module, the repository needs to include a setup folder, that contains a subdirectory with the module name, like https://github.com/OCA/mis-builder/tree/10.0/setup/mis_builder.

OCA updates every nigh the setup folder for all the OCA repositories. If you are working on a PR that adds a new module, you should extend the setup folder manually.

`-e git+https://github.com/Eficent/pos.git@11.0-mig-account_cash_invoice#egg=odoo11_addon_account_cash_invoice&subdirectory=setup/account_cash_invoice`

