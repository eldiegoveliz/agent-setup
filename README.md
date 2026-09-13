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
Skill support depends on your agent. This is a selection from pstack, not its complete plugin. Some skills refer to helpers that are not included, such as `how`, `why`, and `arena`.

## Maintain the setup

I keep upstream checkouts locally in `plugins/`, which Git ignores. To update a third-party skill, I pull its upstream checkout, copy the selected files into `skills/`, review the changes, and update the source revision in [CREDITS.md](CREDITS.md).

My own skills can go directly into `skills/` too.

## Credits and licenses

The current skills come from Lauren Tan's pstack. See [CREDITS.md](CREDITS.md) for the source revision and copied skill list.

My original contributions are available under the [MIT license](LICENSE). Third-party material retains its original copyright and license notices, including [pstack's MIT license](LICENSES/pstack.txt).
