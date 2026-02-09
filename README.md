<p align="center">
  <img src="https://avatars.githubusercontent.com/u/259794077?v=4" width="200" alt="yagi logo" />
</p>

<h1 align="center">yagi-agent</h1>

<p align="center">
  An AI agent ecosystem built around <a href="https://github.com/yagi-agent/yagi">yagi</a>
</p>

---

## [yagi](https://github.com/yagi-agent/yagi)

A CLI chat client for multiple LLM providers with a plugin system powered by [Yaegi](https://github.com/traefik/yaegi). Tools are written as plain Go source files and loaded at runtime — no recompilation needed.

- **Multi-provider support** — OpenAI, Gemini, Anthropic, Groq, DeepSeek, and 16+ providers
- **Dynamic plugin system** — Drop Go files into `~/.config/yagi/tools/` to add tools
- **Memory system** — Learn and recall information across conversations
- **Skills system** — Load specialized prompts for different tasks
- **Session resumption** — Save conversation history per directory and resume with `-resume`
- **Interactive & one-shot modes** — Use interactively or pipe commands

```bash
go install github.com/yagi-agent/yagi@latest

# Interactive mode
yagi

# One-shot
git diff | yagi "Summarize this diff"
```

## [actions-yagi](https://github.com/yagi-agent/actions-yagi)

A GitHub Action for **AI-powered pull request reviews** using yagi. Automatically posts code review comments when a PR is created or updated.

- Supports multiple LLM providers (OpenAI, Anthropic, Gemini, etc.)
- Customizable review prompts
- Optional custom avatar (yagi-chan) via GitHub App setup
- Integrates with [yagi-profiles](https://github.com/yagi-agent/yagi-profiles) for identity and tool configuration

```yaml
- uses: yagi-agent/actions-yagi@v1
  env:
    OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
```

## [vim-yagi](https://github.com/yagi-agent/vim-yagi)

A Vim / Neovim plugin for AI assistance using yagi.

- Multiple commands: `:YagiExplain`, `:YagiRefactor`, `:YagiFix`, `:YagiComment`, and more
- Send visual selections as context
- Default key mappings under `<Leader>y`

```vim
Plug 'yagi-agent/vim-yagi'
```

## [yagi-profiles](https://github.com/yagi-agent/yagi-profiles)

A shared repository of identities (personas), skills, and tools for yagi. Also referenced by actions-yagi.

| Directory | Contents |
|---|---|
| `IDENTITY.md` / `IDENTITY_EN.md` | Yagi-chan persona definitions (Japanese / English) |
| `skills/` | Skill prompts: code-review, debug, explain, refactor, test |
| `tools/` | Shared tools: fetch_url, list_files, read_file, write_file |

---

## License

MIT

## Author

Yasuhiro Matsumoto (a.k.a. [mattn](https://github.com/mattn))
