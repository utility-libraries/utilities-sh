# textwrap utilities

Usage: `cat {input-file} > ./textwrap {command} > {output-file}`

```
usage: textwrap [-h] {fill,dedent,indent,shorten} ...

positional arguments:
  {fill,dedent,indent,shorten}
    fill                Reformat 'text' to fit in lines of no more than 'width' columns
    dedent              Remove any common leading whitespace from every line in text
    indent              Adds 'prefix' to the beginning the lines in 'text'
    shorten             Collapse and truncate the given text to fit in the given width

options:
  -h, --help            show this help message and exit
```

## `textwrap fill [-w WIDTH] [--tabsize TABSIZE]`

```
usage: textwrap fill [-h] [-w WIDTH] [--tabsize TABSIZE]

options:
  -h, --help            show this help message and exit
  -w WIDTH, --width WIDTH
                        Maximum width of the lines
  --tabsize TABSIZE     number of spaces a \t gets expanded to
```

## `textwrap indent [-p PREFIX]`

```
usage: textwrap indent [-h] [-p PREFIX]

options:
  -h, --help            show this help message and exit
  -p PREFIX, --prefix PREFIX
                        to be added at the beginning of the lines
```

## `textwrap dedent`

```
usage: textwrap dedent [-h]

options:
  -h, --help  show this help message and exit
```

## `textwrap shorten [-w WIDTH] [-p PREFIX]`

```
usage: textwrap shorten [-h] [-w WIDTH] [-p PREFIX]

options:
  -h, --help            show this help message and exit
  -w WIDTH, --width WIDTH
                        Maximum width of the lines
  -p PREFIX, --prefix PREFIX
                        Adds 'placeholder' at the end if the text is truncated
```
