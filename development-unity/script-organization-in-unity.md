# Script Organization in Unity

Organize your code by using namespaces and optimize compilation using assembly definitions.

## Namespaces

Set a project wide namespace:

```
Project Settings > Editor > C# Project Generation > Root Namespace
```

* [Namespaces](https://docs.unity3d.com/2020.3/Documentation/Manual/Namespaces.html)

## Assembly Definitions

By default Unity compiles all your code into one assembly, 'Assembly-CSharp.dll' which can lead to long compile times as you grow your project. Organize your code using namespaces, folders and assembly defintions.

* [Assembly Definitions](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html)
* [Assembly Definition Files](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html#create-asmdef)
