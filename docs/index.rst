概览
========

LLVM编译基础设施广泛支持各种项目,从工业强度的编译器到小型学术研究类的JIT应用

因此，文档也被分成多个高阶分类，用于给不同目的的读者阅读。

LLVM 设计 & 概览
======================

一些介绍性的论文和演讲

.. toctree::
   :hidden:

   LangRef

:doc:`LangRef`
  描述了LLVM中间表示

`Introduction to the LLVM Compiler`__
  一个给用户介绍LLVM的演讲

  .. __: http://llvm.org/pubs/2008-10-04-ACAT-LLVM-Intro.html

`LLVM入门`__
  一本书的章节，描述了编译器黑客如何入门LLVM

  .. __: http://www.aosabook.org/en/llvm.html


`LLVM: A Compilation Framework for Lifelong Program Analysis & Transformation`__
  Design overview.

  .. __: http://llvm.org/pubs/2004-01-30-CGO-LLVM.html

`LLVM: 一个多阶段优化的基础设施`__
  更多的细节 (现在挺老了).

  .. __: http://llvm.org/pubs/2002-12-LattnerMSThesis.html

`一些提到LLVM的出版物 <http://llvm.org/pubs>`_
   ..

User Guides
===========

给那些LLVM系统的新手

注意: 如果你是个只对基于LLVM的编译器感兴趣的用户, 你应该查阅 `Clang <http://clang.llvm.org>`_ 或是
`DragonEgg <http://dragonegg.llvm.org>`_ 的文档而不是本文档。本文档的目标受众是需要对LLVM中间表示进行相关工作的读者。

.. toctree::
   :hidden:

   CMake
   CMakePrimer
   AdvancedBuilds
   HowToBuildOnARM
   HowToCrossCompileBuiltinsOnArm
   HowToCrossCompileLLVM
   CommandGuide/index
   GettingStarted
   GettingStartedVS
   FAQ
   Lexicon
   HowToAddABuilder
   yaml2obj
   HowToSubmitABug
   SphinxQuickstartTemplate
   Phabricator
   TestingGuide
   tutorial/index
   ReleaseNotes
   Passes
   YamlIO
   GetElementPtr
   Frontend/PerformanceTips
   MCJITDesignAndImplementation
   CodeOfConduct
   CompileCudaWithLLVM
   ReportingGuide
   Benchmarking
   Docker

:doc:`GettingStarted`
   讨论了如何快速设置并运行LLVM基础设施，涵盖了从分发版的解压和编译到一些工具的执行。

:doc:`CMake`
   An addendum to the main Getting Started guide for those using the `CMake
   build system <http://www.cmake.org>`_.

:doc:`HowToBuildOnARM`
   Notes on building and testing LLVM/Clang on ARM.

:doc:`HowToCrossCompileBuiltinsOnArm`
   关于如何为ARM交叉编译并测试compiler-rt的内置函数

:doc:`HowToCrossCompileLLVM`
   Notes on cross-building and testing LLVM/Clang.

:doc:`GettingStartedVS`
   An addendum to the main Getting Started guide for those using Visual Studio
   on Windows.

:doc:`tutorial/index`
   Tutorials about using LLVM. Includes a tutorial about making a custom
   language with LLVM.

:doc:`LLVM Command Guide <CommandGuide/index>`
   A reference manual for the LLVM command line utilities ("man" pages for LLVM
   tools).

:doc:`Passes`
   A list of optimizations and analyses implemented in LLVM.

:doc:`FAQ`
   A list of common questions and problems and their solutions.

:doc:`Release notes for the current release <ReleaseNotes>`
   This describes new features, known bugs, and other limitations.

:doc:`HowToSubmitABug`
   Instructions for properly submitting information about any bugs you run into
   in the LLVM system.

:doc:`SphinxQuickstartTemplate`
  A template + tutorial for writing new Sphinx documentation. It is meant
  to be read in source form.

:doc:`LLVM Testing Infrastructure Guide <TestingGuide>`
   A reference manual for using the LLVM testing infrastructure.

`How to build the C, C++, ObjC, and ObjC++ front end`__
   Instructions for building the clang front-end from source.

   .. __: http://clang.llvm.org/get_started.html

:doc:`Lexicon`
   Definition of acronyms, terms and concepts used in LLVM.

:doc:`HowToAddABuilder`
   Instructions for adding new builder to LLVM buildbot master.

:doc:`YamlIO`
   A reference guide for using LLVM's YAML I/O library.

:doc:`GetElementPtr`
  Answers to some very frequent questions about LLVM's most frequently
  misunderstood instruction.

:doc:`Frontend/PerformanceTips`
   A collection of tips for frontend authors on how to generate IR
   which LLVM is able to effectively optimize.

:doc:`Docker`
   A reference for using Dockerfiles provided with LLVM.


Programming Documentation
=========================

For developers of applications which use LLVM as a library.

.. toctree::
   :hidden:

   Atomics
   CodingStandards
   CommandLine
   CompilerWriterInfo
   ExtendingLLVM
   HowToSetUpLLVMStyleRTTI
   ProgrammersManual
   Extensions
   LibFuzzer
   FuzzingLLVM
   ScudoHardenedAllocator
   OptBisect

:doc:`LLVM Language Reference Manual <LangRef>`
  描述了LLVM不同节点的中间表示和汇编形式。

:doc:`Atomics`
  Information about LLVM's concurrency model.

:doc:`ProgrammersManual`
  介绍LLVM源码树的大致结构，重要的类和API,以及一些提示和技巧。

:doc:`Extensions`
  LLVM-specific extensions to tools and formats LLVM seeks compatibility with.

:doc:`CommandLine`
  Provides information on using the command line parsing library.

:doc:`CodingStandards`
  Details the LLVM coding standards and provides useful information on writing
  efficient C++ code.

:doc:`HowToSetUpLLVMStyleRTTI`
  How to make ``isa<>``, ``dyn_cast<>``, etc. available for clients of your
  class hierarchy.

:doc:`ExtendingLLVM`
  Look here to see how to add instructions and intrinsics to LLVM.

`Doxygen generated documentation <http://llvm.org/doxygen/>`_
  (`classes <http://llvm.org/doxygen/inherits.html>`_)

`Documentation for Go bindings <http://godoc.org/llvm.org/llvm/bindings/go/llvm>`_

`ViewVC Repository Browser <http://llvm.org/viewvc/>`_
   ..

:doc:`CompilerWriterInfo`
  A list of helpful links for compiler writers.

:doc:`LibFuzzer`
  A library for writing in-process guided fuzzers.

:doc:`FuzzingLLVM`
  Information on writing and using Fuzzers to find bugs in LLVM.

:doc:`ScudoHardenedAllocator`
  A library that implements a security-hardened `malloc()`.

:doc:`OptBisect`
  A command line option for debugging optimization-induced failures.

Subsystem Documentation
=======================

For API clients and LLVM developers.

.. toctree::
   :hidden:

   AliasAnalysis
   MemorySSA
   BitCodeFormat
   BlockFrequencyTerminology
   BranchWeightMetadata
   Bugpoint
   CodeGenerator
   ExceptionHandling
   LinkTimeOptimization
   SegmentedStacks
   TableGenFundamentals
   TableGen/index
   DebuggingJITedCode
   GoldPlugin
   MarkedUpDisassembly
   SystemLibrary
   SourceLevelDebugging
   Vectorizers
   WritingAnLLVMBackend
   GarbageCollection
   WritingAnLLVMPass
   HowToUseAttributes
   NVPTXUsage
   AMDGPUUsage
   StackMaps
   InAlloca
   BigEndianNEON
   CoverageMappingFormat
   Statepoints
   MergeFunctions
   TypeMetadata
   FaultMaps
   MIRLangRef
   Coroutines
   GlobalISel
   XRay
   XRayExample
   XRayFDRFormat
   PDB/index
   CFIVerify

:doc:`WritingAnLLVMPass`
   关于如何编写LLVM IR的变形和分析。

:doc:`WritingAnLLVMBackend`
   关于如何为目标机器编写LLVM后端

:doc:`CodeGenerator`
   The design and implementation of the LLVM code generator.  Useful if you are
   working on retargetting LLVM to a new architecture, designing a new codegen
   pass, or enhancing existing components.

:doc:`Machine IR (MIR) Format Reference Manual <MIRLangRef>`
   A reference manual for the MIR serialization format, which is used to test
   LLVM's code generation passes.

:doc:`TableGen <TableGen/index>`
   描述了在LLVM代码生成器中被大量使用的TableGen工具。

:doc:`AliasAnalysis`
   关于如何编写新的别名分析实现或者是如何使用现有的分析。

:doc:`MemorySSA`
   Information about the MemorySSA utility in LLVM, as well as how to use it.

:doc:`GarbageCollection`
   The interfaces source-language compilers should use for compiling GC'd
   programs.

:doc:`Source Level Debugging with LLVM <SourceLevelDebugging>`
   This document describes the design and philosophy behind the LLVM
   source-level debugger.

:doc:`Vectorizers`
   这个文档描述了LLVM中的向量化目前的状态

:doc:`ExceptionHandling`
   这个文档描述了LLVM中的异常处理的设计和实现。

:doc:`Bugpoint`
   Automatic bug finder and test-case reducer description and usage
   information.

:doc:`BitCodeFormat`
   这个文档描述了LLVM的"bc"文件的格式。

:doc:`System Library <SystemLibrary>`
   This document describes the LLVM System Library (``lib/System``) and
   how to keep LLVM source code portable

:doc:`LinkTimeOptimization`
   This document describes the interface between LLVM intermodular optimizer
   and the linker and its design

:doc:`GoldPlugin`
   How to build your programs with link-time optimization on Linux.

:doc:`DebuggingJITedCode`
   如何用GDB调试JIT生成的代码

:doc:`MCJITDesignAndImplementation`
   Describes the inner workings of MCJIT execution engine.

:doc:`BranchWeightMetadata`
   Provides information about Branch Prediction Information.

:doc:`BlockFrequencyTerminology`
   Provides information about terminology used in the ``BlockFrequencyInfo``
   analysis pass.

:doc:`SegmentedStacks`
   This document describes segmented stacks and how they are used in LLVM.

:doc:`MarkedUpDisassembly`
   This document describes the optional rich disassembly output syntax.

:doc:`HowToUseAttributes`
  Answers some questions about the new Attributes infrastructure.

:doc:`NVPTXUsage`
   This document describes using the NVPTX backend to compile GPU kernels.

:doc:`AMDGPUUsage`
   This document describes using the AMDGPU backend to compile GPU kernels.

:doc:`StackMaps`
  LLVM support for mapping instruction addresses to the location of
  values and allowing code to be patched.

:doc:`BigEndianNEON`
  LLVM's support for generating NEON instructions on big endian ARM targets is
  somewhat nonintuitive. This document explains the implementation and rationale.

:doc:`CoverageMappingFormat`
  This describes the format and encoding used for LLVM’s code coverage mapping.

:doc:`Statepoints`
  This describes a set of experimental extensions for garbage
  collection support.

:doc:`MergeFunctions`
  Describes functions merging optimization.

:doc:`InAlloca`
  Description of the ``inalloca`` argument attribute.

:doc:`FaultMaps`
  LLVM support for folding control flow into faulting machine instructions.

:doc:`CompileCudaWithLLVM`
  LLVM support for CUDA.

:doc:`Coroutines`
  LLVM support for coroutines.

:doc:`GlobalISel`
  This describes the prototype instruction selection replacement, GlobalISel.

:doc:`XRay`
  High-level documentation of how to use XRay in LLVM.

:doc:`XRayExample`
  An example of how to debug an application with XRay.

:doc:`The Microsoft PDB File Format <PDB/index>`
  A detailed description of the Microsoft PDB (Program Database) file format.

:doc:`CFIVerify`
  A description of the verification tool for Control Flow Integrity.

Development Process Documentation
=================================

Information about LLVM's development process.

.. toctree::
   :hidden:

   DeveloperPolicy
   Projects
   LLVMBuild
   HowToReleaseLLVM
   Packaging
   ReleaseProcess
   Phabricator

:doc:`DeveloperPolicy`
   The LLVM project's policy towards developers and their contributions.

:doc:`Projects`
  How-to guide and templates for new projects that *use* the LLVM
  infrastructure.  The templates (directory organization, Makefiles, and test
  tree) allow the project code to be located outside (or inside) the ``llvm/``
  tree, while using LLVM header files and libraries.

:doc:`LLVMBuild`
  Describes the LLVMBuild organization and files used by LLVM to specify
  component descriptions.

:doc:`HowToReleaseLLVM`
  This is a guide to preparing LLVM releases. Most developers can ignore it.

:doc:`ReleaseProcess`
  This is a guide to validate a new release, during the release process. Most developers can ignore it.

:doc:`Packaging`
   Advice on packaging LLVM into a distribution.

:doc:`Phabricator`
   Describes how to use the Phabricator code review tool hosted on
   http://reviews.llvm.org/ and its command line interface, Arcanist.

Community
=========

LLVM has a thriving community of friendly and helpful developers.
The two primary communication mechanisms in the LLVM community are mailing
lists and IRC.

Mailing Lists
-------------

If you can't find what you need in these docs, try consulting the mailing
lists.

`Developer's List (llvm-dev)`__
  This list is for people who want to be included in technical discussions of
  LLVM. People post to this list when they have questions about writing code
  for or using the LLVM tools. It is relatively low volume.

  .. __: http://lists.llvm.org/mailman/listinfo/llvm-dev

`Commits Archive (llvm-commits)`__
  This list contains all commit messages that are made when LLVM developers
  commit code changes to the repository. It also serves as a forum for
  patch review (i.e. send patches here). It is useful for those who want to
  stay on the bleeding edge of LLVM development. This list is very high
  volume.

  .. __: http://lists.llvm.org/pipermail/llvm-commits/

`Bugs & Patches Archive (llvm-bugs)`__
  This list gets emailed every time a bug is opened and closed. It is
  higher volume than the LLVM-dev list.

  .. __: http://lists.llvm.org/pipermail/llvm-bugs/

`Test Results Archive (llvm-testresults)`__
  A message is automatically sent to this list by every active nightly tester
  when it completes.  As such, this list gets email several times each day,
  making it a high volume list.

  .. __: http://lists.llvm.org/pipermail/llvm-testresults/

`LLVM Announcements List (llvm-announce)`__
  This is a low volume list that provides important announcements regarding
  LLVM.  It gets email about once a month.

  .. __: http://lists.llvm.org/mailman/listinfo/llvm-announce

IRC
---

Users and developers of the LLVM project (including subprojects such as Clang)
can be found in #llvm on `irc.oftc.net <irc://irc.oftc.net/llvm>`_.

This channel has several bots.

* Buildbot reporters

  * llvmbb - Bot for the main LLVM buildbot master.
    http://lab.llvm.org:8011/console
  * bb-chapuni - An individually run buildbot master. http://bb.pgr.jp/console
  * smooshlab - Apple's internal buildbot master.

* robot - Bugzilla linker. %bug <number>

* clang-bot - A `geordi <http://www.eelis.net/geordi/>`_ instance running
  near-trunk clang instead of gcc.

Community wide proposals
------------------------

Proposals for massive changes in how the community behaves and how the work flow
can be better.

.. toctree::
   :hidden:

   CodeOfConduct
   Proposals/GitHubMove
   Proposals/VectorizationPlan

:doc:`CodeOfConduct`
   Proposal to adopt a code of conduct on the LLVM social spaces (lists, events,
   IRC, etc).

:doc:`Proposals/GitHubMove`
   Proposal to move from SVN/Git to GitHub.

:doc:`Proposals/VectorizationPlan`
   Proposal to model the process and upgrade the infrastructure of LLVM's Loop Vectorizer.

Indices and tables
==================

* :ref:`genindex`
* :ref:`search`
