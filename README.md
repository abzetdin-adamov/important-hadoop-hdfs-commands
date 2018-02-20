# Important Hadoop HDFS Commands
| Command | Description
|---|----|
| hadoop version | Returns the version of installed Hadoop |
| hdfs dfsadmin -report | Detailed report about HDFS, including available and used space, as well as healthiness of the file system |
| hdfs getconf -namenodes | Returns the list of NameNodes of the cluster |
| hdfs getconf -secondaryNameNodes | Returns the list of Secondary NameNodes of the cluster |
| hdfs getconf -confKey dfs.namenode.name.dir | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey yarn.resourcemanager.address | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey mapreduce.framework.name | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey dfs.namenode.name.dir | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey dfs.default.chunk.view.size | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey dfs.namenode.fs-limits.max-blocks-per-file | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs getconf -confKey dfs.replication | Returns the value of specific key from the HDFS config file hdfs-default.xml |
| hdfs dfs -ls / | Returnds the list of files and directories in root folder of the HDFS |
hdfs dfs -ls -R / | Returnds recursively the list of files and directories including the content sub-folders in root folder of the HDFS |
| hdfs dfs -cat /dir/file | Outputs the textual content of file |
| hdfs dfs -text /dir/file | Outputs the textual content of file |
| hdfs dfs -tail /dir/file | Same as previous two commands, but prints just last several lines |
| hdfs dfs -df -h / | Returns available and used space of HDFS |
| hdfs dfs -find / -name "filename" | Searches file "filename" in HDFS namespace |
| hdfs dfs -put /home/hadoop/data.csv /data | Copies file from Local file system to HDFS |
| hdfs dfs -copyFromLocal /home/hadoop/data.csv /data | Same as previous |
| hdfs dfs -get /data/data.csv /home/hadoop | Copies file from HDFS to the local file system |
| hdfs dfs -copyToLocal /data/data.csv /home/hadoop | Same as previous |
| hdfs dfs -cp /data/data.csv /user/hive | Copies file from one HDFS location (folder) to another HDFS location | 
| hdfs dfs -mv /data/data.csv /user/hive | Moves file from one HDFS location (folder) to another HDFS location | 
| hdfs dfs -rm /data/data.csv | Deletes file from HDFS |
| hdfs dfs -rm -r /data | Deletes directory from HDFS (even if not empty) |
| hdfs dfs -rmdir [--ignore-fail-on-non-empty] /data | Deletes empty directory, but if the key --ignore-fail-on-non-empty is used, directory will be deleted even if its not empty |
| hdfs dfs -stat [format] file | Returns statistical data related to file or directory |
| | Statistic Formats: |
| | %b  Size of file in bytes |
| | %F  Will return "file", "directory", or "symlink" depending on the type of inode |
| | %g  Group name |
| | %n  Filename |
| | %o  HDFS Block size in bytes ( 128MB by default ) |
| | %r  Replication factor |
| | %u  Username of owner |
| | %y  Formatted mtime of inode |
| | %Y  UNIX Epoch mtime of inode |
| | Example hdfs dfs -stat "%b %g %r" /file |
| | |
| hdfs dfs -du /file OR dir | Returns the length of file or aggregated size of files in directory |
| hdfs dfs -chgrp [R] /file or /dir | Changes group assosiation of file or directory. "R" can help to apply this action to all content of directory |
| hdfs dfs -chmod	/file or /dir | Specifies permission to file or directory. Example: hdfs dfs -chmod	644 /file (Read/Write for owner, Read-only for Group and Public) |
| hdfs dfs -chown /file or /dir | Changes the user who is owner of file or directory.
| hdfs fsck /data/news.txt -files | Returns general information about file |
| hdfs fsck /data/news.txt -files -blocks | In addition to previous, returns general information about each block the file divided to |
| hdfs fsck /data/news.txt -files -blocks -locations | In addition to previous, returns location of each block's replica (hostname/IP address) |
|hdfs dfs -usage HDFScommand | Returns description/syntax of usage of the specified HDFS command |
