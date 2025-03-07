# Minilib.Crypto.MD5

Defined in minilib-crypto@0.5.1

MD5 secure hash function.

Implemented from specification of RFC 1321:
https://www.rfc-editor.org/rfc/rfc1321.txt

## Values

### namespace Minilib.Crypto.MD5

#### _bit_not

Type: `Std::U32 -> Std::U32`

bitwise complement

#### _f

Type: `Std::U32 -> Std::U32 -> Std::U32 -> Std::U32`

3.4 Step 4. Process Message in 16-Word Blocks

#### _g

Type: `Std::U32 -> Std::U32 -> Std::U32 -> Std::U32`

#### _h

Type: `Std::U32 -> Std::U32 -> Std::U32 -> Std::U32`

#### _i

Type: `Std::U32 -> Std::U32 -> Std::U32 -> Std::U32`

#### _init_hash

Type: `Std::Array Std::U32`

3.3 Step 3. Initialize MD Buffer

#### _rotl

Type: `Std::U32 -> Std::U32 -> Std::U32`

rotate left

#### _t

Type: `Std::Array Std::U32`

#### _update_hash

Type: `Std::Array Std::U32 -> Std::Array Std::U32 -> Std::Array Std::U32`

3.4 Step 4. Process Message in 16-Word Blocks

#### _update_inner

Type: `Std::Array Std::U8 -> Std::U64 -> Minilib.Crypto.MD5::MD5 -> Minilib.Crypto.MD5::MD5`

`md5._update_inner(input, msglen_inc)` updates the message buffer with input.
And it increments the message length by `msglen_inc`.
When the message buffer is full (64 bytes), it updates hash with the message
and clears the messsage buffer.

#### digest

Type: `Std::Array Std::U8 -> Std::Array Std::U8`

`MD5::digest(bytes)` computes MD5 secure hash function of `bytes`.

#### empty

Type: `Minilib.Crypto.MD5::MD5`

An empty MD5 hasher.

#### finalize

Type: `Minilib.Crypto.MD5::MD5 -> Std::Array Std::U8`

`md5.finalize` retrieves a final MD5 hash value.

#### update

Type: `Std::Array Std::U8 -> Minilib.Crypto.MD5::MD5 -> Minilib.Crypto.MD5::MD5`

`md5.update(bytes)` processes `bytes`, and updates its internal state.

## Types and aliases

### namespace Minilib.Crypto.MD5

#### MD5

Defined as: `type MD5 = unbox struct { ...fields... }`

MD5 hasher.
Usually it is sufficient to simply call `MD5:digest(bytes)` without using this structure.

##### field `hash`

Type: `Std::Array Std::U32`

##### field `msglen`

Type: `Std::U64`

##### field `msgbuf`

Type: `Std::Array Std::U8`

## Traits and aliases

## Trait implementations