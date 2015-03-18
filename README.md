## Local [Haxe](http://haxe.org/) builds

### Why?

If you have different projects that require different versions of haxe, it is difficult to manage. Also haxelibs are installed globally.

These scripts are replacements for the haxe and haxelib binaries. They create a docker contained version of haxe and map the haxelibs to a local folder. This means you can have a project specific version of haxe and haxelibs.

It is also convenient for automated build systems.

### Prerequisites

Linux:

- [docker](www.docker.com/)

Mac:

- [boot2docker](boot2docker.io/)
- [docker](www.docker.com/)

Testing:

- [Vagrant](www.vagrantup.com/)

Windows: in theory this can be made to work in Windows, but I don't have a machine and this is a low priority. Glad to take pull requests here.

### Running

In the terminal (assumes your build.hxml file is in the same):

	<path to>/haxe build.hxml

Or

	<path to>/haxelib install <library>

The haxe and haxelib scripts can be copied and moved anywhere as long as the path to dockerhaxe is modified. The haxelib script will create a 'haxe_modules' folder in the current working directory. Both the haxe and haxelib.

### Testing

	npm run test