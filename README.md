# MIE250 Lab: Week 2 (github basics, Eclipse/Java basics, HelloWorld)

Lab assignment for Week 2 (week starting Sept 9, 2019).

In this lab we will check out a lab assignment as a private github repository, build a HelloWorld program in a Java IDE, add this content to the github repository, and commit/push it to the github remote server so that it can be picked up by the auto-grading scripts.

Note that while this lab is not graded, we will provide auto-grading feedback (deposited directly in your repository) that is committed to your repository to allow you to confirm that you completed and submitted the lab correctly.  

Note: we cannot autograde your project until we know your github username, so please signup here: https://forms.gle/RkxDq19jqn8kJpHL8

1. When logged into github, the link to the github MIE250 repo allows you to create a private repository for MIE250 and will provide the <REPO_URL> to this repository once it is created (keep track of this <REPO_URL> since we'll use it later).

2. Start "Git Bash" (a UNIX-style bash shell for Windows to run git commands) and on ECF "cd /w/" to get to your personal home directory (accessible from any Windows ECF machine).

   If not already done, we suggest you also type "mkdir MIE250" that will make a subfolder "/w/MIE250/" where all of your work in this course can be stored separately from other courses.  Then "cd /w/MIE250/".

   **NOTE 1:** You are responsible for bookmarking the following page as a reference for commands you can use from "Git bash": <https://ss64.com/bash/>  This is a generic UNIX bash commands reference and not all commands are found in Git's version of bash, *but* most file-based commands listed here work.  Click the link (e.g., see "cp", "cd", "ls", "pwd" for common commands) to see example command usage.  You will need some of these in later projects and you will see UNIX commands again in your career.  And yes: you are expected to be able to make use of reference documentation like this in the course (as you would in any future job).

   **NOTE 2:** There are many github/git tutorials on the web, especially useful if collaborating on a software project with a team.  For the most part we'll be only using a few basic git commands (git clone, git status, git add, git commit, and git push), but here is a link to some documentation that you should go through to understand github and git better: <https://try.github.io/>

3. Once your private repository has been created in step 1 and you have navigated to the correct directory in "Git Bash" in step 2, you can use "Git Bash" to run **"git clone <CLONE_URL>"** from the <CLONE_URL> provided at the repository REPO_URL from step 1 (just click the "Clone or Download" button at <REPO_URL>, click "Use https", and copy the provided https <CLONE_URL>).  Once copied, usually a mouse middle click will paste into a "Git Bash" shell.  Do not include the '<' and '>', this notation is just to indicate something that should be substituted with the actual string.

   If "git clone <CLONE_URL>" runs correctly, you should now have a subdirectory in your current directory corresponding to the repository content.  You can change directories with "cd" and see directory contents with "ls" or "ls -la" for more information.  See reference documentation provided above.

4. Now we're finally ready to code!  Use the Eclipse IDE to add and edit Java files to the directory where the repository is stored.  Also use the IDE to run and debug your Java code.  

   Eclipse is a little different in every version, so you may need to adapt the instructions here to your installation.  TAs can assist with the procedure for the specific Eclipse version in the ECF labs.  From the File menu, I select new and then "Java Project", uncheck the "default location" and browse for the file system location of labweek2 cloned from github... when this "labweek2" directory is selected, Eclipse should automatically make the Project name "labweek2".  From there the default settings should work (Eclipse should recognize "src" as the source package and suggest "bin" as the output folder for compilation).  Verify the configuration looks right and click Next/Finish as needed.  If everything is correct, the existing "src/HelloWorld.java" should compile without errors.  Once you add a "main" class (as covered in the lab), you can then right click on the file and select "Run as Java Application" to run it within Eclipse.

   Specifically for this lab, you should edit src/HelloWorld.java so that it prints "Hello World" when run.  The file should compile to bin/HelloWorld.class (the IDE will handle the compilation for you).  The TAs will tell you exactly what to type for the solution during lab, but try some Googling to see if you can get the answer yourself before you are told!
   
   **COMMON ERROR:** If the Eclipse project is loaded and configured correctly, any file directly under the src/ directory **should not** have a package declaration such as "package src;" as the first non-comment line since this is supposed to be the default package and should thus not have a package declaration.  If you see the "package src" declaration anywhere in your Java project files, something is wrong because "src" is **not** a package name you should ever see in a Java file, but rather the name of the directory containing the default package and subpackages.  If this happens, you loaded the Eclipse project incorrectly.  Sometimes you need to delete .project and .classpath from your "labweek2" directory before trying to reload a project in Eclipse, otherwise it remembers your last configuration and repeats it.

5. Once you think you have the solution, you should go back to the "Git bash" command line to check your solution against the reference solution.  **In all MIE250 projects**, there will always be a reference solution provided in the directory "soln" with the name "soln.jar".  This is file contains a compiled solution with all classnames that should be in your solution, except that they are prefixed with the package name "soln".  (You can add "soln.jar" to your library path when you create the Eclipse project so you can access these classes from your code; this will be important in later projects.)  To compare your solution and the reference solution from the command line, do the following:

  **YOUR SOLUTION:** Any Java files under the src/ directory are compiled and placed in the bin/ directory so you have to run your solution from the /bin directory.  Using "cd" in "Git Bash" (use "pwd" to print the current working directory and "cd .." to go up one directory), navigate to the "bin" folder of the project.  If Eclipse compiled the file correctly, you should see HelloWorld.class when you type "ls".  To run this class, type **"java -cp . HelloWorld"**.  This tells the java command that it should search for classes in the current directory "." and run the class with the name "HelloWorld".  Consult TAs if this does not work for you.
  
  **REFERENCE SOLUTION:** Using "Git Bash", now navigate to the "soln" directory.  You should find "soln.jar" in this directory.  Type **"java -cp soln.jar soln.HelloWorld"**.  This tells the java command that it should search for classes in the jar file "soln.jar" and run the class with the name "soln.HelloWorld", that is the class "HelloWorld" in the package "soln".  Remember that the solution classes will always be prefixed in this course with "soln".

6. Now that you've checked out the repository and created a solution to the lab assignment in this repository, we just have to ensure this solution gets transmitted to the remote github repository for MIE250 so it can be autograded.

   To see what files or directories are not currently under version control, type "git status".  To add these files or directories, from the "Git Bash" shell, use "git add <FILE_OR_DIR>".  **Note that you should "git add ..." files under src/ but not files under bin/... we will compile your code from the source code.**
   
   Now we're ready to transmit these changes (new or modified files) to your MIE250 remote github repository.  Type **"git commit -am '<UPDATE_MESSAGE>'; git push"**.  <UPDATE_MESSAGE> is just a note so you can keep track of the purpose of the commit... you can enter anything you want here.  You can now browse <REPO_URL> **from a web browser** to verify that all of your changes are there.  **If** everything runs correctly locally and you've verified that all local files (and their changes) appear at REPO_URL, you're almost done!

   **COMMON ERROR:** Make sure you use "git commit -am ..." and not just "git commit -m ...".  The "-a" is critical for ensuring all modified files are added to the commit.  You are free to do otherwise of course if you know what you are doing!

7. If everything looks correct and you **think** you are done, you must verify you can check out your repository and that it compiles and runs correctly (if not, the autograder will fail and you will get a 0).  To do this, clone your repository in a different temporary directory, load it into Eclipse and compile it, then navigate to this temporary directory from the "Git Bash" command line and run your code as noted above.  Verify that your code output matches the reference solution.  We'll give you more instructions on how to compare solutions with complex outputs in future projects, but here you can just eyeball the outputs to compare.

   **COMMON ERROR:** Make sure to delete any duplicate cloned repositories (e.g. those as used above for testing everything compiles correctly).  A common error in the course is that a student has more than one cloned repository in their local file system and edits code / commits from the wrong repository, or even worse, causes git to enter conflict resolution mode when commits are made from different repositories.  (In this case you need to read the git documentation to understand how to resolve conflicting commits.  It's a lot easier though if you avoid this to begin with!)

8. Note that the autograder for the course retrieves the last committed files from this repository before the deadline -- files that are not in this repository by the deadline will not be graded.  

**Please attend lab for a detailed walkthrough of this lab.  Ask questions where you don't understand and take careful notes.**
