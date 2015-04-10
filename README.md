Repeat
======

Tired of cliking the same spot on your screen again and again? Got bored of typing the same phrase over and over again during your day? Repeat yourself with some intelligence.

Features
=======
1. Record and replay computer activity.
2. Store recorded task and replay them later
3. Write your own task so you have more control over the computer.
4. Assign any arbitrary hotkey combination to activate a stored task.
5. Manage your Repeat tasks (either recorded or written)

Disclaimer
==========
1. This is not a password storage program. Source code written is not encrypted.
2. This program executes your own code. Use the advanced compile - replay feature carefully. Test your task before adding it to the list.

Known issues
============
1. Home/End buttons can only be used if numlocks is off
2. Some source code files are not getting cleaned up. However, they're all in the data/source folder
3. Python language is not fully supported. I'll have to write a better controller (mouse & keyboard) library for python.
4. If application is not initialized correctly, it may not exit and has to be killed
5. Does not catch error if same hotkey is being used for different tasks. (i.e. you are responsible for not violating your hotkey assignment)

How to
======
1. Record: Press record (default hotkey F9) to start recording and stop at any time by pressing the same button again (or press default recording button F9)
2. Replay: Press replay (default hotkey F11) to start replaying and stop at any time by pressing the same button again (or press default replay button F11)
3. Compile your code and play it: the buttons are right under the record and replay section. (F12 for play/stop compiled code)
4. Manage your tasks: using the buttons on the right hand side of the windows to Add, Override, Remove or Reorganize (move up/down) your tasks.
5. Change hotkey for your task: just left click on the hotkey column of your task's row in the table and input the new hotkey
6. Manage task group: click on the button next to Task group on the top right corner at any time to manage the task group.

Code examples
=============

Open Gmail and facebook (assume you're already in Firefox/Chrome)
-----------------------------------------------------------------
    /* Write your code beneath "Begin generated code" */
    controller.blockingWaít(100); //To make sure the hotkey has been fully released
    key.combination(VK_CONTROL, VK_T);
    key.type("gmail.com");
    controller.blockingWait(100);
    key.combination(VK_CONTROL, VK_T);
    key.type("facebook.com");

Open Microsoft Word (assume you're using Windows)
-------------------------------------------------
     /* Write your code beneath "Begin generated code" */
    controller.blockingWaít(100); //To make sure the hotkey has been fully released
    key.combination(VK_CONTROL, VK_R);
    controller.blockingWait(100);
    key.type("winword");
    key.type(VK_ENTER);

Type out 100! = 1 * 2 * 3 * ... * 100
-------------------------------------
    /* Write your code beneath "Begin generated code" */
    controller.blockingWait(100); //To make sure the hotkey has been fully released
    key.type("100! = ");
    for (int i = 1; i <= 100; i++) {
        key.type(i + "");
        if (i != 100)
            key.type(" * ");
    }

Libraries used
==============
1. jnativehook Global Hooks library at https://github.com/kwhat/jnativehook
2. Argo JSON library at http://argo.sourceforge.net/