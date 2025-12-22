Sync dotfiles and Claude Code configuration changes back to the dotfiles repository.

Steps:
1. Sync changes to chezmoi source:

   **Important**: Use `--autotemplate` ONLY for files that are already templates (`.tmpl`) in chezmoi source. Otherwise chezmoi will prompt interactively and fail.

   **Claude files** (NOT templates):
   ```bash
   chezmoi add ~/.claude/CLAUDE.md
   ```

   **System config files** (ARE templates - use --autotemplate):
   ```bash
   chezmoi add --autotemplate ~/.zsh/.zshrc ~/.zsh/.zprofile ~/.zsh/.zshenv ~/.zsh/aliases.zsh
   ```

   **Other files** (check if templated first):
   - If `.tmpl` exists in `~/.local/share/chezmoi/`: use `--autotemplate`
   - If NO `.tmpl`: use plain `chezmoi add`

2. Navigate to the chezmoi source directory (~/.local/share/chezmoi)
3. Use the /pm:git-push skill to commit and push any changes
