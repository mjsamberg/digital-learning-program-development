---
layout: page
title: "Networks and Disaster Recovery Planning"
course: "dlprograms"
unit: 7
---
## Principle of Least Privilege
One of the core principles of cybersecurity is the _Principle of Least Privilege_. The Principle of Least Privilege is the concept that any user should not have access to things that they don't need to do their jobs. Restricting the number of files and computers a user can compromise is a way to reduce your overall attack surface.

Think about it this way: how many Google Docs do you have access to right now that are part of your job? How many of them do you have write access to? While the data in these docs is probably not confidential or critical, they are potential attack vectors. Now consider how many docs you have access to because someone shared a whole folder with you. Now, consider that someone accidentally places a file with contact information for all of their students in that folder without realizing who has access. Boom...data breach. It's important to educate users to share files responsibly and while "everyone with the link" is convenient, is a potential disaster waiting to happen.

The same is true for other systems as well. Your student information system, HR and finance systems, and even your library management system are all targets for attack as they contain personal data. Users shouldn't be able to read or write data in these systems unless it's a part of their core job function - it's our nature sometimes to "over-provision" accounts - to provide more access than is necessary so that a user can do whatever they need to do in the system without having to set up more granular access controls. This over-provisioning increases the amount of damage a compromised account can inflict. 

The same principles apply in your network configurations. While some devices (like AppleTVs and Chromecasts) need to be able to broadcast and be seen on the network, most devices don't. Malware often spreads by broadcasting on the network and looking for potential exploits. Preventing computers on the network from talking to other computers is a potential mitigation strategy - and preventing computers from talking to other computers across the WAN is a critical mitigation strategy. 

### Privilege Separation
As a part of the principle of least privilege is a concept called _privilege separation_. As CTOs, you'll have administrative access to many systems. However, for a majority of your job functions, you'll be interacting as a user. For example, if you're a librarian, you may have administrative access to configure your library management system, but your primary day-to-day usage in the system is to circulate and catalog books. Privilege separation means that superuser access is separated from the day-to-day access such that you only use the superuser account when you need to do specific tasks that require it.

Example: by default, when you set up your computer, your account is provisioned with administrative rights that allow you to do things like install software. While many districts give teachers administrative rights to their devices because they "trust teachers to do the right thing", this is a security vulnerability because the IT department is responsible for vetting software installations and in the event a teacher's machine is compromised by software they should not have installed, they have the rights to compromise their own machines which in turn may compromise others. In fact, I don't run my computer with administrative rights for this reason. I have a separate account on my personal laptop that I use when I need to install software and Mac OS or Windows prompts me for an administrative username and password.

In addition, I do not ever allow my staff to log in to a workstation with an account that has administrative privileges to make changes in Active Directory. Each of my technicians has their user account that they use to log in to computers as a regular user, and then a workstation administrative account that they can use if they need administrative rights to fix a computer. My Active Directory admins have a third account that does not provide administrative access on workstations and is restricted to login on specific devices, but allows for changes in Active Directory.

## Patch Management
The easiest thing you can do to protect a computer network from being a victim of a cyberattack is to keep all of your software current and up-to-date. Configuration management systems such as JAMF, as discussed in Unit 4, can be used to ensure that operating systems stay up-to-date by deploying configurations to force computers to run Windows Update or Mac Update. ChromeOS devices will update themselves automatically. Beyond updating the operating system, steps need to be taken to keep other software up-to-date. User training on how to update software, combined with putting hands on computers frequently in order to keep software updated is critical. Additionally, using App Stores in lieu of manual installations is preferable as the software in app stores is vetted, and all of the applications that are downloaded from an app store are updated at one time, and this process can often be automated. 
  
In addition to workstations, any Internet connected device in your school is a potential attack vector. Your phones and phone systems, printers, HVAC systems, lighting systems, servers, applications, PA systems, etc. are all potential targets for attack or vectors that can be used to attack other systems. These systems can also be impacted by ransomware attacks (many phone systems have been compromised in ransomware attacks). These devices all need to be patched and maintained (which is another argument for standardization). In the event that a device can no longer be patched or upgraded, it is a liability and should be discarded.

## Anti-Malware Tools
Beyond patching, there are a variety of tools that can proactively detect malware on a computer and prevent a computer from being infected or spread. [Google Suite][1] and [Office 365][2] feature built-in anti-phishing and anti-malware protection that can automatically detect and quarantine malware and flag potential phishing emails. Content filters like [ZScaler][3] and many firewalls can also proactively detect and block malware.  

On your computer, tools like [Windows Defender][4] (built-in to windows) and [DetectX for Mac][5] can be used to identify and protect computers from malware by referencing and looking for known executable files. These tools contain profiles that need to be kept up-to-date to find the latest malware. ChromeOS and iOS are locked-down enough that they don't need anti-malware tools because they're built in to the way the OS works. On Android devices, malware is a possibility, but can be avoided by only downloading apps from the Play Store. 

## Managed Services
One of the advantages of using hosted, managed services, especially for critical systems, is that it shifts the responsibility for patching and management from you as the CTO to the vendor. Instead of needing to take responsibility for your keeping your servers secure, patched, and isolated, a managed service does this for you. In addition, if a managed service is breached through technical means (not due to a privilege issue or a compromised account), the vendor of that service is liable which protects both the CTO and the district both legally and financially.  

## Disaster Recovery Plans
Despite your best plans and tightest security, you may still end up with a data breach or a malware attack. Like many other potential disasters that may impact a school system, this is one that needs to be planned for. In the event of a data breach, the impacted system should be shut down immediately and local authorities should be notified. They'll provide direction and begin a detailed investigation to determine how the attacker got in, and what (if any) data was stolen or compromised. In the event that the issue was caused by an unpatched vulnerability, districts (or a liable service provider) may have to provide identity theft protection for a year and pay for any damages that result from the theft of personal data. 

For a malware or DDoS attack, a device should be isolated and removed from the network, the hard drive formatted while offline, and the software reinstalled from scratch. Files should be restored from backup.

### Backups
Backups are a critical strategy for mitigating malware attacks. Any cloud-based service (like Google Drive) has built-in backups, though files may have to be restored one at a time. 

However, a comprehensive backup strategy is critical. On-premises servers and configurations should be backed up routinely, and backup history stored for at least 30 days. Ideally, this is done using an off-site cloud-backup solution (such as Barracuda Cloud Backup or Backupify). Off-site, cloud-based backups reduce the risk of the backup system itself being compromised.

Some districts still use tape backup systems to back up servers, These systems are time-tested and highly effective. However, in these systems, tapes should also be transferred off site to prevent data loss in the event of a fire or other catastrophic event in the building. For example in the last district where I used tape backup systems, I had one set of tapes each month moved from our district office to a safe deposit box in Raleigh since our school district flooded several times. 

Some cloud backup tools will also back up users Google Drives and OneDrives so that they can also be restored in the event of data loss. 

[1]:	https://support.google.com/a/answer/9157861?hl=en
[2]:	https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection?view=o365-worldwide
[3]:	https://help.zscaler.com/zia/configuring-malware-protection-policy
[4]:	https://www.microsoft.com/en-us/windows/comprehensive-security
[5]:	https://sqwarq.com/detectx/