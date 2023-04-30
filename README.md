Download Link: https://assignmentchef.com/product/solved-csc415-assignment-5-buffered-i-o-continued-buffered-write
<br>
This builds on assignment 2 (the buffered read assignment). In this assignment you are adding b_write. The prototypes for these functions must be in a file called b_io.h (provided).

You will be just writing one function and modifying another of the functions in b_io.c from your Assignment 2. If you feel your assignment 2 is good, please use that, otherwise I have provided a version of b_io.c for you to start with.

int b_open (char * filename, int flags); //modified to accept flagsint b_write (int fd, char * buffer, int count);Your functions here will only use Linux I/O APIs. i.e. read, write, open, close (do not use the c library file functions).

The b_open should return a integer file descriptor (a number that you can track the file). You may want to also allocate the 512 byte buffer you will need for read operations here. Make sure though you know how to track the buffer for each individual file. You can return the same error code you receive if the Linux open returns an error.

The b_write takes a file descriptor, a buffer and the number of bytes to be written. The Operation of your b_write function must only write 512 bytes chunks at a time to the operating system from your own buffer, you will need to copy the appropriate bytes from the caller’s buffer to your buffer. This means you may not even need to do a write to the actual file if your buffer is not yet full. Or, it may mean that you have a full buffer to write, then additional bytes to buffer from the caller’s buffer.The return value is the number of bytes you have transferred from the caller’s buffer.Hint: You may also need to track between calls where in the buffer you left off.

Limits: You can assume no more than 20 files open at a time.

Your main program is provided for you, please rename the file from Bierman_Robert_HW5_main.c to the appropriate naming for you. You are provided the file DecOfInd.txt as the file to read. The output file is nicely formatted in 75 or less character lines. The file ProvidedClean.txt provided is the correct output.

You should submit your source code file(s), Makefile, and a copy of Clean.txt (output file) along with a short writeup in PDF format that includes a description of what you did and the compilation and execution output from your program in GitHub, and the PDF in iLearn.

Your main program filenames should be &lt;lastname&gt;_&lt;firstname&gt;HW&lt;#&gt;_&lt;optional&gt;.&lt;proper extension&gt;