=====================
OWASP-CRS-regressions
=====================

Introduction
============
Welcome to the OWASP Core Rule Set regression testing suite. This suite is meant to test specific rules in OWASP CRS version 3. The suite is designed to uses preconfigured IDs that are specific to this version of CRS. The tests themselves can be run without CRS and one would expect the same elements to be blocked, however one must override the default Output parameter in the tests. 

Installation
============
The OWASP Core Rule Set project was part of the effort to develop FTW, the Framework for Testing WAFs. As a result, we use this project in order to run our regression testing. FTW is designed to use existing Python testing frameworks to allow for easy to read web based testing, provided in YAML. You can install FTW by from the repository (at https://github.com/fastly/ftw) or by running pip.

```pip install -r requirements.txt```

This will install FTW as a library. It can also be run natively, see the FTW documentation for more detail.

Running The Tests
=================
There are two requirements for running the OWASP CRS regressions.

1. You must have ModSecurity specify the location of your error.log.
2. You must configure your SecDefaultAction to include both log and pass, enabling anomaly mode.

Once these requirments have been met the tests can be run by using pytest.

On Windows this will look like:
```py.test.exe -v CRS_Tests.py --rule=tests/test.yaml```

On Linux this will look like:
```py.test -v CRS_Tests.py --rule=tests/test.yaml```

