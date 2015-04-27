node-opus
=========
### NodeJS native bindings to libopus

This module implements bindings for Opus v1.1 for Node.js.

    var opus = require('node-opus');

    // Create the encoder.
    // Specify 48kHz sampling rate and 10ms frame size.
    // NOTE: The decoder must use the same values when decoding the packets.
    var rate = 48000;
    var encoder = new opus.OpusEncoder( rate );

    // Encode and decode.
    var frame_size = rate/100;
    var encoded = encoder.encode( buffer, frame_size );
    var decoded = encoder.decode( encoded, frame_size );

Platform support
----------------

Supported platforms:
- Linux x64

Add new supported platforms by running ./autogen.sh and ./configure in
deps/opus and copying the resulting config.h to deps/config/opus/<os>/<arch>.

Use the following flags with configure:

    ./configure --enable-static --disable-shared --with-pic
