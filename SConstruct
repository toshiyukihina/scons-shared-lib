env = Environment()

# Create a shared library
lib_target = "libhello"
lib_sources = ["libhello.c"]
libhello = env.SharedLibrary(target=lib_target, source=lib_sources)

# Create a exectable using libhello.so
bin_target = "hello"
bin_sources = ["hello.c"]
env.Program(target=bin_target, source=bin_sources, parse_flags="-I. -L. -lhello")

env.Install(dir="/usr/local/lib", source=libhello)
env.Alias("install", ["/usr/local/lib"])
