# Issues

## [✅ FIXED] bundler: failed to load command: jekyll

Around Mar 2025, after few months since the last commit, `docker compose up` started failing with the above error.

However, when editing files directly on github, the workflows ran successfully to update the website.

So I investigated the difference between github workflows and local Docker setup and found the `ruby` version is fixed to `3.2.2` in the [`.github/workflows/deploy.yml`](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/5636270b2b57b7c180f20868c1c6103208be20ce/.github/workflows/deploy.yml#L73) and `latest` in [`Dockerfile`](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/5636270b2b57b7c180f20868c1c6103208be20ce/Dockerfile#L1).

**Fix:**
- Updated `ruby` to `3.2.2` in [Dockerfile](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/Dockerfile#L1) (see: [commit](https://github.com/aparajita-bose/aparajita-bose.github.io/commit/0f3a6644998e0fef14493d05284d97c0b4a78cc4#diff-dd2c0eb6ea5cfc6c4bd4eac30934e2d5746747af48fef6da689e85b752f39557))
- Ran `docker compose up --build` to re-build and reflect changes made in `Dockerfile` and website server started successfully!

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