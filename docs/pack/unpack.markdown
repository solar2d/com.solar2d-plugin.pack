# pack.unpack()

`unpack` is called as follows: `unpack(s,F,[init])`, where `s` is a (binary) string
containing data packed as if by pack, `F` is a format string describing what is
to be read from `s`, and the optional `init` marks where in `s` to begin reading the
values. `unpack` returns one value per letter in `F` until `F` or `s` is exhausted
(the letters codes are the same as for [`pack`][plugin.pack.pack], except that numbers following `A`
are interpreted as the number of characters to read into the string, not as
repetitions).
