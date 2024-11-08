---
date: 2024-11-07 15:40
sources: 
tags:
  - zettel
  - linux
status: literature
publish: true
---
# sudo pacman

| Command                 | Description                                                                  |
| ----------------------- | ---------------------------------------------------------------------------- |
| `pacman -Syu`           | Update the package database and upgrade all installed packages.              |
| `pacman -S <package>`   | Install a specified package from the repositories.                           |
| `pacman -R <package>`   | Remove a specified package without removing dependencies.                    |
| `pacman -Rs <package>`  | Remove a specified package and its unneeded dependencies.                    |
| `pacman -Rns`           | Remove a specified package, its unneeded dependencies and orphaned packages. |
| `pacman -Ss <keywords>` | Search for packages in the repositories by keywords.                         |
| `pacman -Qs <query>`    | Search for installed packages matching the query.                            |
| `pacman -Qe`            | List explicitly installed packages.                                          |
| `pacman -Qdt`           | List orphaned packages (installed as dependencies but no longer required).   |

---
## Related Notes
[[add aliases to fish shell]]

## References(links)
[I have two electron in my arch linux distro, electron 30 and electron 32. I...](https://www.perplexity.ai/search/i-have-two-electron-in-my-arch-Ia1xfscVSwO2MMbN12Oqbg)