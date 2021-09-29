# Interesting Package Collections

Swift package collections that are interesting to me.

The Swift package collection JSON files can be added to Xcode from this repository.

### Adding the Collections to Xcode

Each JSON file in the root of the repository is a package collection specification. You can add them to Xcode using raw file github URLs, e.g. for the 3rd party favorites collection:

```
https://raw.githubusercontent.com/memfrag/interesting-package-collections/main/3rd-party-favorites.json
```

### Generating the Collections

### Install the Generator

Use `mint` to install the generator CLI utility:

```bash
$ mint install apple/swift-package-collection-generator@main
```

### Run the Generator

Run the generator like so in the root of the repository:

```bash
$ package-collection-generate Input/<collection>.json ./<collection>.json --auth-token <github personal auth token>
```

### Sign

Temporarily copy `key.pem` and `swift_package.cer` from safe-keeping to this directory and run:

```bash
$ package-collection-sign Unsigned/<collection>.json ./<collection>.json key.pem swift_package.cer
```
