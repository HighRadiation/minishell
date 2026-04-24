# minishell

## What is minishell?

**minishell** was a project in the [42 School](https://42.fr) curriculum (now removed from the syllabus). Its goal was to write a small shell from scratch in C, closely mimicking the behaviour of **bash**.

### Project objectives

Students had to implement:

- **Command execution** – search and launch executables using the `PATH` variable, or with relative/absolute paths.
- **Command history** – navigable with the up/down arrow keys (via `readline`).
- **Redirections**
  - `<`  – redirect stdin from a file
  - `>`  – redirect stdout to a file (overwrite)
  - `>>` – redirect stdout to a file (append)
  - `<<` – here-doc: read input until a given delimiter
- **Pipes** (`|`) – connect the stdout of one command to the stdin of the next.
- **Environment variables** – expand `$VARIABLE` and `$?` (exit status of the last command).
- **Quoting rules** – single quotes preserve literal values; double quotes allow variable expansion.
- **Signals** – handle `Ctrl-C`, `Ctrl-D`, and `Ctrl-\` as bash does in interactive mode.
- **Built-in commands** implemented without calling external binaries:
  | Built-in | Description |
  |----------|-------------|
  | `echo`   | Print arguments (`-n` flag supported) |
  | `cd`     | Change the current directory |
  | `pwd`    | Print the current working directory |
  | `export` | Set or update environment variables |
  | `unset`  | Remove environment variables |
  | `env`    | Print the current environment |
  | `exit`   | Exit the shell with an optional status code |

### Skills practised

- Process management (`fork`, `execve`, `wait`)
- File descriptors and I/O redirection
- Parsing and lexing in C
- Memory management (no leaks allowed)
- Signal handling
