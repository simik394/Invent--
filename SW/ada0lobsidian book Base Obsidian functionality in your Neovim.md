---
page-title: "ada0l/obsidian: :book: Base Obsidian functionality in your Neovim"
url: https://github.com/ada0l/obsidian
date: "2024-06-21 02:51:27"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 3771
dir: auto
---

I often use Obsidian to take daily notes and maintain my knowledge base. This plugin allows you to use the basic functionality to work with Obsidian vaults.

You do not need to decorate functions in keys if you have only one vault in opts.vaults.

{
  'ada0l/obsidian',
  keys \= {
    {
      '<leader>ov',
      function()
        Obsidian.select\_vault()
      end,
      desc \= "Select Obsidian vault",
    },
    {
      '<leader>oo',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.cd\_vault()
        end)
      end,
      desc \= 'Open Obsidian directory',
    },
    {
      '<leader>ot',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.open\_today()
        end)
      end,
      desc \= 'Open today',
    },
    {
      '<leader>od',
      function()
        Obsidian.get\_current\_vault(function()
          vim.ui.input({ prompt \= 'Write shift in days: ' }, function(input\_shift)
            local shift \= tonumber(input\_shift) \* 60 \* 60 \* 24
            Obsidian.open\_today(shift)
          end)
        end)
      end,
      desc \= 'Open daily node with shift',
    },
    {
      '<leader>on',
      function()
        Obsidian.get\_current\_vault(function()
          vim.ui.input({ prompt \= 'Write name of new note: ' }, function(name)
            Obsidian.new\_note(name)
          end)
        end)
      end,
      desc \= 'New note',
    },
    {
      '<leader>oi',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.select\_template('telescope')
        end)
      end,
      desc \= 'Insert template',
    },
    {
      '<leader>os',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.search\_note('telescope')
        end)
      end,
      desc \= 'Search note',
    },
    {
      '<leader>ob',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.select\_backlinks('telescope')
        end)
      end,
      desc \= 'Select backlink',
    },
    {
      '<leader>og',
      function()
        Obsidian.get\_current\_vault(function()
          Obsidian.go\_to()
        end)
      end,
      desc \= 'Go to file under cursor',
    },
    {
      '<leader>or',
      function()
        Obsidian.get\_current\_vault(function()
          vim.ui.input({ prompt \= 'Rename file to' }, function(name)
            Obsidian.rename(name)
          end)
        end)
      end,
      desc \= 'Rename file with updating links',
    },
    {
      "gf",
      function()
        if Obsidian.found\_wikilink\_under\_cursor() ~= nil then
          return "<cmd>lua Obsidian.get\_current\_vault(function() Obsidian.go\_to() end)<CR>"
        else
          return "gf"
        end
      end,
      noremap \= false,
      expr \= true
    }
  },
  opts \= function()
    \---@param filename string
    \---@return string
    local transformator \= function(filename)
      if filename ~= nil and filename ~= '' then
        return filename
      end
      return string.format('%d', os.time())
    end
    return {
      vaults \= {
        {
          dir \= '~/Documents/Knowledge/',
          templates \= {
            dir \= 'templates/',
            date \= '%Y-%d-%m',
            time \= '%Y-%d-%m',
          },
          note \= {
            dir \= '',
            transformator \= transformator,
          },
        },
        {
          dir \= '~/Documents/SyncObsidian/',
          daily \= {
            dir \= '01.daily/',
            format \= '%Y-%m-%d',
          },
          templates \= {
            dir \= 'templates/',
            date \= '%Y-%d-%m',
            time \= '%Y-%d-%m',
          },
          note \= {
            dir \= 'notes/',
            transformator \= transformator,
          },
        }
      }
    }
  end
},