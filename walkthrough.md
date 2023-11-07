After running the Javascript code, use the following to improve your terminal if you are getting double typed charecters.

1. On your reverse shell, background the process by pressing `Ctrl-Z`. This will put the shell in the background and return you to your local shell.

2. In your local shell, disable local echo by running:

   ```sh
   stty raw -echo
   ```

   This command sets the terminal to raw mode and turns off local echo, which means that your local terminal will no longer echo back what you type.

3. Now foreground the reverse shell process with:

   ```sh
   fg
   ```

   This will return you to the reverse shell.

4. Finally, in the reverse shell, reset the terminal by typing:

   ```sh
   reset
   ```

   You might not see the characters you type to input this command due to the terminal settings, but just type it and press enter.

   Then you can export the terminal variable:

   ```sh
   export TERM=xterm
   ```

   And if necessary, adjust the rows and columns to match your current terminal:

   ```sh
   stty rows <num> columns <cols>
   ```

   You can find out the number of rows and columns by running `stty size` in your local terminal before you start the reverse shell process.

5. If you're still experiencing issues, you can also try using `rlwrap` with the `nc` listener command on your local machine:

   ```sh
   rlwrap nc -lvnp <port>
   ```

   `rlwrap` can provide a more stable input environment for network connections that are acting as shells.

Make sure that when you resume the session with `fg`, you're not pressing any keys until you've finished typing the `reset` command and pressed Enter. This ensures that the terminal settings are applied correctly without additional keystrokes causing issues.


$2a$12$SOn8Pf6z8fO/nVsNbAAequ/P6vLRJJl7gCUEiYBU2iLHn4G/p/Zw2
