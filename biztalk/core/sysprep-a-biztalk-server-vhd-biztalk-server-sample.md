---
title: Sysprep BizTalk Server VHD （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35f0146d-60ed-4265-983a-0e3665ef2ae4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2791dc77e70e294afbe1e3ef8670df3a03282dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393862"
---
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a>Sysprep BizTalk Server VHD （BizTalk Server 示例）
Sysprep 创建的虚拟机与快照[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便进行快速部署其他虚拟机上安装。  
  
## <a name="prerequisites"></a>先决条件  
 使用 Sysprep 之前，应具有与 HYPER-V 使用虚拟机的一些知识。 你还应具有 BizTalk Server 和所有必备条件的全新、 典型安装的虚拟机。  
  
 Sysprep 将在 Windows Server 2008 和 Windows Vista SP1 上运行。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 创建的 VHD，Sysprep[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便进行快速部署其他虚拟机上安装 （包括操作系统和所有前提条件）。 创建使用 Sysprep 的映像将选择新的计算机名以加入到域中第一次启动的时。 若要获取 BizTalk Server 正常运行，就需要更新的计算机名称存储在注册表和数据库的不同实例。  
  
 本文档假定 BizTalk Server 配置为在一台计算机上运行并演示如何使用新名称更新计算机名称的其他实例。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*Samples Path*\>\Admin\Sysprep\  
  
 下表显示了本示例中的文件及其用途说明：  
  
> [!NOTE]
>  下表中的.vbs 和.cmd 文件都自动在 Sysprep 应答文件 （Sysprep.xml 和 SetupCompletecmd.txt） 中，并仅适用于参考此处列出。 如果需要手动运行这些脚本，则它们在表中显示的顺序运行它们。  
  
|文件|Description|  
|----------|-----------------|  
|Sysprep.xml|答案文件|  
|SetupCompletecmd.txt|答案文件|  
|ReplaceMachineName.vbs|目的：打开文件并使用当前的计算机名称替换给定字符串的所有实例。 若要准备其他脚本和 xml 文件，并更新 bm.exe.config 非常有用。<br /><br /> 用法：ReplaceMachineName.vbs\<文件以打开\>\<要替换的字符串\>|  
|UpdateRegistry.vbs|目的：更新存储在 BizTalk 注册表设置中的计算机名称。<br /><br /> 用法：UpdateRegistry.vbs \<UpdateInfo.xml\>。 请确保 $ （oldcomputername） 和 $ （newcomputername） 此 xml 文件中的所有实例替换都为。|  
|UpdateDatabase.vbs|目的：更新存储在 BizTalk 管理数据库中的计算机名称。<br /><br /> 用法：UpdateDatabase.vbs \<UpdateInfo.xml\>|  
|UpdateBAMDb.vbs|目的：更新存储在 BAM 数据库中的计算机名称。<br /><br /> 用法：UpdateBamDb.vbs \<UpdateInfo.xml\>|  
|UpdateSSO.cmd|目的：重新配置企业单一登录 (SSO) 密钥服务器。<br /><br /> 用法： sso.cmd \<UpdateInfo.xml\>|  
|UpdateSqlServerAndInstanceName.cmd|目的：重新配置 SQL 和 SQL Express、 重新启动一系列的依赖服务，并重新注册 BAMAlerts。<br /><br /> 用法：编辑脚本并替换所有 $(NEWCOMPUTERNAME) 实例并更新 BAM 警报的 serviceusername 和 servicepassword。 然后运行 UpdateSqlServerAndInstanceName.cmd，作为第一个参数传递旧计算机名称。|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a>创建答案文件和运行 Sysprep  
  
#### <a name="to-create-the-answer-files"></a>若要开始创建答案文件  
  
1. 安装和配置 BizTalk Server 的虚拟机上。 请确保使用默认安装和配置选项，因为 Sysprep 不支持自定义的安装。  
  
2. 将包含"scripts"文件夹的内容复制到 C:\Scripts，虚拟机上。  
  
3. 通过修改 Sysprep.xml 中的以下行准备 sysprep 应答文件。 (注意：这些行标记为"！" 之前它们。）可以使用这些作为模板，或进行您自己，并通过复制\<FirstLogonCommands\>部分。  
  
   - $ （oldcomputername） 替换为虚拟机的当前计算机名称。  
  
   - 用户帐户  
  
   - 密码  
  
   - 任何公司详细信息还应更新 UpdateSqlServerAndInstance.cmd 和你 Sysprep.xml 中。  
  
     或者，可以使用使用从头创建 Sysprep 应答文件[自动安装工具包 (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) Windows Server 2008 上。 确保你\<FirstLogonCommands\>部分与示例相匹配，以便 BizTalk 脚本将在首次启动上运行。  
  
#### <a name="to-run-sysprep"></a>若要运行 Sysprep  
  
1. 打开命令提示符并运行 Sysprep。 该命令将如下所示：  
  
   ```  
   C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
   ```  
  
2. Sysprep 需要大约半个小时运行。 完成后，它将自动关闭虚拟机。  
  
3. 关闭虚拟机后，合并所有快照，并将 VHD 文件复制到安全位置。  
  
4. 现在，VHD 已准备好完整操作系统、 BizTalk Server 和所有必备项与其他虚拟机上部署。  
  
   **SetupCompletecmd.txt**  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 **Sysprep.xml**  
  
```  
- <!--   
References:  
"Unattended Installation Settings Reference" @ http://technet.microsoft.com/library/cc749204.aspx  
"How to Sysprep in Windows 2008 " @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008  
  
Make sure to modify the values specified for the   
<Credentials> and <DomainAccounts> sections of this unattend file.  
  
SetupComplete.cmd should be copied to the C:\Windows\Setup\Scripts\ folder before running sysprep.  
Contents of SetupComplete.cmd:  
  
del /Q /F c:\windows\system32\sysprep\sysprep.xml   
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
Sysprep.xml (this file) should be copied to the C:\Windows\System32\sysprep\ folder.  
  
Run sysprep with the following options:  
  
sysprep /generalize /oobe /shutdown /unattend:sysprep.xml  
  -->   
  <?xml version="1.0" encoding="utf-8" ?>   
- <unattend xmlns="urn:schemas-microsoft-com:unattend">  
- <settings pass="oobeSystem">  
- <component name="Microsoft-Windows-International-Core" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <InputLocale>0409:00000409</InputLocale>   
  <SystemLocale>en-US</SystemLocale>   
  <UILanguage>en-US</UILanguage>   
  <UILanguageFallback>en-US</UILanguageFallback>   
  <UserLocale>en-US</UserLocale>   
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <UserAccounts>  
- <!--   
This sets the password for the Administrator account back to pass@word1   
  -->   
- <AdministratorPassword>  
  <Value>pass@word1</Value>   
  <PlainText>true</PlainText>   
  </AdministratorPassword>  
- <!--   
Enter the appropriate value for the <Name> and <Domain> elements here,   
this group/account will be added to the local Administrators and Remote Desktop Users groups.  
  -->   
- <DomainAccounts>  
- <DomainAccountList wcm:action="add">  
- <DomainAccount wcm:action="add">  
  <Name>MSMQ4TR</Name>   
  <Group>Administrators;RemoteDesktopUsers</Group>   
  </DomainAccount>  
  <Domain>Northamerica.corp.microsoft.com</Domain>   
  </DomainAccountList>  
- <!--   
Additional DomainAccountList section. Uncomment/modify this section if you need to add   
groups / users from multiple domains to the local Administrators and Remote Desktop Users groups.  
                    <DomainAccountList wcm:action="add">  
                        <DomainAccount wcm:action="add">  
                            <Name>OsloVM_NTDev</Name>  
                            <Group>Administrators;RemoteDesktopUsers</Group>  
                        </DomainAccount>  
                        <Domain>Ntdev.corp.microsoft.com</Domain>  
                    </DomainAccountList>  
  -->   
  </DomainAccounts>  
  </UserAccounts>  
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.  
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <TimeZone>Pacific Standard Time</TimeZone>   
- <Display>  
  <ColorDepth>16</ColorDepth>   
  <HorizontalResolution>1024</HorizontalResolution>   
  <VerticalResolution>768</VerticalResolution>   
  </Display>  
  <RegisteredOrganization />   
  <StartPanelOff>true</StartPanelOff>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <VisualEffects>  
  <FontSmoothing>ClearType</FontSmoothing>   
  </VisualEffects>  
  </component>  
  </settings>  
- <settings pass="specialize">  
- <component name="Microsoft-Windows-IE-ESC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <IEHardenAdmin>false</IEHardenAdmin>   
  <IEHardenUser>false</IEHardenUser>   
  </component>  
- <component name="Microsoft-Windows-UnattendedJoin" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
Enter credentials for a user account that has permissions to join a computer to the domain specified in the <JoinDomain> element. (Note: you must enter your password in plaintext here. This file will be deleted at the conclusion of Windows setup by SetupComplete.cmd in the C:\Windows\Setup\Scripts\ folder. For more information see the bottom of "How to Sysprep in Windows 2008" @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008)  
  -->   
- <Identification>  
- <Credentials>  
  <Domain>northamerica</Domain>   
  <Username>davidhamilton</Username>   
  <Password>******</Password>   
  </Credentials>  
  <JoinDomain>Redmond.corp.microsoft.com</JoinDomain>   
  </Identification>  
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
By specifying a value of "*" for <ComputerName>, Windows setup will generate a new computer name using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******  
  -->   
  <ComputerName>*</ComputerName>   
  <RegisteredOrganization />   
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.   
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <!--   
This setting will copy the profile of the original image to the renamed image when set to true   
  -->   
  <CopyProfile>true</CopyProfile>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  </component>  
  </settings>  
- <settings pass="generalize">  
- <component name="Microsoft-Windows-Security-Licensing-SLC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <SkipRearm>1</SkipRearm>   
  </component>  
- <component name="Microsoft-Windows-OutOfBoxExperience" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenInitialConfigurationTasksAtLogon>true</DoNotOpenInitialConfigurationTasksAtLogon>   
  </component>  
- <component name="Microsoft-Windows-ServerManager-SvrMgrNc" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenServerManagerAtLogon>true</DoNotOpenServerManagerAtLogon>   
  </component>  
  </settings>  
  <cpi:offlineImage cpi:source="catalog:e:/sources/install_windows longhorn serverenterprise.clg" xmlns:cpi="urn:schemas-microsoft-com:cpi" />   
  </unattend>  
- <!--   
When the virtual machine is started, Windows setup will:  
  
 - Assign the copy a random computer name: "OsloVPC-*****"  
 - Reset the local Administrators password to pass@word1  
 - Join the domain specified in the sysprep.xml file (under Microsoft-Windows-UnattendedJoin\Identification\JoinDomain)  
 - Add the groups/users specified under <DomainAccounts> to the local Administrators and the local Remote Desktop Users group.  
  
Known issues:  
  
 - Sysprep removes the Server Manager icon from the Quick Launch toolbar, investigating how to prevent this.  
 - To start SQL Server Management Studio, either connect to the new server name (OsloVPC-*******) or else connect to ".".  The "Server name:" drop-down box in SQL Server Management Studio is pre-populated with "PDC08-CSD" which will not work since the computer name has been changed by sysprep.  
 - There are some known issues associated with changing the computer name; renaming the computer after everything was installed was not a design, development or test requirement for this milestone.  
  -->  
```  
  
## <a name="comments"></a>注释  
 这些脚本不会修改 Microsoft Office SharePoint Server。 如果使用的 Windows SharePoint Services 适配器，您可能需要重新配置 Microsoft Office SharePoint Server，然后更新 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\ 下的 SharePointAdapterManagementGroup 密钥TPM。