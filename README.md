My name is Michael Uhlenberg. I am a (meanwhile retired) programmer.
I was born 1953 in Hamburg, Germany. I spent my childhood mainly in Wolfsburg,
studied in Braunschweig, got a degree in Computer Science (Diplom-Informatiker) in 1977,
moved to München (Munich) to start work at Siemens, then PCS, then IXOS, then Opentext, then retired.

# Studying #
## Philips X1 ##
My very first experience with computers is from around 1969, where I took a Fortran course. While studying,
I had access to a Philips Elektrologica X1 machine, which had an Algol 60 compiler on two reels of ticker tape.
The first reel was pass 1 of the compiler. You had to read in this reel, then your program on ticker tape, then the second reel with pass2.
Then you could run your program. You had to provide data on another piece of ticker tape, and you could watch your program reading your tape.
There was also a tape punch on which you could write the output data, or print to a IBM Selectric ball head typewriter.
The program and data tapes were punched on a teleprinter. Editing meant to duplicate a tape up to a certain point, then 
inserting new characters or skipping characters, then continue duplicating, and so on. Or you took scissors to cut your tape, 
and put another piece of tape in between, with the help of scotch tape.
## ICL 1900 ##
As a graduate student I had access to a real mainframe, an ICL 1900, which offered 24 bit words, card readers, line printers, tape drives,
and magnetic disks. I remember the day when a heavy piece of equipment was lifted by a crane through a window into the computer centre. 
That was a storage epansion of 256k words, i.e. 3*256k bytes. Amazingly, the computer had an Algol 68 compiler, by the British Royal Radar Establishment. 
My diploma thesis was an Algol68 program that implemented a small relational database based on k-d-trees. 
## 8-bit microprocessor ##
I also programmed on some 8-bit microprocessors, perhaps 6502,
on which I used emulated 16-bit-arithmetic to implement digital filters. They were very slow, however.
## ICL 2900 ##
In the last year the computer centre bought an ICL 2900 machine. This was a very advanced machine, with lots of advanced concepts. There is a Wikipedia article for it.
# Siemens #
## Prisma, BS1000
I started work in a group working on a hierarchical database system called Prisma. You could write programs for it in assembly language. 
A colleague in a research lab of Siemens had developped a macro preprocessor (called Columbus) for the assembly code, so that you could use 
if-then-else or while-do statements in the code, instead of jump instructions. I programmed an interpreter with that, 
so that I could write test code in a small language that exercised the database. In this way you could write test code much faster than by writing assembly code.
Prisma worked on a Siemens mainframe with the operating system BS1000. This was a very cumbersome OS at that time, and a real pain to use. If you wanted to use a computer,
you had to apply for a time slot, often in the middle of the night. When your time slot was near, you moved to the machine with your magnetic discs, inserted them in the drives,
and you could use the machine all by yourself, during the time slot. After the ICL machines this was a real culture shock for me.
## Research, Pascal, 8-bit
After a year or so I moved to a central research lab, where the aforementioned Columbus programmer was now my colleague. He had written or ported a Pascal compiler to a 8-bt
microprocessor with 64kb memory, which was quite a lot. The compiler produced P-code, like Java bytecode, 
and there was a P-code-interpreter on the microprocessor. My first job was to write a post mortem dump analyzer. When the program crashed, 
the PMD analyzer produced a stack trace with line numbers and variable contents. Debuggers did not exist. Later, the interpreter was enhanced to implement something
like virtual memory. I.e. the program could be larger than 64k minus the interpreter size, and the interpreter would page in and out data as needed. 
But this affected the program speed badly. 
## C, Unix, PDP11 ##
Therefore, we were very excited when we learned about 16-bit machines, like the PDP11. We got one, 
and on it we could run an OS called Unix! It's source code was printed on a few pages, in a language called C. Later, the Unix versions were called V6 and V7.
The PDP11 had 8 segments of 8k, if I remember correctly, doubled for system and user space. The Unix programs ran in segmented space, but there was no paging yet.
## M68000 ##
Then there appeared several 32-bit microprocessors: the 80286, the Zilog Z8000, and the Motorola M68000. We liked the 68000 best. 
We found a nearby hardware company, PCS, that attached a memory management unit to the 68000, similar to the PDP11, and I embarked on a Unix port to this machine.
For this, I took an existing C compiler and rewrote the backend to produce 68000 code. The compiler ran on a Digital VAX. 
First I wrote a large program that consisted of a Unix kernel with some utilities like shell, cp, mv, ftp and so on all compiled into one binary. 
This program was then used to bootstrap Unix onto the machine.
## M68020, PCS ##
The 68020 had a real mmu. In the meantime we had also access to Unix code for the VAX, that supported virtual memory with paging, and we ported this code to the 68020.
Sun did the same on their machines, and eventually there were a number of vendors selling Unix machines based on 32-bit microprocessors. Unfortunately, 
Siemens had an official strategy of supporting Intel only, and our Motorola efforts were not well looked at. So a few colleagues and I moved to the PCS company. 
For a couple of years PCS produced UNIX workstations based on Motorola, Intel 432 and Digital Alpha, but the competition eventually became ovewrwhelming. 
And then of course appeared the IBM PC. PCS and many other companies disappeared or stopped producing Unix workstations. Nevertheless, one could say that these were
the best days of my life, at least as far as the work is concerned. I stopped working as a hardware oriented guy, developping drivers and adapting to new machines, 
frequently sitting with the hardware engineers in front of a digital analyzer.
## IXOS, Opentext, Archives ##
One of the PCS founders had founded a new software company called IXOS. When I joined the company, it was doing projects and courses. 
But then it started to develop products, in the archive field. We stored files on first WORMs, later CDs or DVDs, located in jukeboxes. 
There was a database that recorded which file was on which medium. WORMs were written filewise, CDs/DVDs had to be "burned" as a whole.
Several years later, disk space had become so large, that the need for optical storage and thus jukeboxes had disappeared. Instead, files had to be written to cloud storage.
IXOS was eventually aquired by Opentext. As a developer I moved from C to Java, using C only for low level interface code. Security became more and more important.
Also, while at the beginning it was most important never to loose any files, at the end it was very important to delete files after their retention period.
For some years I fought against software patents,in vain. And I could watch how development was more and more influenced by legal aspects.
Every now and then the management came up with new tools, that scanned code I had written in many years, and produced hundreds of messages, 
mostly irrelevant, but the management always looks at numbers, and wants them to be zero. Our programs were based on dozens of third-party packages. 
Once I counted more than 600 DLLs attached to our program. Always a lot of them were out of date, and worse, appeared in CVEs. This grew worse every year, 
and still you were expected not only to maintain your old code, but produce new code as well. Also, we started to use Scrum, or what the management thought Scrum was.
For us it mostly meant standups and two-week sprints. On each sprint you started, became faster, were fast, slowed down and stopped. No more "flows" over a longer period.
Scrum notwhithstanding, deadlines were fixed. Someone told you what you had to do in the next sprint. Not more, not less. Especially not more. 
When you were ready early, you were not allowed to do something more, because it produced a greater load on the test crew. You could only develop as much as the test
crew said it can handle. I was glad when the time of retirement had come.
## Currently ##
I still like to program. I am amazed how much excellent software there is, and all of it for free. Like Visual Studio Code, Arduino, Eclipse, Python, Javascript, Node, Go, Vue, Typescript, Svelte, Django and many more. I produced some apps using Python/Kivy or Dart/Flutter. I wrote scripts for Google Forms and Sheets. I have a Raspberry Pi 3B running Mysql, Django, SQLAlchemy. All to be found here on Github.
