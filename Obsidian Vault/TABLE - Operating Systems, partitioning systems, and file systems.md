
| OS            | Partitioning | System                     | /////                      | ///// | File                             | /////                   | System                  | /////                      | ///// |
| ------------- | ------------ | -------------------------- | -------------------------- | ----- | -------------------------------- | ----------------------- | ----------------------- | -------------------------- | ----- |
| ///////////// | MBR          | GPT                        | NTFS                       | FAT32 | ReFS                             | XFS                     | ext4                    | APFS                       | exFAT |
| Windows       | Yes          | **Yes, required for boot** | **Yes, required for boot** | Yes   | Yes, designed for Windows Server | Read/write w/ 3rd party | Read only w/ 3rd party  | Read/write w/ 3rd party    | Yes   |
| macOS         | Yes          | **Yes, required for boot** | Read only                  | Yes   | Read/write w/ 3rd party          | Read/write w/ 3rd party | Read/write w/ 3rd party | **Yes, required for boot** | Yes   |
| Linux         | Yes          | **Yes, preferred**         | Yes                        | Yes   | Read/write w/ 3rd party          | Yes                     | **Yes, preferred**      | Read/write w/ 3rd party    | Yes   |
| Chrome OS     | Yes          | **Yes, preferred**         | Yes                        | Yes   | No                               | No                      | No                      | No                         | Yes   |
|               |              |                            |                            |       |                                  |                         |                         |                            |       |
