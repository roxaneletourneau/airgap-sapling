# AirGap Sapling Wasm

[![npm](https://img.shields.io/npm/v/@airgap/sapling-wasm.svg?colorB=brightgreen)](https://www.npmjs.com/package/@airgap/sapling-wasm)

A Wasm wrapper around [Zcash Rust crates](https://github.com/zcash/librustzcash).

## Install

```
$ npm install --save @airgap/sapling-wasm
```

## Example

```ts
import * as bip39 from 'bip39'
import * as sapling from '@airgap/sapling-wasm'

const mnemonic: String = bip39.generateMnemonic()
const seed: Buffer = bip39.mnemonicToSeed(mnemonic, '')
const derivationPath: String = 'm/'

// create an extended spending key
const spendingKey: Buffer = sapling.getExtendedSpendingKey(seed, derivationPath)
console.log(spendingKey.toString('hex'))

// create an extended full viewing key
const viewingKey: Buffer = sapling.getExtendedFullViewingKey(seed, derivationPath)
console.log(viewingKey.toString('hex'))
```
