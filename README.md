# NPM Deep Pack

📦 Resolve and download a package and its dependencies 🗃️

## Installation

`npm i @tar-erpedia/deep-pack -g`

## CLI

---

By default direct dependencies and peer dependencies are resolved and downloaded.

### Usage

`npx npm-deep-pack <spec> [options]`
<br>

#### \<spec\>

1. ##### Single package with dependencies

    **Package name**: `[@<pkg_org>/]<package_name>`
    Package name with version range `[@<pkg_org>/]<package_name>[@<pkg_version>]`

    Valid examples: `next`, `@vue/cli`, `react@19.0.1`, `vite@latest`

2. ##### All dependencies in a package.json file

    **Path**: `path/to/package.json`

    Valid examples: `/absolute/path/to/package.json`, `relative/path/to/package.json`

#### Options

`-V, --version                   output the version number`
`-d, --max-depth <depth>         max depth. | integer bigger than 1 (default: null)`
`--dev, --dev-deps               Resolve devDependencies`
`--no-peer, --no-peer-deps       Don't resolve peerDependencies`
`--optional, --optional-deps     Resolve optionalDependencies`
`--out-deps <out>                Export dependencies list? (default: false)`
`--out-resolved-deps <out>       Export resolved dependencies list? (default: true)`
`-r, --resume-last-run <resume>  Resume last run?`
`--tgz, --output-tgz             Bundle output to tgz (default: false)`
`-h, --help`

#### Full examples

###### Basic

`npx npm-deep-pack vite`

###### With optional dependencies and output dependencies in tgz bundle

`npx npm-deep-pack --optional --tgz next`


###### Unrecommended: No peer, only direct

`npx npm-deep-pack --no-peer react-router`