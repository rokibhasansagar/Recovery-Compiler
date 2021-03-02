# Recovery-Compiler 🤖

This GitHub Action Let's You Compile Recovery For Android Devices.

## Features 📜

 - Let's you Compile Without Any Hassle Of Setting Up Environment.
 - Just Setup Env Variables & Everything Is Automated.


## Notes ✋

Build either on `ubuntu-18.04` or `ubuntu-20.04` also Known As `ubuntu-latest`

You MUST use `rokibhasansagar/slimhub_actions@main` Action befor running this Compiler Action to Cleanup Spaces

PATH for Compiled Recovery is `/home/runner/work/out/target/product/*/*.img , *.zip`

For Orangefox android V10 Use `orangefox` in `MANIFEST` `/home/runner/work/out/target/product/*/*.img , *.zip`
            
Caution :- `orangefox` term is Only For Android10 based devices aka dynamic devices

For Android 9 devices you can use Manifest

## Usage 👨‍💻

```yaml
# ...
jobs:
  recovery_builder:
    runs-on: ubuntu-latest
    # You can use either of the ubuntu-18.04 or ubuntu-20.04 runner
    steps:
      # You might want to Checkout your repo first, but not mandatory
      - uses: actions/checkout@v2
      # Cleanup The Actions Workspace Using Custom Composite Run Actions
      - uses: rokibhasansagar/slimhub_actions@main
      # That's it! Now use this action
      - name: Recovery Compilation
        uses: CarbonatedBlack/Recovery-Compiler@production
        env:
          MANIFEST: "Recovery Manifest URL with -b branch" or "orangefox" for orangefox android v10
          DT_LINK: "Your Device Tree Link"
          VENDOR: "Your Device's Vendor name as in used inside DT. Example: xiaomi, samsung, asus, etc."
          CODENAME: "Your Device's Codename as in used inside DT. Example: nikel, phoenix, ginkgo, etc."
          KERNEL_LINK: "Kernel repo link with optional -b branch. If not filled it would be detected as prebuilt"
          TARGET: "Set as recoveryimage or bootimage if no recovery partition avaiable"
          FLAVOR: "eng or userdebug"
          EXTRA_CMD: "if you want to Execute any external Command Before Compilation Starts"
          TZ: "Asia/Kolkata" # Set Time-Zone According To Your Region
```

## Credits 🥰

[rokibhasansagar](https://github.com/rokibhasansagar) For His Cleanup Scripts And Great Help

## License 🔖

Licensed Under [GPLV3](https://github.com/Carbonatedblack/Recovery-Compiler/blob/production/LICENSE)
