Description:
  Compare multiple paths recursively with a probabilistic algorithm

Usage:
  diffuzzy [options] path1 path2 path3...

Options:
  -h, --help
    Output this help message and exit.
  -m,--method method1,method2,...
    A comma-separated list of which comparisons to run:
      existential  default  Detect missing objects
      type         default  Detect mismatched file types
      size         default  Detect file size mismatches
      header       default  Compare the first 512 bytes
      footer       default  Compare the last 512 bytes
      offsets      default  Compare floor(log(2,size)) random 512 byte offsets
  --unittest
    Perform unit tests to verify functionality of this script.
  -v
    Output each set of files that are compared.

Version:
  diffuzzy 0.0.0.0
  Copyright (C) 2018 Nathan Shearer
  Licensed under GNU General Public License 2.0
