# agent-setup

My personal agent setup, with skills I write and work I adopt from others.
Currently, it contains selected skills from Lauren Tan's [pstack](https://github.com/cursor/plugins/tree/main/pstack).

## Use the skills

If you do not already have a `~/.agents` directory, clone this repository there:

```bash
git clone https://github.com/eldiegoveliz/agent-setup.git ~/.agents
```

If you already have a setup, clone this repository elsewhere and copy the skill folders you want into your existing `~/.agents/skills/`.

The actual skill files are included in `skills/`. No submodules, symlinks, or additional downloads are needed to get these files.
Skill support depends on your agent. This selection includes `how`, `why`, and `arena`, their reference files, and the supporting principle skills. The upstream instructions include Cursor-specific model names, subagent settings, and tool assumptions that may need adaptation for your agent. This is not the complete pstack plugin. Optional workflows mentioned in the text, such as `show-me-your-work`, are not included.

## Maintain the setup

These skills may be outdated. Check the linked sources for updates before relying on them.

I keep upstream checkouts locally in `plugins/`, which Git ignores. To update a third-party skill, I pull its upstream checkout, copy the selected files into `skills/`, review the changes, and update the source revision in [CREDITS.md](CREDITS.md).

My own skills can go directly into `skills/` too.

## Credits and licenses

The current skills come from Lauren Tan's pstack. See [CREDITS.md](CREDITS.md) for the source revision and copied skill list.

My original contributions are available under the [MIT license](LICENSE). Third-party material retains its original copyright and license notices, including [pstack's MIT license](LICENSES/pstack.txt).
