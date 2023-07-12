---
title: "Test page"
description: "This page test various markdown formats."
weight: 80
chapter: false
---

## Intro

This [Peertube](https://joinpeertube.org/) plugin is meant to provide chat system for Peertube videos.

| | |
|---|---|
| ![Chat screenshot](/peertube-plugin-livechat/images/chat.png?classes=shadow,border&height=200px) | ![Fullscreen chat screenshot](/peertube-plugin-livechat/images/fullscreen.png?classes=shadow,border&height=200px) |

{{% notice tip %}}
See a [demo](https://www.yiny.org/w/399a8d13-d4cf-4ef2-b843-98530a8ccbae).
{{% /notice %}}

{{% notice warning %}}
This is a warning notice.
{{% /notice %}}

## Various

If you have any question, or if you want to talk about this plugin, you can join this XMPP room with any Jabber client: [plugin-livechat-support@room.im.yiny.org](xmpp:plugin-livechat-support@room.im.yiny.org?join).

If you want to support the project financially, you can contact me by mail at git.[at].john-livingston.fr, or check my [Liberapay profile](https://liberapay.com/JohnLivingston/).

To clone the repository:

```bash
# Clone the repository
git clone https://github.com/JohnXLivingston/peertube-plugin-livechat.git
# Be sure to checkout the main branch
git checkout main
# Initialize the submodules. This command must be run again if any submodules' version changes.
git submodule update --init --recursive

# Install NPM dependencies and build the module for the first time:
npm install

# Build the plugin after a modification:
npm run build

# If you have a fork from the repository, add it as remote (example):
git remote add me git@github.com:MY_GITHUB_ACCOUNT/peertube-plugin-livechat.git

# Create a local branch for you developments, and checkout it (example):
git checkout my_development # Note: if an issue is associated, use fix_1234 as your branch name (where 1234 is the issue's number)
# To propose your modifications, push your branch to your repository (example):
git push --set-upstream me my_development
# Then go to your github repository with your web browser to propose the Pull Request (see additional instructions below)
```

```bash
NODE_ENV=dev npm run build
```

## ESBuild vs Typescript

This plugin uses ESBuild for frontend code generation, as the official `peertube-plugin-quickstart` plugin.
ESBuild can handle Typescript, but does not check types (see [ESBuild documentation](https://esbuild.github.io/content-types/#typescript)).
That's why we first compile Typescript with the `-noEmit` option, just to check types (`check:client:ts` in package.json file).
Then, if everything is okay, we run ESBuild to generate the compiled javascript.

## Translations

The principal language is english (`en` code).

The different translations of the same file are side by side in the tree, and are identified by a language code in the file name extension.
Example: `_index.fr.md` is the French translation of `_index.en.md`.

Please note that a missing translation file will not appear in the menus of the generated site.

**Always make sure to create files for all languages**, even if the translation is not yet available.

For this, there is a script `doc-generate-missing-translations.sh` in the root of the repository. When you add a new file, you just have to create the english version, then run this script.
It will create all  missing translations, putting a sample message inviting the user to read the english version.

## Credits

[package.json](https://github.com/JohnXLivingston/peertube-plugin-livechat/blob/main/package.json),
[COPYRIGHT](https://github.com/JohnXLivingston/peertube-plugin-livechat/blob/main/COPYRIGHT.md)
and [LICENSE](https://github.com/JohnXLivingston/peertube-plugin-livechat/blob/main/LICENSE)
files contain the license information for this software and its dependencies.

The plugin is maintained by [John Livingston](https://www.john-livingston.fr/).

Thanks to David Revoy for his work on Peertube's mascot, [Sepia](https://www.davidrevoy.com/index.php?tag/peertube).
The character design is under CC-By licence, and the SVG files used to create some logo and avatars in this plugin are GPLv3.0.

Thanks to [Framasoft](https://framasoft.org) for making [Peertube](https://joinpeertube.org/) possible, for the financial support, and for hosting the project translations on their [Weblate instance](https://weblate.framasoft.org).

Thanks to [ritimo](https://www.ritimo.org/) for the financial support.

Thanks to [Code Lutin](https://www.codelutin.com/) and [Rétribution Copie Publique](https://copiepublique.fr/) for the financial support.

Thanks to [NlNet](https://nlnet.nl/) and the [NGI0 Entrust fund](https://nlnet.nl/entrust/) for the financial support.
