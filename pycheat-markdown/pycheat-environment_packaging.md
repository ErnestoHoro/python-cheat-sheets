# pycheat - environment, packaging

## environment

```bash
sys.path
```

## pip

```bash
get-pip.py  # pip manual installation script
python -m pip install -U pip  # upgrade pip (global)
python -m pip install --user -U pip  # upgrade pip (user)
python -m pip install --user --upgrade setuptools pip  # upgrade pip + setuptools
pip install -U pip  # upgrade pip (linux | global)
pip install <module_name>
pip install --user <module_name> --trusted-host pypi.org
pip install --user ./downloads/python-pkg.tar.gz
pip install --only-binary :all: <module_name>  # install binaries only
pip freeze > requirements.txt
pip install -r requirements.txt
grep -lr md5 ~/.cache/pipenv/hash-cache | xargs rm  # delete md5 hashes from cache
```

## zipapp - Executable Python ZIP Archives (built-in)

```bash
# python -m zipapp source [options]
python -m zipapp myapp -m "myapp:main" -c  # c - compress
python -m zipapp hello_world.pyz --info  # display embedded interpreter
    # (e.g.) Interpreter: /sw/common-os/oss/python/3.8.2/bin/python3
python myapp.pyz  # run a zipapp
```

## Virtual Environments

### pipenv

```bash
python -m pip install pipenv  # install pipenv (user)
```

### virtualenv

```bash
pip install virtualenv
virtualenv --version
virtualenv <my_env>  # create new virtualenv
virtualenv -p /usr/bin/python3 <my_env>  # specify interpreter for virtualenv

source <my_env>/bin/activate  # activate your virtualenv (bash)
pip install <package_name>  # use pip from your virtualenv
```

## PyInstaller

```bash
pyinstaller myscript.py  # single folder packaging
pyinstaller --onefile --windowed myscript.py  # single file packaging
pyinstaller --specpath='<*.spec>' myscript.py  # include *.spec file
pyinstaller --windowed --hiddenimport lf --onefile order_entry_demo.py
```

