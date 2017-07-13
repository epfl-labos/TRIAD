
## TRIAD

#### TRIAD: Creating Synergies Between Memory, Disk and Log in Log Structured Key-Value Stores
https://infoscience.epfl.ch/record/228863?ln=en

We added our experiments in db_bench_tool, the test suite used by rocksDB; the main file is in tools/db_bench_tool.cc
	
To run
	- Details about how to run db_bench, along with performance benchmarks can be found here: https://github.com/facebook/rocksdb/wiki/performance-benchmarks 
	- parameters that are of interest for TRIAD:
		--benchmarks
		--threads
		--key_size 
		--value_size
		--disable_wal=false
        --write_buffer_size
        --target_file_size_base
        --max_write_buffer_number=2
        --level0_file_num_compaction_trigger (how many files do we allow on L0 before triggering L0 compaction)
        --num_levels
        --use_existing_db=1
        --db=test

## RocksDB Original Readme

#### RocksDB: A Persistent Key-Value Store for Flash and RAM Storage


RocksDB is developed and maintained by Facebook Database Engineering Team.
It is built on earlier work on LevelDB by Sanjay Ghemawat (sanjay@google.com)
and Jeff Dean (jeff@google.com)

This code is a library that forms the core building block for a fast
key value server, especially suited for storing data on flash drives.
It has a Log-Structured-Merge-Database (LSM) design with flexible tradeoffs
between Write-Amplification-Factor (WAF), Read-Amplification-Factor (RAF)
and Space-Amplification-Factor (SAF). It has multi-threaded compactions,
making it specially suitable for storing multiple terabytes of data in a
single database.

Start with example usage here: https://github.com/facebook/rocksdb/tree/master/examples

See the [github wiki](https://github.com/facebook/rocksdb/wiki) for more explanation.

The public interface is in `include/`.  Callers should not include or
rely on the details of any other header files in this package.  Those
internal APIs may be changed without warning.

Design discussions are conducted in https://www.facebook.com/groups/rocksdb.dev/
