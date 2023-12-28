# Azure Confidential Computing: Confidential Temp Disk Encryption

## Description

One of the things I think that Microsoft's Confidential Compute team has to get right to make the offering more compelling is to raise the feature parity with what is currently already available on Azure. I can imagine that this is no easy feat, since there's years of development that have gone into making those features. Things like support for Azure Site Recovery and Azure Backup are on the top of my wish list, but these are two services that would be extremely complex to get working right, especially since you'd have to make sure that the vTPM keys are somehow synced between the regions. The decision to pursue such features also raises philosophical questions, as the core principle hinges on Microsoft maintaining no access.

Similar complexities arise in the realm of disk encryption for Azure confidential computing. so I was pleasantly surprised to read about [the public preview of "temporary disk encryption"](https://techcommunity.microsoft.com/t5/azure-confidential-computing/confidential-temp-disk-encryption-for-confidential-vms-in-public/ba-p/3971393). Temporary disk encryption for AMD SEV-SNP confidential VMs will allow Azure customers to encrypt the temporary disk attached to their Confidential VMs using platform or customer-managed keys. This ensures any sensitive data on those disks is protected at rest.

It's worth noting that disk encryption in Azure's confidential computing offerings differs from the conventional Azure Disk Encryption. Confidential VMs employ a process known as Confidential OS disk encryption (sometimes known as full disk encryption), focusing solely on encrypting the OS disk. This is in contrast to the mechanism used in typical scenarios involving Azure Disk Encryption for encrypting other types of disks, including temporary disks and data disks.

What's even better, is that the implementation of this encryption mechanism appears to leverage the __Secure Key Release__ mechanism, a topic I've previously discussed in [my other blog posts](/tags/secure-key-release/).

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FThomVanL%2Fblog-2023-12-azure-confidential-computing-temp-disk-encryption%2Fmain%2Fbicep%2Fmain.json)

## 🔗 Links

- [Azure Confidential Computing: Confidential Temp Disk Encryption (12/2023)](https://thomasvanlaere.com/posts/2023/12/azure-confidential-computing-confidential-temp-disk-encryption/)
