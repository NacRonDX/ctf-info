An important concept that everyone who has worked on the study of Operating Systems is the idea of caching. Files are cached in memory for system performance as they are accessed and used. This makes cache an important source for collecting valuable info.

The dumpfiles plugin has many options. Let us have a look at what they are:
```
-r REGEX, --regex=REGEX
                        Dump files matching REGEX
  -i, --ignore-case     Ignore case in pattern match
  -o OFFSET, --offset=OFFSET
                        Dump files for Process with physical address OFFSET
  -Q PHYSOFFSET, --physoffset=PHYSOFFSET
                        Dump File Object at physical address PHYSOFFSET
  -D DUMP_DIR, --dump-dir=DUMP_DIR
                        Directory in which to dump extracted files
  -S SUMMARY_FILE, --summary-file=SUMMARY_FILE
                        File where to store summary information
  -p PID, --pid=PID     Operate on these Process IDs (comma-separated)
  -n, --name            Include extracted filename in output file path
  -u, --unsafe          Relax safety constraints for more data
  -F FILTER, --filter=FILTER
                        Filters to apply (comma-separated)
```

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 dumpfiles -Q <Offset> -D <dump folder>
