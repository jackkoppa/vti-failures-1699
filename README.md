# vti-failures-1699

Repro case for https://github.com/vuejs/vetur/issues/1699
Where a certain number of files causes `vti diagnostics` to fail

## To Reproduce

```bash
git clone https://github.com/jackkoppa/vti-failures-1699.git
cd vti-failures-1699
npm ci
npm run vti

# On local machine (system info below),
# fails ~80% of the time as described in vetur/issues/1699
# no JS exceptions, just exit code 1

# Now, change `ComplexComponent5.vue` ->  `ComplexComponent5.txt`
# thus removing it from vti observation, and run vti again
mv src/components/ComplexComponent5.vue src/components/ComplexComponent5.txt
npm run vti

# On local machine, succeeds 100% of the time
```

## Local system info

* MacBook Pro (15-inch, 2018)
* Processor: 2.6 GHz 6-Core Intel Core i7
* Memory: 16 GB 2400 MHz DDR4
* Graphics: Intel UHD Graphics 630 1536 MB

* `node -v`: v12.12.0
* `npm -v`: 6.13.7

## Notes

If reproduction does not end up being easy across machines, I may need some help getting whatever the most useful memory profile is
