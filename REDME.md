
# Log File Truncation Script

This guide provides step-by-step instructions to find the largest log file named `x.log` on your computer and truncate it to 100 lines using Bash commands.

## Step 1: Navigate to the Log Files Directory

Open a terminal window and navigate to the directory where you suspect the `x.log` file is located using the `cd` command:

```bash
cd /path/to/log/files/directory
```

Replace `/path/to/log/files/directory` with the actual path to the directory containing your log files.

## Step 2: Find the Largest Log File

Use the `du` (disk usage) command to find the sizes of all files in the directory and its subdirectories. Then, use `sort` to sort the results in descending order and `head` to display the largest file:

```bash
du -a | sort -n -r | head -n 1
```

This command will give you the largest file's size and path. If the largest file is indeed named `x.log`, proceed to the next step.

## Step 3: Truncate the Log File

To truncate the `x.log` file to 100 lines, use the `head` command to extract the first 100 lines and redirect the output back to the file. This will overwrite the file with the truncated content:

```bash
head -n 100 x.log > x.log.temp
mv x.log.temp x.log
```

This sequence of commands creates a temporary file with the first 100 lines of `x.log` and then renames the temporary file back to `x.log`, effectively truncating the original file.

## Step 4: Verify the Truncation

Use the `wc` command to count the lines in the truncated log file and confirm that it has been successfully truncated to 100 lines:

```bash
wc -l x.log
```

This command should output `100 x.log`, indicating that the file now contains 100 lines.

That's it! You've successfully found the largest log file named `x.log` and truncated it to 100 lines using Bash commands. Just make sure to replace `/path/to/log/files/directory` with the actual path to your log files directory and adapt the steps accordingly if the file is located in a different directory.
```
