# Description
ze_peer is a performance benchmark suite for measuing peer-to-peer bandwidth
and latency.

# How to Build it

### Building Level Zero Performance Tests

```
mkdir build
cd build
cmake
  -D CMAKE_INSTALL_PREFIX=$PWD/out/perf_tests
  ..
cd perf_tests
make -j`nproc`
make install
```

ze_peer test executable is installed in your CMAKE build/out/perf_tests directory.

# How to Run it
To run, use the following command options.
```
 ./ze_peer -h

 ze_peer [OPTIONS]

 OPTIONS:
  -t, string                  selectively run a particular test
      transfer_bw             selectively run transfer bandwidth test
      latency                 selectively run latency test
  -a                          run all above tests [default]
  -b                          run bidirectional mode
  -o, string                  operation to perform
      read                    read from remote
      write                   write to remote
  -m                          run tests in multiprocess
  -d                          destination device
  -s                          source device
  -n                          max number of devices to use to run all to all. By default, only devices 0 and 1 are used
  -z                          size to run
  -v                          validate data (only 1 iteration is executed)
  -q                          query for number of engines available
  -g, number                  select engine group (default: 0)
  -i, number                  select engine index (default: 0)
  -e                          run concurrently using all compute engines (each size is evenly distributed among engines)
  -l                          run concurrently using all copy engines (each size is evenly distributed among engines)
  -h, --help                  display help message
```
