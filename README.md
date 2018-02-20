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


hdfs dfs -ls / 
hdfs dfs -ls -R / 
hdfs dfs -cat /dir/file

hdfs dfs -text /dir/file

hdfs dfs -tail /dir/file


hdfs dfs -df -h /

hdfs dfs -find / -name "filename"

hdfs dfs -put (copyFromLocal)
hdfs dfs -get (copyToLocal)

hdfs dfs -cp course destination 

hdfs dfs -mv

hdfs dfs -rm

hdfs dfs -rm -r

hdfs dfs -rmdir [--ignore-fail-on-non-empty] # if the key --ignore-fail-on-non-empty is used, directory will be deleted even if its not empty

hdfs dfs -stat [format]

hdfs dfs -stat "%b %g %r" /file

Stat Formats:
%b  Size of file in bytes
%F  Will return "file", "directory", or "symlink" depending on the type of inode
%g  Group name
%n  Filename
%o  HDFS Block size in bytes ( 128MB by default )
%r  Replication factor
%u  Username of owner
%y  Formatted mtime of inode
%Y  UNIX Epoch mtime of inode

hdfs dfs -du /fileORdir 	# returns the length of file or aggregated size of files in directory

hdfs dfs -chgrp [R]

hdfs dfs -chmod		# specifies permission

hdfs dfs -chown

hdfs dfs -usage HDFScommand		# describes the usage of the HDFS command


hdfs fsck /data/news.txt 	#general information about file

hdfs fsck /data/news.txt -files 
