# vti-failures-1699

**Update**: See [Use of `sudo`](#Use-of-sudo) for current workaround

Repro case for https://github.com/vuejs/vetur/issues/1699

Where a certain number of files causes `vti diagnostics` to fail

## To Reproduce

```bash
git clone https://github.com/jackkoppa/vti-failures-1699.git
cd vti-failures-1699
npm ci
npm run vti

# On local machine (system info below),
# fails ~5/6 times as described in vetur/issues/1699
# no JS exceptions, just exit code 1

# Now, change one of the ComplexComponent files from .vue -> .txt
# thus removing it from vti observation, and run vti again
mv src/components/ComplexComponent4.vue src/components/ComplexComponent4.txt
npm run vti

# On local machine, succeeds 100% of the time

# Finally, if you *still* see a failure message, we can try one more thing:
git checkout -- .
git clean -df
# This branch has even fewer vti-checked files,
# and it would be very surprising if the vti command still fails
git checkout minimal-file-count-for-additional-testing
npm run vti
```

Can see [logs/detailed_repro_logs(2.17.20).md](./logs/detailed_repro_logs(2.17.20).md) for local reproduction results

## Local system info

* MacBook Pro (15-inch, 2018)
* Processor: 2.6 GHz 6-Core Intel Core i7
* Memory: 16 GB 2400 MHz DDR4
* Graphics: Intel UHD Graphics 630 1536 MB

* `node -v`: v12.12.0
* `npm -v`: 6.13.7

## Notes

* If reproduction does not end up being easy across machines, I may need some help getting whatever the most useful memory profile is

* Initial repo files created with:

```bash
npx -p @vue/cli@latest vue create vti-failures-1699 --inlinePreset '{"useConfigFiles": true,"plugins": {"@vue/cli-plugin-typescript": {"classComponent": false}}}'
```

## Use of `sudo`

* Per [this comment](https://github.com/vuejs/vetur/issues/1699#issuecomment-587334315) from [@dkonchekov](https://github.com/dkonchekov), it appears that running with `sudo` - i.e. `sudo npm run vti` - removes whatever process-specific upper bound is causing the failure. In all cases tested thus far, `sudo` solves all problems demo-ed by this repo, regardless of component count.
* Next steps, then, are to diagnose the upper bound that `sudo` removes, so that the command can adjust memory/file/thread/etc. usage to not require sudo; will continue to be discussed in [1699](https://github.com/vuejs/vetur/issues/1699)
