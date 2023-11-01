# template-replace

Usage: `cat {input-file} > ./template-replace --key val --key2 val2 ... > {output-file}`

## usage

`app.conf.template`
```ini
[section]
location=${location}
```

`command-line`
```bash
cat app.conf.template > ./template-replace --location "/opt/program/" > build/app.conf 
```

`build/app.conf`
```ini
[section]
location=/opt/program
```

## configurations

`$TEMPLATE_REPLACE_STYLE`

```bash
cat input > TEMPLATE_REPLACE_STYLE="DEFAULT" ./template-replace --key value > output
```

styles:
- `DEFAULT`/`BASH`
  - `${key}`
- `DOUBLE`
  - `{{key}}`
- `SINGLE`
  - `{key}`

## (sub)command execution

you can directly invoke commands and insert the output into the template

> note: you can't use formatter on the output

```
${$:echo "Hello World"}
```

## variables

There are certain default variables

| name  | value                          |
|-------|--------------------------------|
| today | date today as isoformat string |
| now   | time now as isoformat string   |

otherwise you can use shell variables (`${$shell-variable}`)

or variables provided via `--key value` as command-line arguments

## formatting

you can specify a formatting option with `${key:fmt opt1 opt2 ...}`

formatting options:

### escape

Escapes special characters (`"`|`'`|`\t`|`\n`|...) in a string.

```
${key:escape}
```

### date

Format the value to a date

The value can either be a timestamp or either `$TEMPLATE_REPLACE_STRPTIME` (if available) or isoformat

```
${key:date [fmt]}
```

See [here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes) for information about the format.

### align

```
${key:align {left|center|right} size [fillchar]}
```

### dedent

Removes any common leading whitespace from every line in the text.

```
${key:dedent}
```

### indent

Adds 'prefix' to the beginning of every line in the text.

```
${key:indent [prefix]}
```

### trim

removes spaces and newlines on both sides or left/right

```
${key:trim [both|left|right]}
```

### ltrim

removes spaces and newlines one the left side

<small>Alias for `${key:trim left}`</small>

```
${key:ltrim}
```

### rtrim

removes spaces and newlines one the right side

<small>Alias for `${key:trim right}`</small>

```
${key:rtrim}
```
