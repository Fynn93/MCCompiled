# Macros
Macros are a useful way to prevent a lot of repeated code. They work similarly to functions in regular programming but cannot return a value. You can still make an output preprocessor variable if you want, but it's not officially supported by macros.

## Usage
To create a macro, use the syntax `ppmacro <macro name> <args>`.
```
ppmacro deny message {
  select @s
  printp [color: RED]$message
}
```

After a macro is defined, you can run it by typing in the name and your inputs.<br />
To input a string with multiple words, you can surround it with `"`.
```
ppmacro deny "You can't buy that yet!"
```

# Recursive Macros
Macros *can* call themselves over again, but this is disabled by default to detect errors. Compile with `-r` to disable this recursion guard. After that you're free to call as many times in as you like. Remember that every recursion stacks onto how much memory is used by the application (which can get quite large).
