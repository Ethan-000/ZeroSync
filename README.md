# ZEROSYNC

## An alternative to Bitcoins initial block download using STARK proofs that verify the correctness of a corresponding chainstate
Zerosync will allow to download the latest state of the Bitcoin Blockchain and a verifiable proof attesting its correctness. Instead of validating every block and included transaction only the STARK proof has to be verified.

This will be achieved with a full node implememtation in Cairo. In the current state we implemented a light client in Cairo that we will now expand with functionalities.

The original light client was a relay/bridge implementation that made Bitcoin blocks available on Ethereum (e.g. for SPV) and is available in the `relay` branch.

**In general, all of this is experimental research code and not to be used in production!**

## Requirements

- Python3.7
- [Cairo](https://github.com/starkware-libs/cairo-lang) - [installation guide](https://www.cairo-lang.org/docs/quickstart.html)
- Bitcoin client, e.g. [bitcoincore](https://bitcoincore.org/en/download/)
- If you want to create STARK proofs without SHARP you need [giza](https://github.com/maxgillett/giza) (Keep the Cairo [license](https://github.com/starkware-libs/cairo-lang/blob/master/LICENSE.txt) in mind)

## Installation

- clone this repository and cd into it
- ` pip3 install -r python-requirements`
- Zerosync will prompt you for setup info when you first run it

## Usage

- Validate a batch:

```
zerosync validate-batch [START]-[END] -s
```

## Tests

### Cairo

We provide tests using [protostar](https://github.com/software-mansion/protostar).

Initial setup from within the cairo directory (the suggested standard lib directory is perfectly fine):
```
protostar init --existing
```

Run all Cairo tests from within the cairo dir (zerosync/cairo):

```
sudo chmod +x testCairo.sh
./testCairo.sh
```


## Credits

sha256 code adopted from Lior Goldberg: https://github.com/starkware-libs/cairo-examples/tree/master/sha256
