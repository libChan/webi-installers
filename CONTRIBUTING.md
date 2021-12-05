# Guidelines for Contributing to Webi

Not strictly mandatory, but we appreciate:

- [x] Signed Commits
- [x] Semantic Commit Messages
- [x] Update `test` psuedo-package

## Signed Commits

Please **enable gpg-signing**.

You can do this **in about 30 seconds**:

1. Run [`git-config-gpg`](https://webinstall.dev/git-config-gpg) from Webi:
   ```bash
   # On Mac & Linux
   curl https://webinstall.dev/git-config-gpg | bash
   ```
2. Copy the GPG public key (it will be printed to your screen)
3. Add it to your GitHub profile: <https://github.com/settings/gpg/new>

## Semantic Commit Messages

We try to follow "semantic commits" to some degree. Especially since this is a
project with many sub-projects.

The general format is `<type>(<package>): <description>`, using these _types_:

| _type_   | _usage_                                                            |
| :------- | :----------------------------------------------------------------- |
| feat     | new feature for the user, not a new feature for build script       |
| fix      | bug fix for the user, not a fix to a build script                  |
| docs     | changes to the documentation                                       |
| style    | formatting, missing semi colons, etc; no production code change    |
| refactor | refactoring production code, eg. renaming a variable               |
| test     | adding missing tests, refactoring tests; no production code change |
| chore    | updating grunt tasks etc; no production code change                |

Try to write your commit messages (in the present tense) like this:

```txt
fix(node): update install.sh (fix #200)
```

```txt
feat(delta): add cheat sheet and install.sh
```

```txt
docs(ssh-adduser): document that foo does bar
```

See <https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716> for
some more examples.

## Also update the `test` installer (a 3-line change)

Whenever adding a new installer, please also update `test/install.sh`

- `rm -rf ~/.local/opt/YOUR_PACKAGE`
- `rm -f ~/.local/bin/YOUR_PACKAGE`
- `webi YOUR_PACKAGE`
- (and please keep it in alphabetical order)

See
<https://github.com/webinstall/webi-installers/pull/346/files#diff-db3af85ef45ed7ac0d1d9c473cf4d858657c127dc24d931fe18a9961f17e05b1>
for an example.
