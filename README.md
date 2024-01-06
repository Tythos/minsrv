# minsrv

Basic C server for testing system-level C development techniques on Windows.

Largely based on Licthman's excellent whirlwind:

  https://www.youtube.com/watch?v=2HrYIl6GpYg

## Building

Enter WSL (if on Windows) and use the basic CMake one-two:

```sh
$ cmake -S . -B build
$ cmake --build build
```

You should now have a build you can run, preferably with strace for debugging:

```sh
$ strace build/minsrv
```

## Testing

You can test by fetching `index.html` from another WSL shell with `wget`:

```sh
$ wget localhost:8080/index.html
```

The sole function of this program is to parse the file path from the GET request, read the corresponding file, and write it back to the socket. So do not expect much.
