# lsp_hover

A packaged version of a fancy lsp hover window I found on [reddit](https://www.reddit.com/r/neovim/comments/1i84nmd/a_simple_slightly_fancy_lsp_hover_to_take/)

> [!NOTE]
> I take absolutely no credit in this, I simply packaged the code for easy installation and lazy loading.
>
> Original gist can be found [here](https://gist.github.com/OXY2DEV/645c90df32095a8a397735d0be646452)

# Installation

```lua
-- lazy
{ "paradoxical-dev/lsp_hover", lazy = true }
```

If using [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) or [mason-lspconfig](https://github.com/williamboman/mason-lspconfig.nvim) you can add the setup into the on_attach function of your configuration like this

```lua
{
  "williamboman/mason-lspconfig.nvim",
  -- ...
  opts = {
    -- ...
    handlers = {
      function(server_name)
        lsp_config[server_name].setup({
          on_attach = function(client, bufnr),
            require("lsp_hover").setup({
              -- configuration options
            })
          end
        })
      end,
    }
  }
}
```
