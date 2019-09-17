Description:
  Compare multiple paths recursively with a probabilistic algorithm

Usage:
  diffuzzy [OPTION]... PATH1 PATH2 [PATH3]...

Options:
  -h, --help
    Output this help message and exit.
  -m,--method method1,method2,...
    A comma-separated list of which comparisons to run:
      existential   default  Detect missing objects
      mode                   Compare file mode bits
      type          default  Compare file types
      size          default  Compare file size
      data          default  Compare file data
      header        default  Compare the first 512 bytes
      footer        default  Compare the last 512 bytes
      offsets       default  Compare floor(log(2,size)) random 512 byte offsets
  --unittest
    Perform unit tests to verify functionality of this script.
  -v
    Output each set of files that are compared.

Details:
  The data comparison method will compare all bits if the files are 4096 bytes
  or smaller. If the files are larger than 4096 bytes, then the header, footer,
  and floor(log(2,size)) random 512 byte offsets are compared.

Version:
  diffuzzy 2.1.2.0
  Copyright (C) 2018 Nathan Shearer
  Licensed under GNU General Public License 2.0
