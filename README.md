# bundler-checksum-dependabot

Showing dependabot issue in that it removes the bundler checksum (see https://github.com/ruby/rubygems/blob/master/bundler/CHANGELOG.md#4011--2026-04-30 ) from Bundler 4.0.11 when creating a dependabot PR

Dependabot ticket:
* https://github.com/dependabot/dependabot-core/issues/14913
Example PR/change where bundler checksum is removed:
* https://github.com/broksonic21/bundler-checksum-dependabot/pull/1/changes#diff-89cade48462044ee1b672dc5f4c3ec250fbd29effcd8932096a23c1283c6731fL14

Specific setup was:

* create the Gemfile
* run these commands: 

```
bundle update --bundler
bundle lock --normalize-platforms
bundle lock --add-checksums
```

* let Dependabot create a PR. 

We see this behavior on every PR of ours.

For Bundler:

Specific Changelog entry:
* Ensure the release CI doesn't break due to the Bundler checksum feature. Pull request [#9436](https://github.com/ruby/rubygems/pull/9436) by Edouard-chin

