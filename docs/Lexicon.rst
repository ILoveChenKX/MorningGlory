================
The LLVM Lexicon
================

.. note::

    这份文档还在编辑中

Definitions
===========

A
-

**ADCE**
    激烈的死代码删除

**AST**
    抽象语法树.

    由于Clang的影响 (主要是由于语法分析和语义分析纠缠的太紧,尤其是C和C++), LLVM社区中对AST的定义大致上是
    "编译器的第一个完整的符号化的(而不是文本化的)对输入程序的表达形式(译注:文本化的表达形式即源码)
    所以，一个"抽象语法树"可能更像是一个比较泛型的"图"而不是"树"
    (consider the symbolic representation for the type of a typical "linked
    list node"). This working definition is closer to what some authors
    call an "annotated abstract syntax tree".

    Consult your favorite compiler book or search engine for more details.

B
-

.. _lexicon-bb-vectorization:

**BB Vectorization**
    Basic-Block Vectorization

**BDCE**
    Bit-tracking dead code elimination. Some bit-wise instructions (shifts,
    ands, ors, etc.) "kill" some of their input bits -- that is, they make it
    such that those bits can be either zero or one without affecting control or
    data flow of a program. The BDCE pass removes instructions that only
    compute these dead bits.

**BURS**
    从下至上的重写系统 --- 一种用于代码生成的指令选择方式。一个例子就是`BURG
    <http://www.program-transformation.org/Transform/BURG>`_ 工具.

C
-

**CFI**
    调用帧信息. 在DWARF调试信息和C++栈回溯中被用于描述
    函数的序言在栈帧中的结构。

**CIE**
    Common Information Entry.  A kind of CFI used to reduce the size of FDEs.
    The compiler creates a CIE which contains the information common across all
    the FDEs.  Each FDE then points to its CIE.

**CSE**
    Common Subexpression Elimination. An optimization that removes common
    subexpression compuation. For example ``(a+b)*(a+b)`` has two subexpressions
    that are the same: ``(a+b)``. This optimization would perform the addition
    only once and then perform the multiply (but only if it's computationally
    correct/safe).

D
-

**DAG**
    Directed Acyclic Graph

.. _derived pointer:
.. _derived pointers:

**Derived Pointer**
    A pointer to the interior of an object, such that a garbage collector is
    unable to use the pointer for reachability analysis. While a derived pointer
    is live, the corresponding object pointer must be kept in a root, otherwise
    the collector might free the referenced object. With copying collectors,
    derived pointers pose an additional hazard that they may be invalidated at
    any `safe point`_. This term is used in opposition to `object pointer`_.

**DSA**
    数据结构分析

**DSE**
    死存储清除

F
-

**FCA**
    First Class Aggregate

**FDE**
    Frame Description Entry. A kind of CFI used to describe the stack frame of
    one function.

G
-

**GC**
    Garbage Collection. The practice of using reachability analysis instead of
    explicit memory management to reclaim unused memory.

**GEP**
    ``GetElementPtr``. 一个用于计算复合型数据结构中某个成员的地址的LLVM IR指令。在描述的很详细
    `这里 <http://llvm.org/docs/GetElementPtr.html>`_.

**GVN**
    Global Value Numbering. GVN is a pass that partitions values computed by a
    function into congruence classes. Values ending up in the same congruence
    class are guaranteed to be the same for every execution of the program.
    In that respect, congruency is a compile-time approximation of equivalence
    of values at runtime.

H
-

.. _heap:

**Heap**
    In garbage collection, the region of memory which is managed using
    reachability analysis.

I
-

**IPA**
    Inter-Procedural Analysis. Refers to any variety of code analysis that
    occurs between procedures, functions or compilation units (modules).

**IPO**
    Inter-Procedural Optimization. Refers to any variety of code optimization
    that occurs between procedures, functions or compilation units (modules).

**ISel**
    Instruction Selection

L
-

**LCSSA**
    Loop-Closed Static Single Assignment Form

**LGTM**
    "Looks Good To Me". In a review thread, this indicates that the
    reviewer thinks that the patch is okay to commit.

**LICM**
    Loop Invariant Code Motion

**LSDA**
    Language Specific Data Area.  C++ "zero cost" unwinding is built on top a
    generic unwinding mechanism.  As the unwinder walks each frame, it calls
    a "personality" function to do language specific analysis.  Each function's
    FDE points to an optional LSDA which is passed to the personality function.
    For C++, the LSDA contain info about the type and location of catch
    statements in that function.

**Load-VN**
    Load Value Numbering

**LTO**
    Link-Time Optimization

M
-

**MC**
    Machine Code

N
-

**NFC**
  "No functional change". Used in a commit message to indicate that a patch
  is a pure refactoring/cleanup.
  Usually used in the first line, so it is visible without opening the
  actual commit email.

O
-
.. _object pointer:
.. _object pointers:

**Object Pointer**
    A pointer to an object such that the garbage collector is able to trace
    references contained within the object. This term is used in opposition to
    `derived pointer`_.

P
-

**PR**
    Problem report. A bug filed on `the LLVM Bug Tracking System
    <https://bugs.llvm.org/enter_bug.cgi>`_.

**PRE**
    Partial Redundancy Elimination

R
-

**RAUW**

    Replace All Uses With. The functions ``User::replaceUsesOfWith()``,
    ``Value::replaceAllUsesWith()``, and
    ``Constant::replaceUsesOfWithOnConstant()`` implement the replacement of one
    Value with another by iterating over its def/use chain and fixing up all of
    the pointers to point to the new value.  See
    also `def/use chains <ProgrammersManual.html#iterating-over-def-use-use-def-chains>`_.

**Reassociation**
    Rearranging associative expressions to promote better redundancy elimination
    and other optimization.  For example, changing ``(A+B-A)`` into ``(B+A-A)``,
    permitting it to be optimized into ``(B+0)`` then ``(B)``.

.. _roots:
.. _stack roots:

**Root**
    In garbage collection, a pointer variable lying outside of the `heap`_ from
    which the collector begins its reachability analysis. In the context of code
    generation, "root" almost always refers to a "stack root" --- a local or
    temporary variable within an executing function.

**RPO**
    Reverse postorder

S
-

.. _safe point:

**Safe Point**
    In garbage collection, it is necessary to identify `stack roots`_ so that
    reachability analysis may proceed. It may be infeasible to provide this
    information for every instruction, so instead the information may is
    calculated only at designated safe points. With a copying collector,
    `derived pointers`_ must not be retained across safe points and `object
    pointers`_ must be reloaded from stack roots.

**SDISel**
    Selection DAG Instruction Selection.

**SCC**
    Strongly Connected Component

**SCCP**
    Sparse Conditional Constant Propagation

**SLP**
    Superword-Level Parallelism, same as :ref:`Basic-Block Vectorization
    <lexicon-bb-vectorization>`.

**Splat**
    Splat refers to a vector of identical scalar elements.

    The term is based on the PowerPC Altivec instructions that provided
    this functionality in hardware. For example, "vsplth" and the corresponding
    software intrinsic "vec_splat()". Examples of other hardware names for this
    action include "duplicate" (ARM) and "broadcast" (x86).

**SRoA**
    Scalar Replacement of Aggregates

**SSA**
    静态单赋值形式

**Stack Map**
    In garbage collection, metadata emitted by the code generator which
    identifies `roots`_ within the stack frame of an executing function.

T
-

**TBAA**
    基于类型的别名分析
