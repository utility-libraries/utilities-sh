# template-replace

Usage: `cat {input-file} > ./template-replace --key val --key2 val2 ... > {output-file}`

## usage

`app.conf.template`
```ini
[section]
location=${location}
```

```bash
cat app.conf.template > ./template-replace --location "/opt/program/" > build/app.conf 
```

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

## formatting

you can specify a formatting option with `${key:fmt opt1 opt2 ...}`

formatting options:

### escape

`"${key:escape}"` with `--key 'I said "hey"'` comes to `"I said \"hey\""`

### date

`${key:date [fmt]}`

See [here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes) for information about the format

### align

`${key:align {left|center|right} size [fillchar]}`
