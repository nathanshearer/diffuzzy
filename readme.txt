Description:
  Compare objects with adjustable accuracy and speed

Usage:
  diffuzzy [OPTION]... PATH1 PATH2 [PATH3]...

Options:
  -h, --help
    Output this help message and exit.
  -m,--method method1,method2,...
    A comma-separated list of which comparisons to run:
      e,existential  default  Detect missing objects
      m,mode                  Compare file mode bits
      t,type         default  Compare file types
      s,size         default  Compare file size
      d,data         default  Compare header, footer, and offsets
      h,header       default  Compare the first 512 bytes
      f,footer       default  Compare the last 512 bytes
      o,offsets      default  Compare a set of 512 byte offsets
      b,blockdata             Compare block device data
  --offsets rlog2
    A comma-spearated list of 512 byte offsets to compare:
      rlog2    A set of floor(log(2,size)) random 512 byte offsets. Default.
      log2     1,2,4,8,... up to floor(log(2,size))
      log2log  1,2,4,8,...,last-1,last-2,last-4,last-8...
      n        Specify how many random 512 byte offests.
  --unittest
    Perform unit tests to verify functionality of this script.
  -v
    Output each set of files that are compared.
  --verbose #
    Use more or less verbose output. Valid values are:
      0  Default. No output.
      1  Show compared files.
      2  Show detailed comparison information.

Examples:
  Compare three different paths recursively with fast random offsets
    diffuzzy /mnt/storage /mnt/backup_local /mnt/backup_offsite
  Compare two paths with additinal offsets for higher accuracy
    diffuzzy --offsets log2log,rlog2 /mnt/storage /mnt/backup_local
  Compare only one random offset to minimize load
    diffuzzy --offsets 1 /mnt/storage /mnt/backup_offsite
  Verify objects exist with matching size
    diffuzzy -m e,s /mnt/storage /mnt/backup_offsite
  Verify objects exist with matching mode bits
    diffuzzy -m e,m /var/public /mnt/remote-public

Version:
  diffuzzy 2.3.1.0
  Copyright (C) 2018 Nathan Shearer
  Licensed under GNU General Public License 2.0
