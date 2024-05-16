# Libft - Tu Primera Librería en C

## Resumen

Bienvenido a tu primer proyecto en el cursus de 42: ¡crearás tu propia librería en C! Este proyecto te permitirá entender y reimplementar algunas de las funciones más utilizadas en C, creando así una librería personalizada que será de gran utilidad para tus futuros proyectos.

## Introducción

Programar en C puede resultar tedioso sin acceso a funciones comunes. Este proyecto no solo te enseñará cómo funcionan estas funciones y cómo implementarlas, sino que también te ayudará a familiarizarte con su uso. A lo largo de tu cursus, podrás enriquecer tu `libft`, pero asegúrate de que todas las funciones que utilices respeten las normas de cada proyecto.

## Parte 1 - Funciones de la libc

La primera parte de este proyecto es esencial, ya que sentará las bases de tu experiencia con el lenguaje C. Reimplementarás algunas de las funciones más comunes de la libc (biblioteca estándar de C). Estas funciones son fundamentales para la manipulación de cadenas, memoria y caracteres. Comprender cómo funcionan desde adentro te dará una ventaja significativa y profundizará tu comprensión del lenguaje.

Las funciones a reimplementar tienen los mismos prototipos y comportamientos que las originales, pero con el prefijo `ft_`. Aquí tienes la lista de las funciones que necesitas desarrollar:

- `ft_isalpha`: Comprueba si el carácter es una letra del alfabeto.
- `ft_isdigit`: Comprueba si el carácter es un dígito decimal.
- `ft_isalnum`: Comprueba si el carácter es alfanumérico.
- `ft_isascii`: Comprueba si el carácter es ASCII.
- `ft_isprint`: Comprueba si el carácter es imprimible.
- `ft_strlen`: Calcula la longitud de una cadena.
- `ft_memset`: Rellena una parte de la memoria con un valor específico.
- `ft_bzero`: Establece una parte de la memoria a cero.
- `ft_memcpy`: Copia una parte de la memoria a otra.
- `ft_memmove`: Mueve una parte de la memoria a otra, con seguridad para solapamientos.
- `ft_strlcpy`: Copia una cadena a otra, garantizando la terminación nula.
- `ft_strlcat`: Concatenar dos cadenas, garantizando la terminación nula.
- `ft_toupper`: Convierte un carácter a mayúsculas.
- `ft_tolower`: Convierte un carácter a minúsculas.
- `ft_strchr`: Localiza un carácter en una cadena.
- `ft_strrchr`: Localiza un carácter en una cadena (última ocurrencia).
- `ft_strncmp`: Compara dos cadenas de un número específico de caracteres.
- `ft_memchr`: Busca un carácter en una parte de la memoria.
- `ft_memcmp`: Compara dos partes de la memoria.
- `ft_strnstr`: Localiza una subcadena en una cadena.
- `ft_atoi`: Convierte una cadena a un número entero.

Para las siguientes funciones, utiliza `malloc()` para la gestión de memoria dinámica:

- `ft_calloc`: Asigna memoria para una matriz, inicializándola a cero.
- `ft_strdup`: Duplica una cadena en memoria dinámica.

Este primer paso es crucial, ya que estas funciones te proporcionarán una base sólida que podrás utilizar y extender en futuros proyectos de C.

## Parte 2 - Funciones Adicionales

En esta segunda parte, desarrollarás un conjunto de funciones que, o no están en la libc, o lo están pero de una forma diferente. Estas funciones adicionales te permitirán realizar operaciones más complejas y específicas que serán muy útiles en tus futuros proyectos.

#### ft_substr

**Prototipo:** `char *ft_substr(char const *s, unsigned int start, size_t len);`  
**Descripción:** Reserva (con `malloc`) y devuelve una substring de la string `s`. La substring empieza desde el índice `start` y tiene una longitud máxima `len`.

#### ft_strjoin

**Prototipo:** `char *ft_strjoin(char const *s1, char const *s2);`  
**Descripción:** Reserva (con `malloc`) y devuelve una nueva string, formada por la concatenación de `s1` y `s2`.

#### ft_strtrim

**Prototipo:** `char *ft_strtrim(char const *s1, char const *set);`  
**Descripción:** Elimina todos los caracteres de la string `set` desde el principio y el final de `s1`, hasta encontrar un caracter no perteneciente a `set`. La string resultante se devuelve con una reserva de `malloc`.

#### ft_split

**Prototipo:** `char **ft_split(char const *s, char c);`  
**Descripción:** Reserva (utilizando `malloc`) un array de strings resultante de separar la string `s` en substrings utilizando el carácter `c` como delimitador. El array termina con un puntero `NULL`.

#### ft_itoa

**Prototipo:** `char *ft_itoa(int n);`  
**Descripción:** Utilizando `malloc`, genera una string que representa el valor entero recibido como argumento. Los números negativos deben gestionarse.

#### ft_strmapi

**Prototipo:** `char *ft_strmapi(char const *s, char (*f)(unsigned int, char));`  
**Descripción:** Aplica la función `f` a cada carácter de la cadena `s`, pasando su índice como primer argumento y el propio carácter como segundo argumento. Se crea una nueva cadena (utilizando `malloc`) para recoger los resultados de las sucesivas aplicaciones de `f`.

#### ft_striteri

**Prototipo:** `void ft_striteri(char *s, void (*f)(unsigned int, char*));`  
**Descripción:** Aplica la función `f` a cada carácter de la string `s`, dando como parámetros el índice de cada carácter dentro de `s` y la dirección del propio carácter, que podrá modificarse si es necesario.

#### ft_putchar_fd

**Prototipo:** `void ft_putchar_fd(char c, int fd);`  
**Descripción:** Envía el carácter `c` al file descriptor especificado.

#### ft_putstr_fd

**Prototipo:** `void ft_putstr_fd(char *s, int fd);`  
**Descripción:** Envía la string `s` al file descriptor especificado.

#### ft_putendl_fd

**Prototipo:** `void ft_putendl_fd(char *s, int fd);`  
**Descripción:** Envía la string `s` al file descriptor dado, seguido de un salto de línea.

#### ft_putnbr_fd

**Prototipo:** `void ft_putnbr_fd(int n, int fd);`  
**Descripción:** Envía el número `n` al file descriptor dado.

## Parte Bonus

Si completas la parte obligatoria, puedes ir más allá con esta parte extra. Las funciones para manipular listas son extremadamente útiles y te permitirán manejar estructuras de datos más complejas. Utiliza la siguiente estructura para representar un nodo de tu lista:

```c
typedef struct s_list {
    void *content;
    struct s_list *next;
} t_list;

#### ft_lstnew

**Prototipo:** `t_list *ft_lstnew(void *content);`  
**Descripción:** Crea un nuevo nodo utilizando `malloc`. La variable `content` se inicializa con el contenido del parámetro `content`. La variable `next` se inicializa con `NULL`.

#### ft_lstadd_front

**Prototipo:** `void ft_lstadd_front(t_list **lst, t_list *new);`  
**Descripción:** Añade el nodo `new` al principio de la lista `lst`.

#### ft_lstsize

**Prototipo:** `int ft_lstsize(t_list *lst);`  
**Descripción:** Cuenta el número de nodos de una lista.

#### ft_lstlast

**Prototipo:** `t_list *ft_lstlast(t_list *lst);`  
**Descripción:** Devuelve el último nodo de la lista.

#### ft_lstadd_back

**Prototipo:** `void ft_lstadd_back(t_list **lst, t_list *new);`  
**Descripción:** Añade el nodo `new` al final de la lista `lst`.

#### ft_lstdelone

**Prototipo:** `void ft_lstdelone(t_list *lst, void (*del)(void *));`  
**Descripción:** Libera la memoria del contenido del nodo `lst` utilizando la función `del`, además de liberar el nodo. La memoria de `next` no debe liberarse.

#### ft_lstclear

**Prototipo:** `void ft_lstclear(t_list **lst, void (*del)(void *));`  
**Descripción:** Elimina y libera el nodo `lst` dado y todos los consecutivos de ese nodo, utilizando la función `del` y `free`. Al final, el puntero a la lista debe ser `NULL`.

#### ft_lstiter

**Prototipo:** `void ft_lstiter(t_list *lst, void (*f)(void *));`  
**Descripción:** Itera la lista `lst` y aplica la función `f` al contenido de cada nodo.

#### ft_lstmap

**Prototipo:** `t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));`  
**Descripción:** Itera la lista `lst` y aplica la función `f` al contenido de cada nodo. Crea una lista resultante de la aplicación correcta y sucesiva de la función `f` sobre cada nodo. La función `del` se utiliza para eliminar el contenido de un nodo, si es necesario.

## Consideraciones Finales

Este proyecto es una oportunidad increíble para sumergirse en el mundo de la programación en C. La construcción de tu propia librería te dará una comprensión profunda de cómo funcionan las funciones básicas y cómo puedes utilizarlas y adaptarlas para satisfacer tus necesidades.

Recuerda que la clave del éxito en este proyecto es la paciencia y la atención al detalle. Al reimplementar estas funciones, desarrollarás habilidades que te serán valiosas en todos tus futuros proyectos de programación. ¡Buena suerte y disfruta del proceso de aprendizaje!
