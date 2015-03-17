## Local [Haxe](http://haxe.org/) builds

### Why?

Haxe and the haxelibs are bound to a specific project folder. There is no haxe/haxelib binary installed on the host machine, and the haxelib directory ('haxe_modules') is local to the current working directory. This means different projects can use different versions of haxe.

### Prerequisites

	Linux: [docker](https://www.docker.com/)
	Mac: [boot2docker](http://boot2docker.io/), [docker](https://www.docker.com/)
	Testing: [Vagrant](https://www.vagrantup.com/)

Windows: in theory this can be made to work in Windows, but I don't have a machine and this is a low priority. Glad to take pull requests here.

### Running

In the terminal:

	./haxe

Or

	./haxelib install <library>

The haxe and haxelib scripts can be copied and moved anywhere as long as the path to dockerhaxe is modified. The haxelib script will create a 'haxe_modules' folder in the current working directory. Both the haxe and haxelib.

### Testing

	npm run test