# 🖨️ ft_printf

> **A C reimplementation of `printf`, built as part of the 42 School curriculum.**
>
> This project explores variadic functions, format parsing, and writing formatted output while returning the number of characters printed.

## 🎯 About the project

`ft_printf` reads a format string, retrieves each matching argument with `stdarg.h`, prints the value, and returns the total output length. The implementation is packaged as the reusable static library `libftprintf.a`.

## ✨ Supported conversions

| Conversion | Output |
|---|---|
| `%c` | A character |
| `%s` | A string (`(null)` for a null pointer) |
| `%p` | A pointer address in hexadecimal with a `0x` prefix |
| `%d`, `%i` | A signed integer |
| `%u` | An unsigned integer |
| `%x`, `%X` | A lowercase or uppercase hexadecimal integer |
| `%%` | A literal percent sign |

## 🧠 Key concepts

- 🎭 Variadic arguments with `va_list`, `va_start`, `va_arg`, and `va_end`
- 🔎 Parsing a format string and dispatching to conversion functions
- 🔢 Converting signed, unsigned, hexadecimal, and pointer values to text
- 📏 Counting the characters written and returning the total
- 📦 Building a reusable static library with Make

## 🛠️ Requirements

- A C compiler such as `cc` or `gcc`
- `make`

## 🚀 Build

```bash
git clone <repository-url>
cd printf
make
```

The build creates `libftprintf.a` in the project directory.

## 💡 Example

```c
#include "ft_printf.h"

int main(void)
{
    int printed;

    printed = ft_printf("Hello, %s! Number: %d\n", "world", 42);
    return (printed < 0);
}
```

Compile your program with the library:

```bash
cc -Wall -Wextra -Werror -I/path/to/printf \
  main.c /path/to/printf/libftprintf.a -o app
```

Replace `/path/to/printf` with the directory containing `ft_printf.h` and `libftprintf.a`.

## 🧹 Makefile commands

| Command | Description |
|---|---|
| `make` | Build `libftprintf.a` |
| `make clean` | Remove object files |
| `make fclean` | Remove object files and the library |
| `make re` | Clean and rebuild |

## 🏅 42 evaluation

The project received a **successful score of 104/100**. The evaluation summary is included below.

![42 ft_printf evaluation result: successful, 104 out of 100](assets/ft_printf-evaluation.png)

## 👩‍💻 Author

**Sedef Akkaya**  
[GitHub](https://github.com/sakkayaa) · [LinkedIn](https://www.linkedin.com/in/sedef-akkaya-0a5580228/)

---

✨ *Parse the format. Print the value. Count every character.*
