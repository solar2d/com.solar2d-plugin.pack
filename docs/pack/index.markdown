# lpack.*

> --------------------- ------------------------------------------------------------------------------------------
> __Type__				[Library][api.type.Library]
> __Revision__			[REVISION_LABEL](REVISION_URL)
> __Keywords__			lpack, binary
> __Platforms__			Android, iOS, macOS, Windows, tvOS
> --------------------- ------------------------------------------------------------------------------------------

## Overview

This is a simple Lua library for packing and unpacking binary data. Note, that it extends string except of actually returning the plugin.


## Syntax

	require( "plugin.pack" )

## Functions

#### [string.pack(f,...)][plugin.pack.pack]

#### [string.unpack(s,f,[init])][plugin.pack.unpack]


```
require "plugin.pack"

bpack=string.pack
bunpack=string.unpack

function hex(s)
 s=string.gsub(s,"(.)",function (x) return string.format("%02X",string.byte(x)) end)
 return s
end

a=bpack("Ab8","\027Lua",5*16+1,0,1,4,4,4,8,0)
print(hex(a),string.len(a))

b=string.dump(hex)
b=string.sub(b,1,string.len(a))
print(a==b,string.len(b))
print(bunpack(b,"bA3b8"))

i=314159265 f="<I>I=I"
a=bpack(f,i,i,i)
print(hex(a))
print(bunpack(a,f))

i=3.14159265 f="<d>d=d"
a=bpack(f,i,i,i)
print(hex(a))
print(bunpack(a,f))

```