---
title: Sysprep BizTalk Server VHD （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: cc6ec29ece503f324758cdc08a6ff1351c066af4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007766"
---
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a><span data-ttu-id="1f811-102">Sysprep BizTalk Server VHD (BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1f811-102">Sysprep a BizTalk Server VHD (BizTalk Server Sample)</span></span>
<span data-ttu-id="1f811-103">Sysprep 为安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的虚拟机创建快照，以便在其他虚拟机上进行快速部署。</span><span class="sxs-lookup"><span data-stu-id="1f811-103">Sysprep creates a snapshot of a virtual machine with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed for quick deployment on other virtual machines.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f811-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="1f811-104">Prerequisites</span></span>  
 <span data-ttu-id="1f811-105">在使用之前 Sysprep，你应具有与 HYPER-V 使用虚拟机的一些知识。</span><span class="sxs-lookup"><span data-stu-id="1f811-105">Before using Sysprep, you should have some knowledge of using virtual machines with Hyper-V.</span></span> <span data-ttu-id="1f811-106">你还应该具有 BizTalk Server 和所有其必备组件的干净的典型安装的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="1f811-106">You should also have a virtual machine with a clean, typical installation of BizTalk Server and all of its prerequisites.</span></span>  
  
 <span data-ttu-id="1f811-107">Sysprep 将在 Windows Server 2008 和 Windows Vista SP1 上运行。</span><span class="sxs-lookup"><span data-stu-id="1f811-107">Sysprep will run on Windows Server 2008 and Windows Vista with SP1.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1f811-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="1f811-108">What This Sample Does</span></span>  
 <span data-ttu-id="1f811-109">Sysprep 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装（包括操作系统和所有前提条件）创建 VHD，以便在其他虚拟机上进行快速部署。</span><span class="sxs-lookup"><span data-stu-id="1f811-109">Sysprep creates a VHD of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation (including the operating system and all prerequisites) for quick deployment on other virtual machines.</span></span> <span data-ttu-id="1f811-110">使用 Sysprep 创建的映像将选择一个新的计算机名称，以便在首次启动时即可加入域。</span><span class="sxs-lookup"><span data-stu-id="1f811-110">An image created using Sysprep will choose a new computer name in order to join the domain the first time it starts.</span></span> <span data-ttu-id="1f811-111">若要使 BizTalk Server 正常运行，需要更新存储在注册表和数据库中的计算机名称的各种实例。</span><span class="sxs-lookup"><span data-stu-id="1f811-111">To get BizTalk Server running properly, it is necessary to update various instances of the computer name that are stored in the registry and databases.</span></span>  
  
 <span data-ttu-id="1f811-112">此文档假设将 BizTalk Server 配置为在单个计算机上运行，并演示如何使用新名称更新计算机名称的其他实例。</span><span class="sxs-lookup"><span data-stu-id="1f811-112">This document assumes that BizTalk Server is configured to run on a single computer, and shows how to update other instances of the computer name with the new name.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1f811-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="1f811-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="1f811-114">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="1f811-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="1f811-115">\<*示例路径*\>\Admin\Sysprep\\</span><span class="sxs-lookup"><span data-stu-id="1f811-115">\<*Samples Path*\>\Admin\Sysprep\\</span></span>  
  
 <span data-ttu-id="1f811-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="1f811-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f811-117">下表中的 .vbs 和 .cmd 文件将在 Sysprep 应答文件（Sysprep.xml 和 SetupCompletecmd.txt）中自动运行，在此处列出仅供参考。</span><span class="sxs-lookup"><span data-stu-id="1f811-117">The .vbs and .cmd files in the table below are all automated in the Sysprep answer files (Sysprep.xml and SetupCompletecmd.txt), and are listed here for reference only.</span></span> <span data-ttu-id="1f811-118">如果你需要手动运行这些脚本，请按照表中出现的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="1f811-118">If you do need to run these scripts manually, run them in the order that they appear in the table.</span></span>  
  
|<span data-ttu-id="1f811-119">文件</span><span class="sxs-lookup"><span data-stu-id="1f811-119">File</span></span>|<span data-ttu-id="1f811-120">Description</span><span class="sxs-lookup"><span data-stu-id="1f811-120">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1f811-121">Sysprep.xml</span><span class="sxs-lookup"><span data-stu-id="1f811-121">Sysprep.xml</span></span>|<span data-ttu-id="1f811-122">Answer file</span><span class="sxs-lookup"><span data-stu-id="1f811-122">Answer file</span></span>|  
|<span data-ttu-id="1f811-123">SetupCompletecmd.txt</span><span class="sxs-lookup"><span data-stu-id="1f811-123">SetupCompletecmd.txt</span></span>|<span data-ttu-id="1f811-124">Answer file</span><span class="sxs-lookup"><span data-stu-id="1f811-124">Answer file</span></span>|  
|<span data-ttu-id="1f811-125">ReplaceMachineName.vbs</span><span class="sxs-lookup"><span data-stu-id="1f811-125">ReplaceMachineName.vbs</span></span>|<span data-ttu-id="1f811-126">用途： 打开文件和给定字符串的所有实例都替换为当前计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-126">Purpose: Opens a file and replaces all instances of a given string with the current computer name.</span></span> <span data-ttu-id="1f811-127">这对于准备其他脚本和 xml 文件及更新 bm.exe.config 非常有用。</span><span class="sxs-lookup"><span data-stu-id="1f811-127">Useful to prepare the other script and xml files, and to update bm.exe.config.</span></span><br /><br /> <span data-ttu-id="1f811-128">用法： ReplaceMachineName.vbs\<文件以打开\>\<要替换的字符串\></span><span class="sxs-lookup"><span data-stu-id="1f811-128">Usage: ReplaceMachineName.vbs \<file to open\> \<string to replace\></span></span>|  
|<span data-ttu-id="1f811-129">UpdateRegistry.vbs</span><span class="sxs-lookup"><span data-stu-id="1f811-129">UpdateRegistry.vbs</span></span>|<span data-ttu-id="1f811-130">用途： 更新 BizTalk 注册表设置中存储的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-130">Purpose: Updates the computer name stored in the BizTalk registry settings.</span></span><br /><br /> <span data-ttu-id="1f811-131">用法： UpdateRegistry.vbs \<UpdateInfo.xml\>。</span><span class="sxs-lookup"><span data-stu-id="1f811-131">Usage: UpdateRegistry.vbs \<UpdateInfo.xml\>.</span></span> <span data-ttu-id="1f811-132">请确保替换此 xml 文件中的所有 $(OLDCOMPUTERNAME) 和 $(NEWCOMPUTERNAME) 实例。</span><span class="sxs-lookup"><span data-stu-id="1f811-132">Make sure to replace all instances of $(OLDCOMPUTERNAME) and $(NEWCOMPUTERNAME) in this xml file.</span></span>|  
|<span data-ttu-id="1f811-133">UpdateDatabase.vbs</span><span class="sxs-lookup"><span data-stu-id="1f811-133">UpdateDatabase.vbs</span></span>|<span data-ttu-id="1f811-134">用途： 更新 BizTalk 管理数据库中存储的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-134">Purpose: Updates the computer name stored in the BizTalk Management databases.</span></span><br /><br /> <span data-ttu-id="1f811-135">用法： UpdateDatabase.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="1f811-135">Usage: UpdateDatabase.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="1f811-136">UpdateBAMDb.vbs</span><span class="sxs-lookup"><span data-stu-id="1f811-136">UpdateBAMDb.vbs</span></span>|<span data-ttu-id="1f811-137">用途： 更新 BAM 数据库中存储的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-137">Purpose: Updates the computer name stored in the BAM databases.</span></span><br /><br /> <span data-ttu-id="1f811-138">用法： UpdateBamDb.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="1f811-138">Usage: UpdateBamDb.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="1f811-139">UpdateSSO.cmd</span><span class="sxs-lookup"><span data-stu-id="1f811-139">UpdateSSO.cmd</span></span>|<span data-ttu-id="1f811-140">用途： 重新配置企业单一登录 (SSO) 密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="1f811-140">Purpose: Reconfigures the Enterprise Single Sign-on (SSO) secret server.</span></span><br /><br /> <span data-ttu-id="1f811-141">用法： sso.cmd \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="1f811-141">Usage: sso.cmd \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="1f811-142">UpdateSqlServerAndInstanceName.cmd</span><span class="sxs-lookup"><span data-stu-id="1f811-142">UpdateSqlServerAndInstanceName.cmd</span></span>|<span data-ttu-id="1f811-143">用途： 重新配置 SQL 和 SQL Express，重新启动一系列的从属服务中注册 BAMAlerts。</span><span class="sxs-lookup"><span data-stu-id="1f811-143">Purpose: Reconfigures SQL and SQL Express, restarts a series of dependent services, and reregisters BAMAlerts.</span></span><br /><br /> <span data-ttu-id="1f811-144">用法： 编辑脚本和 $(NEWCOMPUTERNAME) 的所有实例都替换和更新的 serviceusername 和 servicepassword BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="1f811-144">Usage: Edit the script and replace all instances of $(NEWCOMPUTERNAME), and update the serviceusername and servicepassword for BAM Alerts.</span></span> <span data-ttu-id="1f811-145">然后运行 UpdateSqlServerAndInstanceName.cmd，作为第一个参数传递旧计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-145">Then run UpdateSqlServerAndInstanceName.cmd passing the old computer name as the first argument.</span></span>|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a><span data-ttu-id="1f811-146">创建应答文件和运行 Sysprep</span><span class="sxs-lookup"><span data-stu-id="1f811-146">Creating the Answer Files and Running Sysprep</span></span>  
  
#### <a name="to-create-the-answer-files"></a><span data-ttu-id="1f811-147">创建应答文件</span><span class="sxs-lookup"><span data-stu-id="1f811-147">To create the answer files</span></span>  
  
1.  <span data-ttu-id="1f811-148">安装和配置的虚拟机上的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1f811-148">Install and configure BizTalk Server on a virtual machine.</span></span> <span data-ttu-id="1f811-149">确保使用默认安装和配置选项，因为 Sysprep 不支持自定义安装。</span><span class="sxs-lookup"><span data-stu-id="1f811-149">Be sure to use default installation and configuration options, since Sysprep does not support customized installation.</span></span>  
  
2.  <span data-ttu-id="1f811-150">将包括的“scripts”文件夹中的内容复制到虚拟机上的 C:\Scripts。</span><span class="sxs-lookup"><span data-stu-id="1f811-150">Copy the contents of the included “scripts” folder to C:\Scripts on the virtual machine.</span></span>  
  
3.  <span data-ttu-id="1f811-151">通过修改 Sysprep.xml 中的以下行中准备的 sysprep 应答文件。</span><span class="sxs-lookup"><span data-stu-id="1f811-151">Prepare a sysprep answer file by modifying the following lines in Sysprep.xml.</span></span> <span data-ttu-id="1f811-152">(注意： 这些行均未标有"！"</span><span class="sxs-lookup"><span data-stu-id="1f811-152">(Note: These lines are marked with a “!”</span></span> <span data-ttu-id="1f811-153">之前它们。）可以将这些操作用作模板，或进行你自己，并通过复制\<FirstLogonCommands\>部分。</span><span class="sxs-lookup"><span data-stu-id="1f811-153">before them.) You can use these as a template, or make your own and copy over the \<FirstLogonCommands\> section.</span></span>  
  
    -   <span data-ttu-id="1f811-154">$(OLDCOMPUTERNAME) 替换为虚拟机的当前计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1f811-154">$(OLDCOMPUTERNAME) Replace with the current computer name of the virtual machine.</span></span>  
  
    -   <span data-ttu-id="1f811-155">用户帐户</span><span class="sxs-lookup"><span data-stu-id="1f811-155">User accounts</span></span>  
  
    -   <span data-ttu-id="1f811-156">密码</span><span class="sxs-lookup"><span data-stu-id="1f811-156">Passwords</span></span>  
  
    -   <span data-ttu-id="1f811-157">还应更新 UpdateSqlServerAndInstance.cmd 和你 Sysprep.xml 中的任何公司详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f811-157">Any company details should also be updated in UpdateSqlServerAndInstance.cmd and your Sysprep.xml.</span></span>  
  
     <span data-ttu-id="1f811-158">或者，你可以从头开始创建 Sysprep 应答文件使用[自动安装工具包 (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) Windows Server 2008 上。</span><span class="sxs-lookup"><span data-stu-id="1f811-158">Alternatively, you can create a Sysprep answer file from scratch using use the [Automated Installation Kit (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) on Windows Server 2008.</span></span> <span data-ttu-id="1f811-159">确保你\<FirstLogonCommands\>部分与示例相匹配，因此 BizTalk 脚本将在首次启动上运行。</span><span class="sxs-lookup"><span data-stu-id="1f811-159">Ensure that your \<FirstLogonCommands\> section matches the samples so the BizTalk scripts will run on the first boot.</span></span>  
  
#### <a name="to-run-sysprep"></a><span data-ttu-id="1f811-160">运行 Sysprep</span><span class="sxs-lookup"><span data-stu-id="1f811-160">To run Sysprep</span></span>  
  
1.  <span data-ttu-id="1f811-161">打开命令提示符，然后运行 Sysprep。</span><span class="sxs-lookup"><span data-stu-id="1f811-161">Open a command prompt and run Sysprep.</span></span> <span data-ttu-id="1f811-162">该命令将如下所示：</span><span class="sxs-lookup"><span data-stu-id="1f811-162">The command will look something like:</span></span>  
  
    ```  
    C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
    ```  
  
2.  <span data-ttu-id="1f811-163">Sysprep 要运行约半小时。</span><span class="sxs-lookup"><span data-stu-id="1f811-163">Sysprep takes about half an hour to run.</span></span> <span data-ttu-id="1f811-164">完成后，它将自动关闭虚拟机。</span><span class="sxs-lookup"><span data-stu-id="1f811-164">When it is complete, it will automatically shut down the virtual machine.</span></span>  
  
3.  <span data-ttu-id="1f811-165">关闭虚拟机后，合并所有快照，并将你的 VHD 文件复制到安全位置。</span><span class="sxs-lookup"><span data-stu-id="1f811-165">After the virtual machine has been shut down, merge any snapshots, and copy your VHD file to a safe location.</span></span>  
  
4.  <span data-ttu-id="1f811-166">现在 VHD 已经准备就绪，可部署到其他虚拟机上，包含操作系统、BizTalk Server 和所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="1f811-166">Your VHD is now ready to be deployed on other virtual machines, complete with operating system, BizTalk Server, and all prerequisites.</span></span>  
  
 <span data-ttu-id="1f811-167">**SetupCompletecmd.txt**</span><span class="sxs-lookup"><span data-stu-id="1f811-167">**SetupCompletecmd.txt**</span></span>  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 <span data-ttu-id="1f811-168">**Sysprep.xml**</span><span class="sxs-lookup"><span data-stu-id="1f811-168">**Sysprep.xml**</span></span>  
  
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
  
## <a name="comments"></a><span data-ttu-id="1f811-169">注释</span><span class="sxs-lookup"><span data-stu-id="1f811-169">Comments</span></span>  
 <span data-ttu-id="1f811-170">这些脚本不会修改 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="1f811-170">These scripts do not modify Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="1f811-171">如果你使用的是 Windows SharePoint Services 适配器，将可能需要重新配置 Microsoft Office SharePoint Server，然后更新 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM 下的 SharePointAdapterManagementGroup 密钥。</span><span class="sxs-lookup"><span data-stu-id="1f811-171">If you are using the Windows SharePoint Services adapter, you will probably need to reconfigure Microsoft Office SharePoint Server and then update the SharePointAdapterManagementGroup key under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM.</span></span>