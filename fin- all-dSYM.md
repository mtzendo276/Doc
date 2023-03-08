```bash
mdfind -name .dSYM | while read -r line; do dwarfdump -u "$line"; done
```