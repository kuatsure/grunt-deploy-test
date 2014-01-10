# grunt-deploy-test

> playground for version bumping / changelogging / committing / deploying

this uses a custom build of [`grunt-bump`](https://github.com/kuatsure/grunt-bump). hence the `prerelease` method instead of `build`.

### thoughts

Here's a [workflow that I'm figuring out](http://d.pr/i/Czor).

I have a `bump-only` task on `watch` that increaments `build` / `prerelease` number. However I'm not sure how I feel about it. Ideally I don't want the `package.json` to be updated like crazy in the `develop` branch ( because that's where the prerelease number would come into play ). So I'm thinking only major/minor/patch versions will be done, with no prerelease on the `watch` task, or `develop` branch.

Changelog: not exactly liking this either. You can get all you need from `git log`. And it forces commit messages to be a certain way. Meh.

New thing: `grunt-replace`. Loving this, this stops me from forcing files to the `concat` task just to process the version numbers ( or anything templatey for that matter ).

I thought about splitting up the gruntfile into one file per task. But that's just more stuff to worry about and doesn't give the developer a the full picture right then and there. But it does make for some nice `git diff`s.

Next up: bump -> deploy
