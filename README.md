# utilities-sh
shell utility scripts

This project is meant as a container for utility-scripts that should work on any linux system out of the box.

Just select a script you want and copy it into your project.

For further information go into the scripts directory and read the README

## Templates

### [shell-cli-template](./shell-cli-template)

command-line-interface shell-script template

## Ready to go Scripts

### [http-serve](./http-serve)
Serve a folder in http-mode

## shell-utilities

### [template-replace](./template-replace)

```bash
cat {input-file} | ./template-replace --key val --key2 val2 ... > {output-file}
```

### [textwrap](./textwrap)

```bash
cat {input-file} | ./textwrap {fill,dedent,indent,shorten} ... > {output-file}
```
