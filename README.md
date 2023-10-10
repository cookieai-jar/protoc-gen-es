# protoc-gen-es binaries
protoc-gen-es packaged as a binaries for darwin amd64, arm64 and linux amd64

## How to generate binaries
Install the desired version of protoc-gen-es
```
npm install -g @bufbuild/protoc-gen-es
```
Find the source of protoc-gen-es using `which` and `cd` into that directory.
```
which protoc-gen-es
```
Bundle source and dependencies into a single file using esbuild 
```
npx esbuild protoc-gen-es  --bundle --outfile=build.cjs --format=cjs --platform=node
```
Package the source with node platform for darwing and linux targets 
```
npx pkg --targets node16-macos-x64,node16-macos-arm64,node16-linux-x64 build.cjs
```
Rename each binary to protoc-gen-es and create an archive
```
tar -czvf linux-amd64.tar.gz protoc-gen-es
```
Uninstall protoc-gen-es package
```
npm uninstall -g @bufbuild/protoc-gen-es
```
