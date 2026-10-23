# no-claudish

A skill that rewrites Claudish into plain English. Claudish is the prose style Claude tends to write in: contrast framing, structural metaphors ("load-bearing", "gated", "surface"), staged emphasis, and one idea restated several times. The skill also tells Claude to check its own replies for the same habits.

Adapted from the `claudish-to-english` spec in [programasweights/claudish](https://github.com/programasweights/claudish) (MIT, see `LICENSE-upstream`).

## Install

### Claude Code (plugin)

From GitHub, once this repo is pushed (the repo below does not exist yet):

```
/plugin marketplace add partybustohell/no-claudish
/plugin install no-claudish@no-claudish
```

From a local clone:

```
/plugin marketplace add /path/to/no-claudish
/plugin install no-claudish@no-claudish
```

### Claude Code (plain skill folder)

Copy `skills/no-claudish` into `~/.claude/skills/` (all projects) or `.claude/skills/` (one project).

### claude.ai and Claude Desktop

Upload `dist/no-claudish.skill` under Settings, Capabilities, Skills. The file is a zip with `no-claudish/SKILL.md` inside.

## Use

Say "de-claudish this", "translate this to English", or "stop speaking claudish". In Claude Code you can also run `/no-claudish`.

## Rebuild the .skill file

```
python3 -c "import zipfile; z=zipfile.ZipFile('dist/no-claudish.skill','w',zipfile.ZIP_DEFLATED); z.write('skills/no-claudish/SKILL.md','no-claudish/SKILL.md'); z.close()"
```
