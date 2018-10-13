Scanned over this just now. A few quick comments. Might look more in depth tomorrow

- [x] Use command -v in place of which
- [x] Rather than `foo; if- [[ 0 = $? ]]` just do `if foo`
- [ ] put config files in e.g. `~/.config/tokens/config`
- [x] put state files in `~/.local/share/tokens`
- [x] on files you are about to execute, use `-x` not `-r`
- [x] you depend on `oauthtool` but I don't see where you check that it exists
- [ ] more error handling is necessary in many places to make this reliably secure
- [x] `bc` would simplify the math a lot but it's another dependency

Bedtime