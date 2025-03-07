# Minilib.Crypto.SHA512

Defined in minilib-crypto@0.5.1

SHA-512 secure hash function.

Implemented from specification of FIPS PUB 180-4:
https://csrc.nist.gov/files/pubs/fips/180-4/final/docs/fips180-4.pdf

NOTE: FIPS 180-4 (2012) is superseded by FIPS 180-4 (2015), with the only change being
made in the Applicability Clause. There are no changes to the technical specifications.
FIPS 180-4 (2015):
http://dx.doi.org/10.6028/NIST.FIPS.180-4

## Values

### namespace Minilib.Crypto.SHA512

#### _bit_not

Type: `Std::U64 -> Std::U64`

2.2.2 Symbols and Operations
bitwise complement

#### _ch

Type: `Std::U64 -> Std::U64 -> Std::U64 -> Std::U64`

4.1.3 SHA-384, SHA-512, SHA-512/224 and SHA-512/256 Functions

#### _init_hash_sha384

Type: `Std::Array Std::U64`

5.3 Setting the Initial Hash Value (H(0))
5.3.4 SHA-384

#### _init_hash_sha512

Type: `Std::Array Std::U64`

5.3.5 SHA-512

#### _k

Type: `Std::Array Std::U64`

#### _large_sigma_0

Type: `Std::U64 -> Std::U64`

#### _large_sigma_1

Type: `Std::U64 -> Std::U64`

#### _maj

Type: `Std::U64 -> Std::U64 -> Std::U64 -> Std::U64`

#### _rotl

Type: `Std::U64 -> Std::U64 -> Std::U64`

rotate left

#### _rotr

Type: `Std::U64 -> Std::U64 -> Std::U64`

rotate right

#### _shr

Type: `Std::U64 -> Std::U64 -> Std::U64`

shift right

#### _small_sigma_0

Type: `Std::U64 -> Std::U64`

#### _small_sigma_1

Type: `Std::U64 -> Std::U64`

#### _update_hash

Type: `Std::Array Std::U64 -> Std::Array Std::U64 -> Std::Array Std::U64`

6.2.2 SHA-512 Hash Computation

#### _update_inner

Type: `Std::Array Std::U8 -> Std::U64 -> Minilib.Crypto.SHA512::SHA512 -> Minilib.Crypto.SHA512::SHA512`

`sha512._update_inner(input, msglen_inc)` updates the message buffer with input.
And it increments the message length by `msglen_inc`.
When the message buffer is full (128 bytes), it updates hash with the message
and clears the messsage buffer.

#### digest

Type: `Std::Array Std::U8 -> Std::Array Std::U8`

`SHA512::digest(bytes)` computes SHA-512 secure hash function of `bytes`.

#### empty

Type: `Minilib.Crypto.SHA512::SHA512`

An empty SHA-512 hasher.

#### finalize

Type: `Minilib.Crypto.SHA512::SHA512 -> Std::Array Std::U8`

`sha512.finalize` retrieves a final SHA-512 hash value.

#### update

Type: `Std::Array Std::U8 -> Minilib.Crypto.SHA512::SHA512 -> Minilib.Crypto.SHA512::SHA512`

`sha512.update(bytes)` processes `bytes`, and updates its internal state.

### namespace Minilib.Crypto.SHA512::SHA384

#### digest

Type: `Std::Array Std::U8 -> Std::Array Std::U8`

`SHA384::digest(bytes)` computes SHA-384 secure hash function of `bytes`.

## Types and aliases

### namespace Minilib.Crypto.SHA512

#### SHA512

Defined as: `type SHA512 = unbox struct { ...fields... }`

SHA-512 hasher.
Usually it is sufficient to simply call `SHA512:digest(bytes)` without using this structure.

##### field `hash`

Type: `Std::Array Std::U64`

##### field `msglen`

Type: `Std::U64`

##### field `msgbuf`

Type: `Std::Array Std::U8`

## Traits and aliases

## Trait implementations