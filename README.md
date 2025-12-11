🐚 minishell — A Tiny Shell in C  
────────────────────────────────────────────────────────────────────

**minishell** is a team project developed as part of the 42 Wolfsburg curriculum.
In this project, we divided responsibilities and, together with Max Hromylo, created a fully functional command-line interpreter inspired by Bash.

The goal of the project is to recreate the core behavior of a real shell from scratch: command parsing, handling of redirections and pipes, environment variable expansion, process execution, and signal management.


📌 Project Overview  
────────────────────────────────────────────────────────────────────

Your shell must:

	• Display a prompt and wait for user input  
	• Parse and execute commands  
	• Support pipes and redirections  
	• Handle environment variables  
	• Run built-in commands  
	• Manage signals like Bash  
	• Launch executables via PATH or absolute paths  

At most *one* global variable is allowed — and only to store the last received signal.


🧠 Core Features  
────────────────────────────────────────────────────────────────────

Your minishell must handle:

### 📂 1. Command Execution
	• Search executables using PATH  
	• Execute relative / absolute paths  
	• Correct process forking and waiting  

### 🔧 2. Built-ins
	• echo   (-n)  
	• cd     (relative or absolute)  
	• pwd  
	• export  
	• unset  
	• env  
	• exit  

### 🔀 3. Pipes
	`cmd1 | cmd2 | cmd3`  
Each command’s output becomes the next command’s input.

### 📥📤 4. Redirections
	<   input redirection  
	>   output redirection  
	>>  append mode  
	<<  heredoc (no history update required)

### 💲 5. Environment Variables
	$VARIABLE    → expand to value  
	$?           → last command exit status  

### 🧵 6. Quotes
	'...' → literal text, no expansions  
	"..." → expands $, but preserves text  

### 🛑 7. Signal Handling
Interactive mode must behave like Bash:

	ctrl-C → new prompt  
	ctrl-D → exit shell  
	ctrl-\ → ignored  


🧰 Allowed Functions  
────────────────────────────────────────────────────────────────────

	• readline, add_history, rl_*  
	• fork, wait, waitpid, execve  
	• pipe, dup, dup2  
	• open, close, read, write, access  
	• getcwd, chdir, stat, lstat, fstat  
	• signal, sigaction, kill  
	• getenv  
	• opendir, readdir, closedir  
	• tcsetattr, tcgetattr, isatty  
	• malloc, free, exit  
	• strerror, perror  
	• printf (not ft_printf!)  

Libft **is allowed**.


⚙️ Compilation  
────────────────────────────────────────────────────────────────────

The Makefile must include:

	make        → compile minishell  
	make clean  → remove object files  
	make fclean → remove all + executable  
	make re     → rebuild everything  

To launch the shell:

	./minishell


🧩 Program Structure  
────────────────────────────────────────────────────────────────────

A typical minishell architecture includes:

	• Lexer → splits input into tokens  
	• Parser → builds command structures  
	• Executor → handles forks, pipes, redirections  
	• Built-ins module  
	• Environment variable store  
	• Signal handler module  
	• Memory cleanup system  

📖 Requirements  
────────────────────────────────────────────────────────────────────

✔ Follows the 42 Norm  
✔ No memory leaks (except readline internals)  
✔ No crashes or unexpected behavior  
✔ Only one global variable allowed  
✔ Behavior must mimic Bash when possible  


🎯 Status  
────────────────────────────────────────────────────────────────────

This project provides deep understanding of how shells, processes, and file descriptors work — one of the most complex and rewarding challenges of the 42 curriculum.


👥 Team  
────────────────────────────────────────────────────────────────────

	This project was completed as a **team project of two students**:

	• Oleksandr Churko — 42 Wolfsburg 🇩🇪  
	• Max Hromylo — 42 Wolfsburg 🇩🇪
