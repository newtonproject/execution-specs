# NewChain Client Specifications

## Description

This repository contains the consensus specifications related to the NewChain client, specifically the specifications for [network upgrades](/network-upgrades).

### NewChain Protocol Releases

| Version and Code Name | Block No. | Released   | Incl EIPs | Specs | Blog |
| --------------------- | --------- | ---------- | --------- | ----- | ---- |
| `TBD`                 | `TBD`     | `TBD`      | [EIP-2565](https://eips.ethereum.org/EIPS/eip-2565) <br/> [EIP-2929](https://eips.ethereum.org/EIPS/eip-2929) <br/> [EIP-2718](https://eips.ethereum.org/EIPS/eip-2718) <br/> [EIP-2930](https://eips.ethereum.org/EIPS/eip-2930) <br/> [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559) <br> [EIP-3198](https://eips.ethereum.org/EIPS/eip-3198) <br/> [EIP-3529](https://eips.ethereum.org/EIPS/eip-3529) <br/> [EIP-3541](https://eips.ethereum.org/EIPS/eip-3541) <br> [EIP-3554](https://eips.ethereum.org/EIPS/eip-3554) | [Specification](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/london.md) | [Specification](./network-upgrades/mainnet-upgrades/newchain-v2.1.0.md) | [Blog](https://blog.ethereum.org/2021/07/15/london-mainnet-announcement/) |
| Boom                  | 18500000  | 2020-09-20 | [EIP-145](https://eips.ethereum.org/EIPS/eip-145) <br/> [EIP-1014](https://eips.ethereum.org/EIPS/eip-1014) <br/> [EIP-1052](https://eips.ethereum.org/EIPS/eip-1052) <br/> [EIP-1234](https://eips.ethereum.org/EIPS/eip-1234) <br/> [EIP-1283](https://eips.ethereum.org/EIPS/eip-1283) <br/> [EIP-152](https://eips.ethereum.org/EIPS/eip-152) <br/> [EIP-1108](https://eips.ethereum.org/EIPS/eip-1108) <br/> [EIP-1344](https://eips.ethereum.org/EIPS/eip-1344) <br/> [EIP-1884](https://eips.ethereum.org/EIPS/eip-1884) <br/> [EIP-2028](https://eips.ethereum.org/EIPS/eip-2028) <br/> [EIP-2200](https://eips.ethereum.org/EIPS/eip-2200) | [Blog](https://www.newtonproject.org/announcement/2020/09/20/newchainboom)                                           |



## Usage

The NewChain specification is maintained as a Python library, for better integration with tooling and testing.

Requires Python 3.7+

### Building

Building the documentation is most easily done through [`tox`](https://tox.readthedocs.io/en/latest/):

```bash
$ tox -e doc
```

The path to the generated HTML will be printed to the console.

#### Live Preview

A live preview of the documentation can be viewed locally on port `8000` with the following command:

```bash
$ tox -e doc-autobuild
```

### Development

Running the tests necessary to merge into the repository requires:

 * Python 3.7.x (not 3.8 or later), and
 * [PyPy 7.3.x](https://www.pypy.org/).
 * `geth` installed and present in `$PATH`

These version ranges are necessary because, at the time of writing, PyPy is only compatible with Python 3.7.

`execution-specs` depends on a submodule that contains common tests that are run across all clients, so we need to clone the repo with the --recursive flag. Example:
```bash
$ git clone --recursive https://github.com/ethereum/execution-specs.git
```

Or, if you've already cloned the repository, you can fetch the submodules with:

```bash
$ git submodule update --init --recursive
```

The tests can be run with:
```bash
$ tox
```

The development tools can also be run outside of `tox`, and can automatically reformat the code:

```bash
$ pip install -e ".[doc,lint,test]" # Installs eth1spec, and development tools.
$ isort src                         # Organizes imports.
$ black src                         # Formats code.
$ flake8                            # Reports style/spelling/documentation errors.
$ mypy src                          # Verifies type annotations.
$ pytest -n 4                       # Runs tests parallelly.
$ pytest -m "not slow"              # Runs tests which execute quickly.
```

It is recommended to use a [virtual environment](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment) to keep your system Python installation clean.

## Contribution Guidelines

This specification aims to be:

1. **Correct** - Describe the _intended_ behavior of the Ethereum blockchain, and any deviation from that is a bug.
2. **Complete** - Capture the entirety of _consensus critical_ parts of Ethereum.
3. **Accessible** - Prioritize readability, clarity, and plain language over performance and brevity.

### Spelling

Attempt to use descriptive English words (or _very common_ abbreviations) in documentation and identifiers. If necessary, there is a custom dictionary `whitelist.txt`.
