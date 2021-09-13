
# Azure Storage

## Disk storage

Dis Storage provides disks for Azure virtual machines. Applications and other services can access and use these disks as needed, similar to how thy would in on-premises scenarios. Disk Storage allows data to be persistently stored and accessed from an attached virtual hard disk.

- SSD Solid-state-drives (standard, premium and ultra disks)
- HDD Hard-disk-drives

## Azure Blob storage

Azure object storage solution for the cloud. It can store massive amounts of data, such as text or binary data. Azure Blob Storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. Blob Storage can manage thousands of simultaneous uploads, massive amounts of video data, constantly growing log files, and can be reached from anywhere with an internet connection.

Ideal for:

- Serving images or documents directly to a browser.
- Storing files for distributed access.
- Storing up to 8 TB of data for virtual machines.
- Storing data for analysis by an on-premises or Azure-hosted service.
- Storing data for backup and restore, disaster recovery, and archiving.
- Streaming video.

You store blob in containers, which helps you organize your blobs depnding on your business needs.

Build for Scale and Performance, up to petabytes and support for Gbps transfer rates.

| Type | Description |
| ---- | ----------- |
| Block Blob | Optimized for streaming content (images or video files)
| Append Blob | Block blobs which are optimized for append operations (log files)
| Page Blob | Optimized for random read/write operations. (Virtual Machine Disks)

### Custom Domains

You can use Custom domains to link your Container Blob service to your Domain via CNAME

## Azure Files

Azure Files offers fully managed file shares in the cloud that are accessible via the industry standard Server Message Block and Network File System (preview) protocols. Azure file shares can be mounted concurrently by cloud or on-premises deployments of Windows, Linux, and macOS. Applications running in Azure virtual machines or cloud services can mount a file storage share to access file data, just as a desktop application would mount a typical SMB share. Any number of Azure virtual machines or roles can mount and access the file storage share simultaneously. Typical usage scenarios would be to share files anywhere in the world, diagnostic data, or application data sharing.
Designed for SMB (server message block protocol) connectivity. Extended by Azure File Sync.

Use it for:

- Many on-premises applications use file shares. Azure Files makes it easier to migrate those applications that share data to Azure. If you mount the Azure file share to the same drive letter that the on-premises application uses, the part of your application that accesses the file share should work with minimal changes, if any.
- Store configuration files on a file share and access them from multiple VMs. Tools and utilities used by multiple developers in a group can be stored on a file share, ensuring that everybody can find them, and that they use the same version.
- Write data to a file share, and process or analyze the data later. For example, you might want to do this with diagnostic logs, metrics, and crash dumps.

One thing that distinguishes Azure Files from files on a corporate file share is that you can access the files from anywhere in the world, by using a URL that points to the file. You can also use Shared Access Signature (SAS) tokens to allow access to a private asset for a specific amount of time

You can set up *Quotas* and *Snapshots*

### Azure files connectivity

******

| Protocol | Encryption support in transit |  Access Control Support
| - | - | -
| SMB 2.1 | No | Account Keys and Azure AD Domain Services
| SMB 3.0 | Yes | Account Keys and Azure AD Domain Services
| REST/HTTP | Yes | Account Keys and Shared Access Signatures

## Blob access tiers

- **Hot access tier**: Optimized for storing data that is accessed frequently (for example, images for your website).
- **Cool access tier**: Optimized for data that is infrequently accessed and stored for at least 30 days (for example, invoices for your customers).
- **Archive access tier**: Appropriate for data that is rarely accessed and stored for at least 180 days, with flexible latency requirements (for example, long-term backups).

The following considerations apply to the different access tiers:

Only the hot and cool access tiers can be set at the account level. The archive access tier isn't available at the account level.
Hot, cool, and archive tiers can be set at the blob level, during upload or after upload.
Data in the cool access tier can tolerate slightly lower availability, but still requires high durability, retrieval latency, and throughput characteristics similar to hot data. For cool data, a slightly lower availability service-level agreement (SLA) and higher access costs compared to hot data are acceptable trade-offs for lower storage costs.
Archive storage stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data.

## Azure Queues

Ideal for messaging and integration service. Aids in the integration of loosely coupled solutions.

## Azure Tables

Simple storage for non-relational semi-structured data. Useful in modern cloud solutions storing key/attribute data.

## Storage Account

Overall container for any storage type it includes properties such as

- Account Kind (influences the feature and pricing).
- Performance Tier (determines performance characteristics)
- Replication (Configures redundancy and high availability for the underlying storage and infrastructure)
- Access Tier (Changes pricing models based on access levels)

### Account Kind

| Type | Recommended |
:-: | ----:
General-purpose v2(GPv2) | Recommended type for blobs, files, queues, and tables.
General-purpose v1(GPv1) | Legacy type for blobs, files, queues and tables
BlobStorage | Legacy type which only supports blobs.
BlockBlobStorage (premium) | Blob only type, specific to the 'Premium' performance tier.
FileStorage (premium) | File only type, specific to the 'Premium' performance tier.

### Performance Tier

| Type | Recommended |
| ---- | ----- |
Standard | Default performance tier with typical speeds for most production loads
Premium | High performance when required by specific services: GPv1/GPv2: for unmanage disks and page blobs only, BlobStorage: does not support Premium tier, BlockBlobStorage: block and append blobs only, FileStorage: for files only.

### Replication

| Type | Description
| ---- | ----------- |
| Locally-redundant storage (LRS) | Synchronous replication to three other scale units within the region. Low cost option.
| Zone-redundant storage (ZRS) | Synchronous replication to three availability zones within the region.
| Geo-redundant storage (GRS) | Asynchronous replication to a secondary region. Also includes LRS-like replication.
| Geo-zone-redundant storage (GZRS) | A combination of ZRS and GRS (without LRS replication)

### Access Tier

| Type | Description |
| ---- | ----------- |
| Hot | Economic storage tier used when data is being modified fequently
| Cool | Cheaper (Than hot) storage tier that is used when data is being modified less fequently
| Archive | Chapest storage tier tha is used when data can remain offline for long periods of time.

## Connectivity for Storage

| Type | Connectivity |
| ---- | ------------- |
| Public Endpoints | Azure Storage services are built for public accessibility. By default, all services have a publicly accessible endpoint
| Firewall | Using a Storage Account Firewall, it is possible to restrict netowrk access to all services that exist within a storage account
| Network Integration | Service Enpoints, Private Link allow us to change the netwok accessibiity of Azure Storage services.

## Access Controls for Storage Accounts

- Data Layer: Access to the data that resides in the SA itself.

- Management Layer: Access to perform administration and configuration tasks.

| Access Control | Description |
| -------------- | ----------- |
| Access Keys | The least secure access control method, which can provide full management and data layer access. Only recommended for service applications. Access Keys can be regenerated to revoke access.
| Shared Access Signatures (SAS) | Provides access to resources within a single service, or across one or more services within a storage account. Whoever has the SAS, is granted ALL the access granted by the SAS policy. Can be assoicated with an access policy to provide more control.
Role Based Access Control (RBAC) | Used to control the permissions of an Azure Active Directory (AD) identity, with respect to storage account management or data layer access.

### Shared Access Signature

- Account SAS: Provides access to resources within one or more services within a storage account

- Service SAS: Provides access to resources within a single service (blob or files)

- Access Policies: Provide greater control over a SAS. (after creation)
