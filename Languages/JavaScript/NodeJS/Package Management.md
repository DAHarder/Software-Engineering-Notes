# NPM
## Summary
NPM, or Node Package Manager, is a package manager for JavaScript used primarily for managing dependencies in Node.js projects. It allows developers to install, manage, and update third-party packages and libraries, which are stored in a registry containing over 1 million packages. 
NPM is bundled with Node.js and is widely used in the JavaScript and Node.js development communities. It is free and open-source software, and includes features for managing project configuration, running scripts, and collaborating with other developers.

## Common Commands
### npm -v`
List version

### npm init
Initializes a new Node.js project and creates a package.json file.
### `npm search <name>
Search for packages

### npm install
Installs project dependencies listed in the package.json file.

### npm install package-name
Installs the package
- Installs package in `node_modules -> <package name>` under your current directory.  The code is hosted in the `lib` folder
`-g`
This flag will install the package globally (so all projects can see/use it)

### node -e 'console.log(module.paths)'
Lists the paths that `npm install` will look for already-installed packages

### npm uninstall package-name
uninstalls the package and removes it from the package.json file

### npm publish \<package>
Used to to upload a package from the current directory to the npm registry, making it available for other developers to use and install. Before running the command, ensure you have a unique package name and a valid npm account. Once published, others can depend on the package using `npm install package-name`.
## package.json
Typically located in the project root directory, it contains metadata for packages include name, version, author, repository, etc, and Dependencies.
