# 1. Crear directorio precious

Upload al nodo de AWS del ZIP usando WinSCP

[root@ip-172-31-11-253 centos]# ll /tmp/SEBC*.zip
-rw-rw-r-- 1 centos centos 474831 Oct  2 14:54 /tmp/SEBC-master-students.zip

[hdfs@ip-172-31-11-253 centos]$ sudo su hdfs
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -mkdir /precious

hdfs dfs -copyFromLocal /tmp/SEBC-master-students.zip /precious


# 4. Borrar directorio

No me deja

[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots

# 5. Borrar zip

[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -rm /precious/SEBC-master-students.zip
17/10/03 15:17:41 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/precious/SEBC-master-students.zip' to trash at: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master-students.zip

