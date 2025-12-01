---
layout: post
title:  "Type Name Deofuscation With IL2CPP"
tag: "Programming, Hacking, IL2CPP"
---

Many Unity games I come across use *type name obfuscation* in order to attempt to make it more difficult to reverse engineer.

Everything in .net is a type, from assemblies to namespaces, classes or properties, methods or attributes. 
There for the easiest way to put cloth over the end users eyes, is to change the names of these types. Many applications will change type names to random unicode characters or different confusables, such as Iïịíí or ones that often just look like □□□□□. These these changes to the type names are often done after or during the c# code being built to IL(intermediate language) there for it is nondestructive to the original source code. 

IL2CPP adds an extra layer of abstraction to this where the the IL of these applications is then built into a native binary usually called gameassembly.dll(on windows) with essentially an external symbol table called global-metadata.dat which stores our *obfuscated* type names and some additional info. If you want to learn more information on il2cpp reverse engineering check out [Il2CppDumper](https://il2cppdumper.com/il2cpp/what-is-il2cpp)

How do we get the types from these two files? Well a few tools exist to do just this, [Cpp2IL](https://github.com/SamboyCoding/Cpp2IL) a tool that produces *dummy dlls* which have attributes to point to their offsets in the gameassembly binary, and (Il2CppInterop)[https://github.com/BepInEx/Il2CppInterop] a tool to take these dummy dlls and fill their bodies with scaffolding for the bepinex modloader.

But how do we find out what these type truly are? Real answer: there is no way to perfectly know what a type was named before hand(unless it's a very poorly made obfuscation library). 
If you're extremely lucky unity [AddComponentMenu("Menu Name/SubMenu Name")] custom attributes won't be stripped. (Keep in mind that il2cpp interop does strip these in its dummy dlls) More often then not it won't be as easy as that.

We have other options luckily, the next place I will usually check is GameObject names using [UnityExplorer](https://github.com/sinai-dev/UnityExplorer) or if that isn't an option i will look at static objects in the scene files using [UABEA](https://github.com/nesrak1/UABEA) a unity asset bundle extractor/viewer. More often then not the GameObjects a MonoBehaviour is attached to gives away its purpose, such as an object called LocomotionManager will most likely hold MonoBehaviours to do with movement. Some developers have realized this and have tools to randomize GameObject names on ship, but if they haven't it is a very powerful clue.

If you need more hints another place we can look is in the assembly itself, *Cpp2IL* and *Il2Dumper* come with different scripts to aid static debugging *gameassembly.dll* with IDA, Ghidra, and BinaryNinja in newer releases. I personally use a dnspy extension called [dnspy.cpp2il](https://github.com/BadRyuner/dnspy.Cpp2IL) which uses *libcpp2il* and *Echo* to display pseudo IL from the pseudo C produced by Echo. From this you can analyze strings used in to give you hints on what specific classes do, and look at control flow. If your obfuscated method is called by "PlaySong()" this method most likely related to that. It is important to keep in mind that due to the nature of it being static analysis some strings may be incorrect or different at runtime, so take strings you see with a grain of salt.

It is also important to note that tools such as il2cppinterop or unhollower will attempt to *demangle* non alphanumeric type names. These *demanged* names for classes will look like {theSuperClass}{Privacy}{Static} followed by alpha numeric characters. Method names will be {Privacy}{Static}{ReturnValue}{Param1}_0 the 0 being the offset of matching signatures in that class.
