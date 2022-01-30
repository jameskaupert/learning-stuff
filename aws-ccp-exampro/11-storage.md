# Storage

# Types of Storage Services

1. Block

- ie: Elastic Block Store (EBS)
  - data is split into evenly split blocks
  - directly accessible by the OS
  - supports only a single write volume
  - when you need a virtual hard drive to attach to a VM

2. File

- ie: Elastic File Storage (EFS)
  - File is stored with data and metadata
  - multiple connections via a network share
  - supports multiple reads, but writing locks the file
  - when you need a file-share where multiple users/VMs need to access the same drive

3. Object

- ie: S3
  - object stored with data, metadata, and unique ID
  - scales up with few limits (ie: no file or storage limits)
  - supports multiple reads and writes (no locks)
  - when you just want to upload files and not worry about underlying infrastructure
  - not intended for high IOPS

## S3

Object storage = data storage architecture that manages data as objects, as opposed to other storage architectures

S3 provides essentially unlimited storage without worrying about the infrastructure behind it

S3 Objects -> contain your data, like files. Consist of:

- key = name of the object
- value = data itself, made up of a sequence of bytes
- version ID = version of the object, if versioning enabled
- metadata = additional info attached to the object

S3 Buckets -> hold objects, can have folders that hold objects

- S3 is a universal namespace, so bucket names must be globally unique like domain names

Objects can be stored from 0 Bytes to 5 Terabytes in size
