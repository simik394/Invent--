---
page-title: "GustavoKatel/tasks.nvim: Yet another task runner/manager for Neovim"
url: https://github.com/GustavoKatel/tasks.nvim
date: "2024-08-16 23:39:02"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf/automation]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 4907
dir: 
---

## tasks.nvim

[](https://github.com/GustavoKatel/tasks.nvim#tasksnvim)

## State

[](https://github.com/GustavoKatel/tasks.nvim#state)

Alpha

Dependencies:

-   [https://github.com/nvim-lua/plenary.nvim](https://github.com/nvim-lua/plenary.nvim)

Neovim versions:

-   `0.7.2`
-   `nightly`

## Installation

[](https://github.com/GustavoKatel/tasks.nvim#installation)

With Packer:

use({ "GustavoKatel/tasks.nvim", requires \= { "nvim-lua/plenary.nvim" } })

## Configuration

[](https://github.com/GustavoKatel/tasks.nvim#configuration)

Calling `setup` is not mandatory

Example:

local tasks \= require("tasks")

local source\_npm \= require("tasks.sources.npm")
local source\_tasksjson \= require("tasks.sources.tasksjson")

local builtin \= require("tasks.sources.builtin")

require("telescope").load\_extension("tasks")

tasks.setup({
	sources \= {
		npm \= source\_npm,
		vscode \= source\_tasksjson,
		utils \= builtin.new\_builtin\_source({
			sleep \= {
				fn \= function(ctx)
					local pasync \= require("plenary.async")

					pasync.util.sleep(10000)
				end,
			},

            vim\_cmd \= {
                vcmd \= "echo 'ok'"
            },

            shell\_cmd \= {
                cmd \= "make test"
            }
		}),
	},
})

## Sources

[](https://github.com/GustavoKatel/tasks.nvim#sources)

### builtin

[](https://github.com/GustavoKatel/tasks.nvim#builtin)

the builtin source is just a place holder to allow you to define custom task specs using lua functions, vim commands or shell commands.

### npm

[](https://github.com/GustavoKatel/tasks.nvim#npm)

It will load all `package.json` scripts from the project root to be used as task specs.

### tasksjson (vscode)

[](https://github.com/GustavoKatel/tasks.nvim#tasksjson-vscode)

It will load all tasks from `.vscode/tasks.json` to be used as task specs.

There are bunch of things missing from the schema, I believe it's enough to get started. Please open an issue if you think any of the missing features should be added.

## Runners

[](https://github.com/GustavoKatel/tasks.nvim#runners)

### builtin

[](https://github.com/GustavoKatel/tasks.nvim#builtin-1)

The builtin runner is a generic runner that allows you to run lua functions, vim commands or shell commands (using the terminal `:e term://...`)

It's always available, even if you don't specify in your config.

### Custom runners

[](https://github.com/GustavoKatel/tasks.nvim#custom-runners)

A very minimal custom runner that runs lua functions (async functions) can be created as such:

local Task \= require("tasks.lib.task")
local tasks \= require("tasks")

tasks.setup({
    ...
    runners \= {
        custom\_runner \= {
            create\_task \= function(self, spec, args)
                return Task:new(spec.fn, args)
            end
        }
    },

    sources \= {
        my\_tasks \= builtin.new\_builtin\_source({
			sleep \= {
				fn \= function(ctx)
					local pasync \= require("plenary.async")

					pasync.util.sleep(10000)
				end,
                \-- this prop will route this task to the custom runner
                runner\_name \= "custom\_runner"
			},
		}),
    }
})

### Custom router

[](https://github.com/GustavoKatel/tasks.nvim#custom-router)

You can specify a router function to better match specs with runners. This will override the `runner_name` in the specs.

tasks.setup({
    runners \= { ... },
    sources \= { ... },
    router \= function(spec\_name, spec, args, source\_name)
        \-- this will run all specs from the \`npm\` source in runner with name \`my\_custom\_runner\`
        if source\_name \== "npm" then
            return "my\_custom\_runner"
        end
        return nil \-- fallback to use the default router value
    end
})

## Integrations

[](https://github.com/GustavoKatel/tasks.nvim#integrations)

### Telescope

[](https://github.com/GustavoKatel/tasks.nvim#telescope)

Shows all the available specs from all sources.

The default action will create and run a new task.

[![telescope-demo](https://github.com/GustavoKatel/tasks.nvim/raw/main/demo/telescope_demo_specs.png)](https://github.com/GustavoKatel/tasks.nvim/blob/main/demo/telescope_demo_specs.png)

Shows all current running tasks.

The default action will request the task to stop (call `task:request_stop()`).

[![telescope-demo](https://github.com/GustavoKatel/tasks.nvim/raw/main/demo/telescope_demo_running.png)](https://github.com/GustavoKatel/tasks.nvim/blob/main/demo/telescope_demo_running.png)

### sidebar.nvim integration

[](https://github.com/GustavoKatel/tasks.nvim#sidebarnvim-integration)

local tasks\_section \= require("sidebar-nvim.sections.tasks")

local sidebar \= require("sidebar-nvim")

sidebar.setup({
    ...
    sections \= { tasks\_section }
    ...
})

[![sidebar-demo](https://github.com/GustavoKatel/tasks.nvim/raw/main/demo/sidebar_demo.png)](https://github.com/GustavoKatel/tasks.nvim/blob/main/demo/sidebar_demo.png)

### statusline/tabline/winbar

[](https://github.com/GustavoKatel/tasks.nvim#statuslinetablinewinbar)

Minimal integration for lualine

lualine.setup({
    ...
    sections \= {
        lualine\_c \= {
            require("tasks.statusline.running")("<custom\_icon or prefix>")
        }
    }
    ...
})

## API

[](https://github.com/GustavoKatel/tasks.nvim#api)

### tasks.run(spec\_name, args, source\_name)

[](https://github.com/GustavoKatel/tasks.nvim#tasksrunspec_name-args-source_name)

Run the first spec with name `spec_name` additionally passing extra args in `args`

You can also pass `source_name` to refine the search and only run specs from that source.

Returns `task_id` and a task table ([Task](https://github.com/GustavoKatel/tasks.nvim#task-api))

### tasks.run\_last()

[](https://github.com/GustavoKatel/tasks.nvim#tasksrun_last)

Re-run the last spec with the same args passed in the last call to `tasks.run`

Returns `task_id` and task table

### tasks.get\_specs({ source\_name = nil, runner\_name = nil })

[](https://github.com/GustavoKatel/tasks.nvim#tasksget_specs-source_name--nil-runner_name--nil-)

Get all the available specs. Optionally filter by spec name `spec_name` and runner name `runner_name`.

Returns dictionary

Example of return value:

{
    \["my\_source"\] \= {
        \["spec\_1"\] \= {
            ...
        },
        \["spec\_2"\] \= {
            ...
        }
    },
    \[<source\_name>\] \= {
        \[<spec\_name>\] \= <spec>
    }
}

### tasks.get\_running\_tasks({ source\_name = nil, runner\_name = nil })

[](https://github.com/GustavoKatel/tasks.nvim#tasksget_running_tasks-source_name--nil-runner_name--nil-)

Get all the tasks currently running. Optionally filter by spec name `spec_name` and runner name `runner_name`.

Returns dictionary

Example of return value:

{
    \[1\] \= <task>,
    \[2\] \= <task>,
    ...
    \[<task\_id>\] \= <task>
}

### task api

[](https://github.com/GustavoKatel/tasks.nvim#task-api)

A task object has a few helper methods.

### task:get\_spec\_name()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_spec_name)

### task:get\_source\_name()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_source_name)

### task:get\_runner\_name()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_runner_name)

### task:get\_state()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_state)

Returns the current task state, which can evolve from `ready` -> `running` -> `done`.

### task:request\_stop()

[](https://github.com/GustavoKatel/tasks.nvim#taskrequest_stop)

Signal the underlying job that this task should be cancelled.

### task:get\_started\_time()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_started_time)

### task:get\_finished\_time()

[](https://github.com/GustavoKatel/tasks.nvim#taskget_finished_time)