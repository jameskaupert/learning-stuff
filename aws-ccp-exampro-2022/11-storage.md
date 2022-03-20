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

### S3 Storage Classes

AWS offers a range of S3 storage classes that trade retrieval time, accessibility and durability for cheaper storage

- S3 Standard (default) = fast, 99.99% availability, 11 9's durability. Replicated across at least 3 AZs
- S3 intelligent tiering = uses ML to analyze object usage and determine appropriate storage class. Data is moved to the most cost-effective access tier, without any performance impact or added overhead
- S3 standard-IA (infrequent access) = still fast. Cheaper if you access files less than once per month. Additional retrieval fee applied. 50% less than standard, with reduced availability
- S3 One-Zone-IA = still fast. Objects only exist in 1 AZ. Availability is 99.5%. Cheaper than standard IA by 20%. Data could get destroyed. Retrieval fee applied
- S3 Glacier = long term storage. Retrieval of data can take minutes to hours, but is very cheap storage
- S3 Glacier Deep Archive = lowest cost storage class. Retrieval time is 12 hours

## AWS Snow Family

Snow family -> storage and compute devices used to physically move data in or out of the cloud when moving data over the internet or private connection is too slow, difficult, or costly

Snowcone - two sizes (8TB storage on HDD and 14TB storage on SSD)
Snowball Edge - two types (storage optimized with more memory 80TB, and compute optimized 39.5TB)
Snowmobile - tractor trailer with 100PB of storage, scalable to exabytes with multiple trucks

Data is delivered to S3

# Storage Services Comparison

- S3 = serverless object storage service
- S3 Glacier = cold storage service (archiving and long-term backup)
- Elastic Block Store (EBS) = persistent block storage service. Virtual hard drive in the cloud, attached to EC2s. Choose the type of hard drive you want (SSD, IOPS SSD, Throughput HDD, Cold HDD)
- Elastic File Storage (EFS) = cloud-native NFS file system service. File storage you can mount to multipe EC2s at the same time. For when you need to share files between multiple servers
- Storage Gateway = hybrid cloud storage extending on-premise storage to the cloud
  - File Gateway extends local storage to s3
  - Volume Gateway caches local drives to s3 to have continuous backup of local files in the cloud
  - Tape Gateway stores files onto virtual tapes for backing up files on very cost effective long term storage
- AWS Snow Family = storage devices used to physicall migrate large amounts of data to the cloud
- AWS Backup = fully managed backup service via backup plans
- CloudEndure Disaster Recovery = continuously replicates machines into a low-cost staging area in target AWS account and preferred region, enabling fast and reliable recovery in case of IT data center failures
- Amazon FSx = feature rich and highly performant file system. Can be used for Windows (SMB) or Linux (Lustre)
