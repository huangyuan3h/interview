# a file system

### 1. Background Knowledge

#### md5 sum

md5sum could generate the check string base on file content.

web: [http://pajhome.org.uk/crypt/md5/instructions.html](http://pajhome.org.uk/crypt/md5/instructions.html)



#### md5&#x20;

Is md5 uniform distribute?

[https://liam.page/2015/08/12/does-the-result-of-md5-hash-function-uniform/](https://liam.page/2015/08/12/does-the-result-of-md5-hash-function-uniform/)

Yes.



example for email: huangyuan3h@gmail.com :

```
24495927ca3e32ad0baf6a377b01d061
```

Let's say one user will cost 128 bytes.

One table can store 16,777,216 user.

let say in this world we have 8 billion, so we need 476.837158203 tables.

So we just need 512 tables to store user data for this world.



#### when to divided the table:

![](<.gitbook/assets/image (9).png>)

it depends on innodb buffer pool size. the default in mysql is 2 gb. which means it is higher than 2 gb, we should consider to divided the table.





### 2. Basic concept

![](<.gitbook/assets/image (7).png>)





### 3. ER diagram

![basic ER diagram](<.gitbook/assets/image (1).png>)

### 4. High level architecture

![high level architecture V1](<.gitbook/assets/image (4).png>)

This is the v1 at very beginning to design.&#x20;

![high level architecture with extended function v2](<.gitbook/assets/image (6).png>)

This one is to add ELK and kafka support.



Do you find any problem in these 2 diagram?

1. hdfs is nice tool for large file
2. the input and i/o is not divided they are in the same MS

![divided the file service to 2 v3](.gitbook/assets/image.png)



![replace the hdfs to hybrid file system](<.gitbook/assets/image (3).png>)



![detail of file system](<.gitbook/assets/image (5).png>)

Why in the first several version, it is based on hadoop hdfs, but it has been change to be managed by different size of file?

The reason is hdfs is a tool for large files, but no the file for small image, some text file. If store too much small file into hdfs, the `name node` would generate the configure info for these small files, which would slow down hadoop system.  There is one solution to solve this problem call "har" in hadoop, which archive the the small file into big file block. But still, it is not prefect. So, still use another system to store small file.

### 5. Cache/proxy layer

varnish: [https://varnish-cache.org/](https://varnish-cache.org/)

Apollo server redis cache

Apollo client in-memory cache



### 6. api design&#x20;



1. auth: login, register, reset flow, Delete account
2. user: getUserInfo, editUserInfo,

As these api is common function, so we skip it.

#### File related API

1. upload file







2\. upload files







3\. getFileByFileId



