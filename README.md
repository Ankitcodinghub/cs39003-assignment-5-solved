# cs39003-assignment-5-solved
**TO GET THIS SOLUTION VISIT:** [CS39003 Assignment 5 Solved](https://www.ankitcodinghub.com/product/compilers-laboratory-cs39003-solved-3/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113934&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS39003 Assignment 5 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
1 Preamble – tinyC

The Lexical Grammar (Assignment 3) and the Phase Structure Grammar (Assignment 4) for tinyC have already been defined as subsets of the C language specification from the International Standard ISO/IEC 9899:1999 (E).

In this assignment you will write the semantic actions in Bison to translate a tinyC program into an array of 3-address quad’s, a supporting symbol table, and other auxiliary data structures. The translation should be machine-independent, yet it has to carry enough information so that you can later target it to a specific architecture (x86 / IA-32 / x86-64).

2 Scope of Machine-Independent Translation

Focus on the following from the different phases to write actions for translation.

2.1 Expression Phase

Support all arithmetic, shift, relational, bit, logical (boolean), and assignment expressions excluding:

1. sizeof operator

2. Comma (,) operator

3. Compound assignment operators

*= /= %= += -= &lt;&lt;= &gt;&gt;= &amp;= ^= |=

Support only simple assignment operator (=)

4. Structure component expression

2.2 Declarations Phase

Support for declarations should be provided as follows:

1. Simple variable, pointer, array, and function declarations should be supported. For example, the following would be translated:

float d = 2.3; int i, w[10]; int a = 4, *p, b; void func(int i, float d); char c;

2. Consider only void, char, int, and float type-specifiers. As specified in C, char and int are to be taken as signed.

For computation of offset and storage mapping of variables, assume the following sizes (in bytes) of types:

void undefined

char 1

int 4

float 8

void * 4 All pointers have same size

void func(int i, float d); should be supported while

2.3 Statement Phase

Support all statements excluding:

1. Declaration within for.

2. All Labelled statements (labeled-statement).

3. switch in selection-statement.

4. All Jump statements (jump-statement) except return.

2.4 External Definitions Phase

Support function definitions and skip external declarations.

3 The 3-Address Code

Use the 3-Address Code specification as discussed in the class. For easy reference the same is reproduced here. Every 3-Address Code:

• Uses only up to 3 addresses.

• Is represented by a quad comprising – opcode, argument 1, argument 2, and result; where argument 2 is optional.

3.1 Address Types

• Name: Source program names appear as addresses in 3-Address Codes.

• Constant: Many different types and their (implicit) conversions are allowed as deemed addresses.

• Compiler-Generated Temporary: Create a distinct name each time a temporary is needed – good for optimization.

3.2 Instruction Types

For Addresses x, y, z, and Label L

• Binary Assignment Instruction: For a binary op (including arithmetic, shift, relational, bit, or logical operators):

x = y op z

• Unary Assignment Instruction: For a unary operator op (including unary minus or plus, logical negation, bit, and conversion operators):

x = op y

• Copy Assignment Instruction:

x = y

• Unconditional Jump: goto L

• Conditional Jump: – Value-based:

if x goto L ifFalse x goto L

– Comparison-based: For a relational operator op (including &lt;, &gt;, ==, ! =, ≤, ≥):

if x relop y goto L

• Procedure Call: A procedure call p(x1, x2, …, xN) having N≥ 0 parameters is coded as (for addresses p, x1, x2, and xN):

param x1 param x2 … param xN

y = call p, N

Note that N is not redundant as procedure calls can be nested.

• Return Value: Returning a return value and / or assigning it is optional. If there is a return value v it is returned from the procedure p as:

return v

• Indexed Copy Instructions:

x = y[z] x[z] = y

• Address and Pointer Assignment Instructions:

x = &amp;y x = *y *x = y

4 Design of the Translator

Attributes Design the attributes for every grammar symbol (terminal as well as nonterminal). List the attributes against symbols (with brief justification) in comment on the top of your Bison specification file. Highlight the inherited attributes, if any.

Symbol Table Use symbol tables for user-defined (including arrays and pointers) variables, temporary variables and functions.

Name Type Initial Size Offset Nested

Value Table

… … … … … …

For example, for

float d = 2.3; int i, w[10]; int a = 4, *p, b; void func(int i, float d); char c; the Symbol Tables will look like:

ST(global) This is the Symbol Table for global symbols

Name Type Initial Size Offset Nested

Value Table

d float 2.3 8 0 null

i int null 4 8 null

w array(10, int) null 40 12 null

a int 4 4 52 null

p ptr(int) null 4 56 null

b int null 4 60 null

func function null 0 64 ptr-to-ST(func)

c char null 1 64 null

ST(func) This is the Symbol Table for function func

Name Type Initial Size Offset Nested

Value Table

i int null 4 0 null

d float null 8 4 null

retVal void null 0 12 null

lookup(…) A method to lookup an id (given its name or lexeme) in the Symbol Table. If the id exists, the entry is returned, otherwise a new entry is created.

gentemp(…) A static method to generate a new temporary, insert it to the Symbol Table, and return a pointer to the entry.

update(…) A method to update different fields of an existing entry.

print(…) A method to print the Symbol Table in a suitable format.

Note:

• It should be easy to extend the Symbol Table as further features are supported and more functionality is added.

• The global symbol table is unique.

• Every function will have a symbol table of its parameters and automatic variables. This symbol table will be nested in the global symbol table.

• Symbol definitions within blocks are naturally carried in separate symbol tables. Each such table will be nested in the symbol table of the enclosing scope. This will give rise to an implicit stack of symbol tables (global one being the bottom-most) the while symbols are processed during translation. The search for a symbol starts from the top-most (current) table and goes down the stack up to the global table.

Quad Array The array to store the 3-address quad’s. Index of a quad in the array is the address of the 3-address code. The quad array will have the following fields (having usual meanings)

op arg 1 arg 2 result

… … … …

Note:

• result is variable (address) only.

For example, if

int i = 10, a[10], v = 5;

…

do i = i – 1; while (a[i] &lt; v);

translates to

100: t1 = i – 1 101: i = t1

102: t2 = i * 4

103: t3 = a[t2]

104: if t3 &lt; v goto 100

the quad’s are represented as:

Index op arg 1 arg 2 result

… … … … …

100 – i 1 t1

101 = t1 i

102 * i 4 t2

103 =[] a t2 t3

104 &lt; t3 v 100

emit(…) An overloaded static method to add a (newly generated) quad of the form: result = arg1 op arg2 where op usually is a binary operator. If arg2 is missing, op is unary. If op also is missing, this is a copy instruction.

print(…) A method to print the quad array in a suitable format.

void main()

{

int i = 10; int a[10]; int v = 5; int t1; int t2; int t3;

L100: t1 = i – 1; L101: i = t1;

L102: t2 = i * 4;

L103: t3 = a[t2];

L104: if (t3 &lt; v) goto L100;

}

Note:

makelist(i)

A global function to create a new list containing only i, an index into the array of quad’s, and to return a pointer to the newly created list.

merge(p1, p2)

A global function to concatenate two lists pointed to by p1 and p2 and to return a pointer to the concatenated list.

backpatch(p, i)

A global function to insert i as the target label for each of the quad’s on the list pointed to by p.

typecheck(E1, E2)

A global function to check if E1 &amp; E2 have same types (that is, if &lt;type of E1&gt; = &lt;type of E2&gt;). If not, then to check if they have compatible types (that is, one can be converted to the other), to use an appropriate conversion function conv&lt;type of E1&gt;2&lt;type of E2&gt;(E) or conv&lt;type of E2&gt;2&lt;type of E1&gt;(E) and to make the necessary changes in the Symbol Table entries. If not, that is, they are of incompatible types, to throw an exception during translation.

conv&lt;type1&gt;2&lt;type2&gt;(E)

A global function to convert an expression E from its current type type1 to target type type2, to adjust the attributes of E accordingly, and finally to generate additional codes, if needed.

5 The Assignment

1. Write a 3-Address Code translator based on the Flex and Bison specifications of tinyC. Assume that the input tinyC file is lexically, syntactically, and semantically correct. Hence no error handling and / or recovery is expected.

2. Prepare a Makefile to compile and test the project.

3. Prepare test input files ass5 roll test&lt;number&gt;.c to test the semantic actions and generate the translation output in ass5 roll quads&lt;number&gt;.out.

4. Name your files as follows:

File Naming

Flex Specification ass5 roll.l

Bison Specification ass5 roll.y

Data Structures (Class Definitions) &amp;

Global Function Prototypes ass5 roll translator.h

Data Structures, Function Implementations &amp; Translator main() ass5 roll translator.cxx

Test Inputs ass5 roll test&lt;number&gt;.c

Test Outputs ass5 roll quads&lt;number&gt;.out

5. Prepare a tar-archive with the name ass5 roll.tar containing all the files and upload to Moodle.

6 Credits

Design of Grammar Augmentations: 5

Explain the augmentations in the production rules in Bison

Design of Attributes: 5

Explain the attributes in the respective %token and %type in Bison

Design and Implementation of Symbol Table &amp;

Supporting Data Structures: 10

Explain with class definition of ST &amp; other Data Structures

Design and Implementation of Quad Array: 5

Explain with class definition of QA

Design and Implementation of Global Functions: 10

Explain i/p, o/p, algorithm &amp; purpose for every function

Design and Implementation of Semantic Actions:

Explain with every action in Bison

Expression Phase: 15

Correct handling of operators, type checking &amp; conversions

Declaration Phase: 10

Handling of variable declarations, function definitions in ST

Statement Phase: 15

Correct handling of statements

External Definition Phase: 5

Correct handling of function definitions

Design of Test files and correctness of outputs: 20

Test at least 5 i/p files covering all rules

Shortcoming and / or bugs, if any, should be highlighted
