Download Link: https://assignmentchef.com/product/solved-cs2123-program-1-infix-to-postfix
<br>
Convert expressions that are in infix notation to postfix notation.  The expressions might contain parentheses and these operators:  =, ONLY, NEVER, AND, OR.  In program #2, you will evaluate that postfix expression. Examples:

<table width="623">

 <tbody>

  <tr>

   <td width="312"><strong>Infix </strong></td>

   <td width="312"><strong>Postfix </strong></td>

  </tr>

  <tr>

   <td width="312">RECIT = N</td>

   <td width="312">RECIT N =</td>

  </tr>

  <tr>

   <td width="312">RECIT = Y</td>

   <td width="312">RECIT Y =</td>

  </tr>

  <tr>

   <td width="312">PROF = CLARK</td>

   <td width="312">PROF CLARK =</td>

  </tr>

  <tr>

   <td width="312">PROF NEVER CLARK</td>

   <td width="312">PROF CLARK NEVER</td>

  </tr>

  <tr>

   <td width="312">PROF ONLY CLARK</td>

   <td width="312">PROF CLARK ONLY</td>

  </tr>

  <tr>

   <td width="312">PROF NEVER CLARK AND DEPT = CS</td>

   <td width="312">PROF CLARK NEVER DEPT CS = AND</td>

  </tr>

  <tr>

   <td width="312">RECIT = Y AND ( PROF = CLARK OR PROF = GIBSON )</td>

   <td width="312">RECIT Y = PROF CLARK = PROF GIBSON = OR AND</td>

  </tr>

 </tbody>

</table>







<h1>Precedence rules</h1>

<ul>

 <li>Evaluate contents in () before others</li>

 <li>=, NEVER, ONLY – high precedence</li>

 <li>AND, OR – lower precedence</li>

</ul>




<h1>Driver Program and your function in separate files</h1>

For this program, I provided a driver program which will invoke your function to convert from infix to postfix.   <strong>Your code</strong> <strong>must be placed in a separate file</strong>.

Why did I provide a driver program?

<ul>

 <li>Reduces the amount of code you have to write. This allows you to focus on the most important points.</li>

 <li>Teaches you what it is like to use code written by someone else.</li>

 <li>Shows you the value of programming standards.</li>

 <li>Provides a design which makes it easier for you to do this program. It is very helpful to have <strong>addPostfixOut</strong>, <strong>categorize</strong>, and <strong>getToken</strong>.</li>

</ul>

Why must you put your code in a separate file?

<ul>

 <li>In the <em>real </em>world, many programmers work on the same program. It is significantly easier to manage code when it is separated into many files.</li>

</ul>




<strong>Some Files for your use </strong>cs2123p1.h – include file for Program #1.  Please review this.

cs2123p1Driver.c – driver program that I provided.  It has several useful routines to help reduce your effort.  Please review this code.

p1Input.txt – input file containing infix expressions, one per text line.

p1Extra.txt – input expressions, one per text line.  This is used for extra credit.  Note that it also contains the expressions in p1Input.txt.

Makefile.txt – rename to simply Makefile, this will help you compile and link your code.

Note: some Internet browsers won’t allow .c and .h files to be downloaded.  To avoid that problem, I changed the file names to cs2123p1_h.txt and cs2123p1Driver_c.txt.  Please rename them.

<strong> </strong>

<h1>Your code</h1>

<ul>

 <li>Create your code in <strong>p1<em>abc123</em>.c</strong> (replace <em>abc123 </em>with your abc123 ID). It must not contain the code from the driver!!  Based on what the driver calls, you need to create (at least) this function:</li>

</ul>

int convertToPostfix(char *pszInfix, Out out)

It returns 0 if it converted successfully.  Otherwise, it returns a value which indicates an error in the infix expression (e.g., missing left paren, missing right paren).

It populates the <strong>out</strong> array using the addPostfixOut function (provided in the driver).

For <strong>modularity</strong>, you will need to divide convertToPostfix into multiple functions.

<ul>

 <li>To compile the driver, your code, and create an executable, use the <strong>make</strong> utility (see below).</li>

</ul>




<h1>Error Handling</h1>

<ul>

 <li>Your code must handle errors like the following: o Missing “(” o Missing “)” o Additional errors are handled for extra credit.</li>

 <li>When an error is encountered, your code for convertToPostfix should return a non-zero value to the driver. Your program must not terminate.</li>

</ul>




<h1>Requirements</h1>

<ol>

 <li>Your code must be written according to my programming standards.</li>

 <li>You should not have to modify cs2123p1Driver.c. If you want to modify it, please see me before you do that.</li>

 <li>See below for what to turn in via BlackBoard.</li>

 <li>The output should show a warning for each poorly formed expression, but do not terminate the program (simply skip to the next expression).</li>

 <li>Make certain you free up allocated memory (e.g., stack).</li>

 <li><strong>Modularity matters</strong>. You probably need to code more than just the convertToPostfix function.</li>

</ol>




<strong>Hint </strong>

The functions <strong>getToken</strong> and <strong>categorize</strong> are provided in the cs2123p1Driver.c.  These can greatly simplify your code.




<h1>Meaning of the = operator</h1>

<ul>

 <li>The “=” operator is interpreted as “is at least”. “PROF = CLARK” means the PROF attribute type must have a value of at least CLARK.   It may have other values in the data for a particular course.</li>

 <li>This meaning of “=” is much more important for program #2.</li>

</ul>




<strong>Extra Credit</strong> (10 pts + 100 / N)

<ul>

 <li>Extra credit is all or nothing. Your program must meet ALL requirements.</li>

 <li>You will <strong>not</strong> <strong>receive extra credit</strong> if your program is turned in <strong>late</strong>.</li>

 <li>N = the number of people who get it completely correct. For example, if only 4 people get the extra credit completely correct, they each receive an extra 35 points (10 + 100 / 4).</li>

 <li>The following errors must be detected: o Missing “(” — must also be handled for normal credit o Missing “)”   — must also be handled for normal credit o Missing operator o Missing operand</li>

 <li>You must also turn in your output for the extra credit input file.</li>

 <li>If your program does not follow my programming standards, it will not receive extra credit.</li>

</ul>




<h1>Compiling Using the make Utility</h1>

Before using the make utility, you must:

<ul>

 <li>Download the Makefile.txt file and rename it simply <strong>Makefile </strong>(i.e., remove the .txt suffix)</li>

 <li>Edit Makefile to change o with your abc123 id. Note that you are changing a <strong>.o </strong>file reference.  The make utility will automatically reference your .c file if you properly name the p1abc123.o file:</li>

</ul>

# Define the machine object files for your program

OBJECTS = p1abc123.o cs2123p1Driver.o

# Define your include file

INCLUDES = cs2123p1.h




# make for the executable p1: ${OBJECTS}

gcc -g -o p1 ${OBJECTS}




# Simple suffix rules for the .o

%.o: %.c ${INCLUDES}  gcc -g -c $&lt;




# Clean the .o files clean:

rm -f ${OBJECTS}

Based on the rules in the Makefile, when you tell make to make your executable, it will <strong>automatically compile</strong> your .c file and the driver .c file.  (For more information about the <strong>make</strong> utility, <a href="http://www.cs.utsa.edu/~clark/setup/UnixMakeUtility.pdf">click here</a><a href="http://www.cs.utsa.edu/~clark/setup/UnixMakeUtility.pdf">.</a>) make p1

Executing the p1 executable:

./p1 &lt; p1Input.txt




<strong>Turn in</strong> LastNameFirstName<strong>.zip</strong> containing

<ul>

 <li>Your include file (if it changed)</li>

 <li>Your p1<em>abc123</em>.c file.</li>

 <li>Your Makefile (since you changed it for your p1<em>abc123</em>.c).  The TA/grader will use your Makefile to make the code.</li>

 <li>Your output based on the data provided. If you did the extra credit, turn in the output for just the extra credit</li>

 <li>Also, provide a note to the TA on whether you did the extra credit.</li>

</ul>

<strong> </strong>