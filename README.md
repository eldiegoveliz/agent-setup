# agent-setup

My personal agent setup, with skills I write and work I adopt from others.
Currently, it contains selected skills from Lauren Tan's [pstack](https://github.com/cursor/plugins/tree/main/pstack), including adaptations for my personal workflow.

## Use the skills

If you do not already have a `~/.agents` directory, clone this repository there:

```bash
git clone https://github.com/eldiegoveliz/agent-setup.git ~/.agents
```

If you already have a setup, clone this repository elsewhere and copy the skill folders you want into your existing `~/.agents/skills/`.

The actual skill files are included in `skills/`. No submodules, symlinks, or additional downloads are needed to get these files.
Skill support depends on your agent. This selection includes `how` and `arena`, their reference files, and the supporting principle skills. The adapted workflows prefer Terra and Sol at medium reasoning with fast mode disabled. Model access, delegation, and other tools depend on your environment. Settings that cannot be applied or verified should be reported. This is not the complete pstack plugin. Optional workflows mentioned in the text, such as `show-me-your-work`, are not included.

## Maintain the setup

These skills may be outdated. Check the linked sources for updates before relying on them.

I keep upstream checkouts locally in `plugins/`, which Git ignores. To update a third-party skill, I pull its upstream checkout and compare the selected files with my copies before applying changes. I preserve the adaptations noted in [CREDITS.md](CREDITS.md), review the result, and record which source revision each updated skill uses. Copying upstream files over adapted skills would overwrite my changes.

My own skills can go directly into `skills/` too.

## Credits and licenses

The current skills come from Lauren Tan's pstack. See [CREDITS.md](CREDITS.md) for the source revision and copied skill list.

My original contributions are available under the [MIT license](LICENSE). Third-party material retains its original copyright and license notices, including [pstack's MIT license](LICENSES/pstack.txt).
