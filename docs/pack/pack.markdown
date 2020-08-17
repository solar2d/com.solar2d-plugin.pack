# pack.pack()

`pack` is called as follows: `pack(F,x1,x2,...)`, where `F` is a string describing
how the values `x1`, `x2`, ... are to be interpreted and formatted. Each letter
in the format string F consumes one of the given values. Only values of type
number or string are accepted. `pack` returns a (binary) string containing the
values packed as described in `F`. The letter codes understood by `pack` are listed
below (they are inspired by Perl's codes but are not the same). Numbers
following letter codes in F indicate repetitions.

|Character|Description|
|---------|-----------|
|z|zero-terminated string|
|p|string preceded by length byte|
|P|string preceded by length word|
|a|string preceded by length size_t|
|A|string|
|f|float|
|d|double|
|n|Lua number|
|c|char|
|b|byte = unsigned char|
|h|short|
|H|unsigned short|
|i|int|
|I|unsigned int|
|l|long|
|L|unsigned long|
|<|little endian|
|>|big endian|
|=|native endian|
