###Info

This is a stripped down version of the [Reflexil](http://reflexil.net/). It contains [Reflexil's version](https://github.com/sailro/Reflexil/tree/master/Libs/Sources/Mono.Cecil.Pdb.Reflexil) of the [Mono.Cecil](https://github.com/jbevain/cecil) library + helper classes ([ByteHelper.cs](https://github.com/sailro/Reflexil/blob/master/Utils/ByteHelper.cs), [CecilHelper.cs](https://github.com/sailro/Reflexil/blob/master/Utils/CecilHelper.cs)).
It's main purpose is to be able to inject/patch a .Net code without GUI-mode Reflexil plugin.

###Technical details

I've removed dependency on the Reflexil's settings and edited `CloneMethodBody` method to accept `2` overloads:

``````csharp
OverloadDefinitions
-------------------
static void CloneMethodBody(Mono.Cecil.Reflexil.MethodDefinition source, Mono.Cecil.Reflexil.MethodDefinition target)
static void CloneMethodBody(Mono.Cecil.Reflexil.MethodDefinition source, Mono.Cecil.Reflexil.MethodDefinition target, bool OptimizeAndFixIL)
```

If you don't want to build this project yourself, just download the [Mono.Cecil.Reflexil.dll](https://github.com/beatcracker/GUILess-Reflexil/raw/master/Mono.Cecil.Reflexil/bin/Release/Mono.Cecil.Reflexil.dll) binary.

###Example

See my [Ori Controller Remap] tool, which uses this library in PowerShell to replace method in the assembly.

[Ori Controller Remap]:https://github.com/beatcracker/Ori-Controller-Remap