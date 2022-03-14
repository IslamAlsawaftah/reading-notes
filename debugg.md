### code not  always run as we expect, and for  me i spen a lot of time asking my self what is the problem, or why this happen, why this error arise. so instead of exhausted ourseleves thinking and losing time we should use debugging tool, or debugger. debugger used to trace our code to know where we mistaken, debugging tools often allow you to make temporary changes so you can continue running the program it's a skill that takes time and need practice to learn. you need to specify your problem before start debugging

### we ask ourselves those questions :
* What did you expect your code to do?

* What happened instead?
#### use  error (exception) while running the app

### enter debugging mode by using F5 (or the Debug > Start Debugging menu command or the Start Debugging button Start Debugging in the Debug Toolbar)
#### use breakpoints with the debugger to examine code more carefully.In Visual Studio, you can quickly set a breakpoint by clicking in the left margin next to a line of code. Or place the cursor on a line and press F9

### How to use the try/catch block to catch exceptions?
#### surround the code that might rise an error and then return message by catching this error

### CLR configuration:
- A Debug dialog box appears.
- The program stops execution and a dialog box with exception information appears.
- An error prints out to the standard error output stream.

### Example:
```
using System;
using System.IO;
public class ProcessFile
{
    public static void Main()
    {
        try
        {
            using (StreamReader sr = File.OpenText("data.txt"))
            {
                Console.WriteLine($"The first line of this file is {sr.ReadLine()}");
            }
        }
        catch (FileNotFoundException e)
        {
            Console.WriteLine($"The file was not found: '{e}'");
        }
        catch (DirectoryNotFoundException e)
        {
            Console.WriteLine($"The directory was not found: '{e}'");
        }
        catch (IOException e)
        {
            Console.WriteLine($"The file could not be opened: '{e}'");
        }
    }
}
```