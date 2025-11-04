<div align=center>

# Goto-Remote

</div>

#### What is Goto-Remote?
Goto-Remote is a simple bash script that can open the remote repo of your CWD's git repo from your browser.

#### How to install (Manual)
1. Place the script in one of your `PATH`s.
2. That's it! (Try typing `gtr` inside a git directory)

> !NOTE
> This script is made for linux. Just change the last line's `xdg-Open` to `open`.

#### For maximum productivity
1. Map a keybind in your shell configuration file:

Example for zsh:
```bash
# Run gtr with ctrl + g
bindkey -s '^g' 'gtr\n'
```

2. Add custom command to neovim: 

Example for neovim:
```lua
-- Create a func for gtr
vim.api.nvim_create_user_command("Gtr", function()
	vim.fn.jobstart({ "bash", "-c", "gtr" }, { detach = true })
	vim.api.nvim_echo({ { "remote opened in the default browser!", "Normal" } }, false, {})
end, {})

-- Create a custom keymap
vim.keymap.set("n", "<C-g>", ":Gtr<CR>", { noremap = true, silent = true })
```

#### TODO
 - [ ] Add support for multiple remotes.
 - [ ] Add an install script.
 - [ ] Switch to bubble tea for better UX.
