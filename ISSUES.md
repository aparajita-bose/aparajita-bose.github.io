# Issues

## [✅ FIXED] `deploy` github workflow failed at `Setup Ruby` step

Error message in [logs](https://github.com/aparajita-bose/aparajita-bose.github.io/actions/runs/13843035642/job/38734916553#step:3:44):
```
Your bundle only supports platforms ["aarch64-linux-gnu"] but your local
platform is x86_64-linux. Add the current platform to the lockfile with
`bundle lock --add-platform x86_64-linux` and try again.
```

Found related github issue -
[Deployment failed with Gemfile.lock (created by local setup) · Issue #2544 · alshedivat/al-folio](https://github.com/alshedivat/al-folio/issues/2544)

Fix option #1: revert `Gemfile.lock`

Fix option #2: `bundle lock --add-platform x86_64-linux`

Went for option #2 but since `bundle` wasn't installed locally, I just made added `x86_64-linux` under `PLATFORMS` in [Gemfile.lock](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/Gemfile.lock#L187) (see: [commit](https://github.com/aparajita-bose/aparajita-bose.github.io/commit/893f60364032140d3986387186a0a32009e4f979))