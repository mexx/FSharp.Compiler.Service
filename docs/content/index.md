F# Compiler Services
====================

The F# compiler services package is a component derived from the F# compiler source code that
exposes additional functionality for implementing F# language bindings, additional
tools based on the compiler or refactoring tools. The package also includes F# 
interactive service that can be used for embedding F# scripting into your applications.

<div class="row">
  <div class="span1"></div>
  <div class="span6">
    <div class="well well-small" id="nuget">
      The F# Compiler Services package can be <a href="https://nuget.org/packages/FSharp.Compiler.Service">installed from NuGet</a>:
      <pre>PM> Install-Package FSharp.Compiler.Service -Pre</pre>
    </div>
  </div>
  <div class="span1"></div>
</div>

Available services
------------------

The project currently exposes the following services that are tested & documented on this page.
The libraries contain additional public API that can be used, but is not documented here.

 * [**F# Language tokenizer**](tokenizer.html) - turns any F# source code into a stream of tokens.
   Useful for implementing source code colorization and basic tools. Correctly handle nested 
   comments, strings etc.

 * [**Processing untyped AST**](untypedtree.html) - allows accessing the untyped abstract syntax tree (AST).
   This represents parsed F# syntax without type information and can be used to implement code formatting
   and various simple processing tasks.   

 * [**Using editor (IDE) services**](editor.html) - expose functionality for auto-completion, tool-tips,
   parameter information etc. These functions are useful for implementing F# support for editors
   and for getting some type information for F# code.

 * [**Working with signatures, types, and resolved symbols**](symbols.html) - many services related to type checking
   return resolved symbols, representing inferred types, and the signatures of whole assemblies. 
  
 * [**Working with projects project-wide analysis**](project.html) - you can request a check of
   an entire project, and ask for the results of whole-project analyses such as find-all-references.
   
 * [**Hosting F# interactive**](interactive.html) - allows calling F# interactive as a .NET library
   from your .NET code. You can use this API to embed F# as a scripting language in your projects.
 
 * [**Hosting the F# compiler**](compiler.html) - allows you to embed calls to the F# compiler.
  
 * [**File system API**](filesystem.html) - the `FSharp.Compiler.Service` component has a global variable
   representing the file system. By setting this variable you can host the compiler in situations where a file system
   is not available.
  
> **NOTE:** The services in FSharp.Compiler.Service.dll are overlapping and will in the future be made more regular.


Contributing and copyright
--------------------------

This project is a fork of the [fsharp/fsharp](https://github.com/fsharp/fsharp) which has been
modified to expose additional internals useful for creating editors and F# tools and also for
embedding F# interactive.

The F# source code is copyright by Microsoft Corporation and contributors, the extensions have been
implemented by Dave Thomas, Anh-Dung Phan, Tomas Petricek and other contributors. The source code
is available under the [Apache 2.0 license](https://github.com/fsharp/FSharp.Compiler.Service/blob/master/LICENSE).
