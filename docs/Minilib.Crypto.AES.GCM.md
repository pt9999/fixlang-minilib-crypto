# Minilib.Crypto.AES.GCM

Defined in minilib-crypto@0.5.1

Galois/Counter Mode (GCM) for AES

Implemented from specification of NIST Special Publication 800-38D:
Recommendation for Block Cipher Modes of Operation: Galois/Counter Mode (GCM) and GMAC
https://doi.org/10.6028/NIST.SP.800-38D

## Values

### namespace Minilib.Crypto.AES.GCM::Block

#### _GCTR

Type: `(Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block) -> Minilib.Crypto.AES.GCM::Block -> Std::Array Std::U8 -> Std::Array Std::U8`

Calculates GCTR() function.

#### _GHASH

Type: `Minilib.Crypto.AES.GCM::Block -> Std::Iterator::DynIterator Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Calculates GHASH() function.

#### _R

Type: `Minilib.Crypto.AES.GCM::Block`

The reduction polynomial `R = 11100011 || 0^120`.
This is the primitive polynomial of GF(2^128).

#### _bit_xor

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Calculates bitwise XOR of two 128-bit blocks.

#### _bytes_to_blocks

Type: `Std::Array Std::U8 -> Std::Iterator::DynIterator Minilib.Crypto.AES.GCM::Block`

Converts a byte array to an iterator of 128-bit blocks.

#### _inc_32

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

6.2 Incrementing function

#### _is_bit_set

Type: `Std::I64 -> Minilib.Crypto.AES.GCM::Block -> Std::Bool`

`x._is_bit_set(i)` returns true if the bit `i` is set.
NOTE that the bit 0 is the leftmost bit (ie. MSB) of the block.

#### _mul

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Multiplication operation of Blocks

#### _mul_bitwise

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Multiplication operation of Blocks using bitwise-xor and reducing by the reduction polynomial `_R`.

#### _shift_right_1

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Shifts a 128-bit block to right by 1 bit.

#### _u64_to_bitstring

Type: `Std::U64 -> Std::Array Std::U8`

#### _zero

Type: `Minilib.Crypto.AES.GCM::Block`

A zero block.

#### get_block_be

Type: `Std::I64 -> Std::Array Std::U8 -> Minilib.Crypto.AES.GCM::Block`

`buf.get_block_be(i)` reads a 128 bit block in big endian at position `i` in array `buf`.

#### make

Type: `Std::U64 -> Std::U64 -> Minilib.Crypto.AES.GCM::Block`

`Block::make(hi, lo)` creates a 128 bit block.

#### set_block_be

Type: `Std::I64 -> Minilib.Crypto.AES.GCM::Block -> Std::Array Std::U8 -> Std::Array Std::U8`

`buf.set_block_be(i, block)` writes a 128 bit block in big endian at position `i` in array `buf`.

### namespace Minilib.Crypto.AES.GCM::CLMul

#### _clmul_u128_u128_reduce

Type: `Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Performs multiplication operation on blocks.
ie. clmul(u128, u128) and reduce the result by the reduction polynomial `R = 11100001 || 0^120`.
NOTE: the bit order is reversed, ie. bit 0 is MSB, bit (n-1) is LSB.

#### _clmul_u16_u16

Type: `Std::U16 -> Std::U16 -> Std::U32`

Performs carryless multiplication of U16 and U16.
NOTE: the bit order is reversed, ie. bit 0 is MSB, bit (n-1) is LSB.

#### _clmul_u32_u32

Type: `Std::U32 -> Std::U32 -> Std::U64`

Performs carryless multiplication of U32 and U32.
NOTE: the bit order is reversed, ie. bit 0 is MSB, bit (n-1) is LSB.

#### _clmul_u64_u64

Type: `Std::U64 -> Std::U64 -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Performs carryless multiplication of U64 and U64. `z` is used as a buffer for setting the result.
NOTE: the bit order is reversed, ie. bit 0 is MSB, bit (n-1) is LSB.

#### _clmul_u8_u8

Type: `Std::U8 -> Std::U8 -> Std::U16`

Performs carryless multiplication of U8 and U8.

#### _clmul_u8_u8_table

Type: `Std::Array Std::U16`

### namespace Minilib.Crypto.AES.GCM::GCM

#### _get_j0

Type: `Minilib.Crypto.AES.GCM::Block -> Std::Array Std::U8 -> Minilib.Crypto.AES.GCM::Block`

get the pre-counter block

#### _get_tag

Type: `(Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block) -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::I64 -> Std::Array Std::U8`

get the authentication tag

#### _to_cipher

Type: `Minilib.Crypto.AES::AES -> Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block`

Converts an AES structure to a cipher.
NOTE: aes.decrypt_block will not be used in AES-GCM.

#### gcm_ad

Type: `(Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block) -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::I64 -> Std::Result Std::ErrMsg (Std::Array Std::U8)`

Performs authenticated decryption.
Input:
- cipher: 128-bit block cipher
- iv: initialization vector, typically 96 bits
- ciphertext: a byte sequence which will be decrypted
- auth_data: a byte sequence which will not be encrypted
- tag: authentication tag
Output: ok(plaintext) or err(ErrMsg)
- ok(plaintext): decrypted byte sequence
- err(ErrMsg): inauthenticity

#### gcm_ae

Type: `(Minilib.Crypto.AES.GCM::Block -> Minilib.Crypto.AES.GCM::Block) -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::Array Std::U8 -> Std::I64 -> (Std::Array Std::U8, Std::Array Std::U8)`

Performs authenticated encryption.
Input:
- cipher: 128-bit block cipher
- iv: initialization vector, typically 96 bits
- plaintext: a byte sequence which will be encrypted
- auth_data: a byte sequence which will not be encrypted
- len_t: tag length in bits
Output: (c, t)
- c: ciphertext
- t: authentication tag

## Types and aliases

### namespace Minilib.Crypto.AES.GCM

#### Block

Defined as: `type Block = unbox struct { ...fields... }`

A block is a bit string of 128 bits.
We use two U64 as a representation.
When converted to a bit string, it is encoded in big-endian.
If a byte sequence is encoded to a bit string, MSB of the first byte becomes the leftmost bit.

##### field `hi`

Type: `Std::U64`

##### field `lo`

Type: `Std::U64`

## Traits and aliases

## Trait implementations

### impl `Minilib.Crypto.AES.GCM::Block : Minilib.Text.Hex::ToStringHex`

### impl `Minilib.Crypto.AES.GCM::Block : Std::Eq`

### impl `Minilib.Crypto.AES.GCM::Block : Std::FromBytes`

### impl `Minilib.Crypto.AES.GCM::Block : Std::ToBytes`

### impl `Minilib.Crypto.AES.GCM::Block : Std::ToString`