# Two_pass_Macro_Processor
Designed and implemented a two-pass macro processor in C, capable of expanding macro definitions in assembly language code.
Macro processors have been used for language expansion (defining new language constructs that can be expressed in terms of existing language components), for systematic text replacements that require decision making, and for text reformatting.

# Languages used:
 c
 
 Assembly(for input)

 # Data Structures
MACRO Definition table

MACRO Name Table

Argument Array List


# Pass 1 (Definition of MACROS)

Pass1 of macro processor makes a line-by-line scanover it's input.

Set MDTC = 1 and MNTC = 1.

Read next line of input program.

If it is a MACRO pseudo-op, the entire macro definition except MACRO line is stored in MDT.

The name is entered in the MNT along with a pointer to the 1st location of MDT entry.

When the END pseudo-op is encountered all the macro-definitions have been processed, so control is transferred to pass2.

# Pass 2 (Replacing MACRO calls by its definition)
This algorithm reads one line of i/p program at a time.

For each line it checks if op-code of that line matches any of the MNT entry.

The initial value of MDTP is obtained from MDT index field of MNT entry.

The macro expander prepares the ALA consisting of a table of dummy argument indices and corresponding arguments to the call.

The value from the argument list is substituted for dummy arguments indices in the macro definition table.

Reading MEND line in MDT terminates expantion of macro and scanning continues in the input file.

When END pseudo-op is encountered, the expanded source program is given to the assembler.
