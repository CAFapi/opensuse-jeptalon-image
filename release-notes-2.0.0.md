#### Version Number
${version-number}

#### New Features
- **SCMOD-8481**: TLS/SSL cipher hardening  
Weaker TLS algorithms have been disabled to help to protect against vulnerabilities such as [Logjam](https://en.wikipedia.org/wiki/Logjam_(computer_security)).

#### Bug Fixes
- **SCMOD-8122**: Installing `python-numpy-devel` package instead of `python-numpy`  
This is due to missing headers causing a `scikit-learn` installation error.

#### Known Issues
- None

#### Breaking Changes
- **SCMOD-8481**: TLS/SSL cipher hardening  
Weaker TLS algorithms are no longer supported by default.  See [here](https://github.com/CAFapi/opensuse-java8-images/blob/develop/src/main/docker/disableWeakTlsAlgorithms.patch) to view the list of algorithms which have been disabled.
