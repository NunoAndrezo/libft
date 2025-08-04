# 📚 libft – 42 Lisboa

> Reimplement the C standard library functions and add useful utilities—foundation for future 42 projects.

---

## 🧠 Project Overview

**libft** is your personal version of the C standard library. You will:

- Reproduce functions from `<string.h>`, `<stdlib.h>`, `<unistd.h>`.  
- Create additional helpers (e.g., linked list manipulators).  
- Adhere strictly to the 42 Norm (≤ 25 lines/function, ≤ 5 variables, ≤ 80 columns).  
- Ensure no memory leaks, no forbidden functions, and clean code.

This library becomes a dependency for all subsequent 42 projects.

---

## 🎯 Objectives & Requirements

Implement the following categories of functions:

1. **Memory**: `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memccpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`.  
2. **String**: `ft_strlen`, `ft_strlcpy`, `ft_strlcat`, `ft_strchr`, `ft_strrchr`, `ft_strncmp`, `ft_strdup`.  
3. **Character**: `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`, `ft_toupper`, `ft_tolower`.  
4. **Conversion**: `ft_atoi`, `ft_itoa`.  
5. **Output**: `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`.  
6. **Allocation**: `ft_calloc`.  
7. **Advanced String**: `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_strmapi`.  
8. **File Reading**: `get_next_line` *(Bonus)*.  
9. **Linked List**: `ft_lstnew`, `ft_lstadd_front`, `ft_lstsize`, `ft_lstlast`, `ft_lstadd_back`, `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`.

**Forbidden:** any other functions from libc (except those reimplemented), global variables, loops over file descriptors.

---

## ⚙️ Installation & Usage

### Build

```bash
git clone https://github.com/NunoAndrezo/libft.git
cd libft
make
```

Generates `libft.a` in the project root.

### Integration

In your next project's `Makefile`:

```makefile
LIBFT_DIR = ../libft
LIBFT = $(LIBFT_DIR)/libft.a

all: libft $(NAME)

libft:
	make -C $(LIBFT_DIR)

$(NAME): $(OBJS) $(LIBFT)
	$(CC) $(CFLAGS) $(OBJS) $(LIBFT) -o $(NAME)
```

---

## 🛠️ Function Usage Examples

```c
// ft_strjoin
char *s = ft_strjoin("Hello, ", "42!");  // s = "Hello, 42!"

// ft_split
char **arr = ft_split("a,b,c", ',');     // arr = ["a","b","c",NULL]

// ft_lstiter
void print_elem(void *content) { printf("%s\n", (char *)content); }
t_list *lst = ft_lstnew("one");
ft_lstadd_back(&lst, ft_lstnew("two"));
ft_lstiter(lst, print_elem);             // prints "one" then "two"
```

---

## 🔍 Testing & Validation

- **Norminette**  
    ```bash
    norminette .
    ```  
- **Valgrind**  
    ```bash
    gcc -g src/*.c && ./a.out && valgrind --leak-check=full ./a.out
    ```  
- Write a test suite covering edge cases (NULL pointers, empty strings, large allocations).

---

## 📚 Resources

- 📖 “The C Programming Language” by Kernighan & Ritchie  
- 🖥️ `<string.h>`, `<stdlib.h>`, `<unistd.h>` man pages  
- 🛠️ Norminette rules: https://github.com/42School/norminette  

---

## 👤 Author

**Nuno Andrezo**  
42 Lisboa Student  
🔗 GitHub: [@NunoAndrezo](https://github.com/NunoAndrezo)
