# template-replace

within your script you can either call it directly with `./template-replace` or load the functions with `source ./template-replace`.

## usage

`app.conf.template`
```ini
[section]
location=${location}
```

```bash
./template-replace --location "/opt/program/" app.conf.template build/app.conf 
```

```ini
[section]
location=/opt/program
```

## configurations

`$TEMPLATE_REPLACE_STYLE`

```bash
TEMPLATE_REPLACE_STYLE="DEFAULT" ./template-replace --key value input output
```

styles:
- `DEFAULT`/`BASH`
  - `${key}`
- `DOUBLE`
  - `{{key}}`
- SINGLE
  - `{key}`

## formatting

you can specify a formatting option with `${key:fmt opt1 opt2 ...}`

formatting options:

### escape

`"${key:escape}"` with `--location 'I said "hey"'` comes to `"I said \"hey\""`

### date

`${key:date fmt}`

See [here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes) for information about the format
