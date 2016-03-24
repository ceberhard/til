## How to check that a bash variable exists and has a value
To verify that a bash variable exists use:
```bash
if [[ -z $var ]]; then echo "var is unset"; else echo "var is set to '$var'"; fi
```

To verify that a bash variable exists and is non-empty use:
```bash
if [[ -z ${var+x} ]]; then echo "var is unset or empty"; else echo "var is set to '$var'"; fi
```

If your variable is a directory which needs to be created, then this will create that directory if the variable is set:
```bash
! [[ -z ${var_dir+x} ]] && mkdir -p ${var_dir}
```

### References:
http://stackoverflow.com/questions/3601515/how-to-check-if-a-variable-is-set-in-bash
