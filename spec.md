[![hackmd-github-sync-badge](https://hackmd.io/xccnNbdcSx6j1JjraTEglQ/badge)](https://hackmd.io/xccnNbdcSx6j1JjraTEglQ)
<!-- Note: GitHub has table of contents built in -->

# Draft Specification

**[Reference implementation](https://github.com/emojipack/emojipack-rs)**

## Goals and philosophy


## Protocol sequencing (Kevin)
Sequence of messages being sent, when, why, etc.

## Message data structures (Kevin)
Format of messages being sent, "what".

## Message encoding (Kevin)
How to hide data in text.

## Payload format (Yuto)
Emojipack "resource"/"payload".

An Emojipack Payload consists of a header and a body. The header consists of the signature, Emojipack name, and the Emojipack's UUID. The body consists of an array of Emojipack Emojinames, and Emojipack Tilemap.

### Header

#### Signature
The signature is a 256-bit Blake3 hash of the remainder of the Emojipack Payload.

#### Emojipack name
The Emojipack name is a string of valid UTF-8 codepoints, none of which whitespace or zero-width characters.

#### Emojipack UUID
The UUID is a standard 128-bit label generated

## Rendering and parsing (Yuto)
Text => Text+Emoji, emoji size(s).
Existing UTF-8 emojis (skin tones, flag countries, genders, hahahaha).
