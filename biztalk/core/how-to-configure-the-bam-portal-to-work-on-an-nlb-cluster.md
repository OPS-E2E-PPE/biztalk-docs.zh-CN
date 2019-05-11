---
title: 如何在 NLB 群集上配置 BAM 门户，转到工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0273433cf06fd0c455d6ed5a0be05198a149b4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386174"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a>如何在 NLB 群集上配置 BAM 门户，转到工作
可以配置 BAM 门户，以便在网络负载平衡 (NLB) 群集中。  
  
> [!IMPORTANT]
>  BAM 门户*仅*在 32 位模式下运行。 如果在 64 位计算机上安装 IIS，然后确认在 32 位模式下启用 ASP.NET 2.0。 若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在中**启用 32 位应用程序**，选择**True**。  
>   
>  有关其他 BAM 门户要求，请参阅[规划 BAM 门户](../core/planning-for-the-bam-portal.md)。  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a>若要准备将 NLB 群集上配置 BAM 门户  
  
1.  安装和配置第一台计算机上的门户。  
  
    > [!NOTE]
    >  只需在第一台计算机上配置门户。 必须启用在群集中的其他计算机的其他 BAM 门户的选项，但仅在第一台计算机上进行的配置。  
  
2.  要包含在 NLB 群集中的所有计算机上安装门户组件，然后将其他计算机加入到在其配置门户的计算机的 BizTalk 组在群集中。 必须启用 BizTalk 组并加入相应组。  
  
3.  选择在其上安装在门户的计算机配置的 BizTalk 管理数据库。  
  
4.  创建 NLB 群集。 有关如何创建和管理网络负载平衡群集的详细信息，请参阅"创建和管理网络负载平衡群集"处[ http://go.microsoft.com/fwlink/?LinkId=56206 ](http://go.microsoft.com/fwlink/?LinkId=56206)。  
  
    > [!NOTE]
    >  您应确认该 NLB 群集正常工作的 BizTalk Server 上下文外部然后再继续。  
  
    > [!NOTE]
    >  若要设置基于硬件的 NLB，请参阅硬件提供商的文档。  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a>若要更新 BAM 配置以反映群集的位置  
  
1. 使用 BAM 管理实用程序来获取当前 BAM 配置。 若要执行此操作，请单击**启动**，单击**运行**，然后键入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config-filename: Myconfig.xml。  
  
2. 将本地主机名替换为 NLB 群集的名称。 若要执行此操作，请单击**启动**，单击**运行**，然后键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml。  
  
3. 对于基于硬件的 NLB，验证具有以下配置文件：  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  更新基于硬件的 NLB 上的 BAM 配置时，则不需要步骤 4 和 5。  
  
4. 修改以下行以指向 NLB 群集的计算机名 (machinename) 替换为群集名称：  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. 保存新配置。 若要执行此操作，请单击**启动**，单击**运行**，然后键入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm 更新-config-filename: Myconfig.xml。  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a>若要编辑 BAM 门户 web.config 文件中的 BAMmanagementService 和 QueryService Url 以指向 NLB 服务器名。 注意：此过程不是必需的基于硬件的 NLB。  
  
1. 打开 web.config 文件，使用记事本**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2. 修改计算机名 (machinename) 和以下两个行，以指向群集的名称的名称中的端口名称：  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. 保存该文件。 若要执行此操作，请单击**文件**，然后单击**保存**记事本的菜单栏上。  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a>若要在群集中配置其他每台计算机  
  
1. 将 web.config 文件复制到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal 文件夹在群集中每台计算机上的。  
  
   > [!NOTE]
   >  在以下步骤对所有引用**Program Files**文件夹将为**Program Files (x86)** 对于 64 位计算机。  
   > 
   > [!IMPORTANT]
   >  在以下步骤中，当创建虚拟目录，检查以确保它们具有的设置创建的第一台计算机上的 BizTalk Server 配置的三个 BAM 虚拟目录相同。 确认文件路径、 ASP.NET 版本、 目录权限和应用程序池。  使用相同的域服务帐户所用设置第一台计算机时你要设置的计算机上运行 BAMAppPool。 请确保所有计算机上运行 BAMAppPool。 有两个 web.config 文件，则必须将复制。  
   > 
   >  Web.config 文件除了[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal，您必须将复制的 web.config 文件中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService 和[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService 到此计算机上的相同文件夹。  
  
2. 对于基于硬件的 NLB 仅，修改计算机名 (machinename) 和以下两个行，以指向群集的名称的名称中的端口名称：  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. 创建名为 BAMAppPool 的应用程序池。  
  
   > [!NOTE]
   >  虚拟目录的目录路径应为 %installationfolder%/bamportal、 InstallationFolder%/BamPortal/BAMManagementService，%和 %installationfolder%InstallationFolder%/BamPortal/BAMQueryService。  
  
4. 创建名为 BAM 在默认网站下的虚拟目录。  
  
5. 将 BAM 虚拟目录的应用程序池更改为 BAMAppPool。  
  
   > [!NOTE]
   >  虚拟目录的目录路径应为 %installationfolder%/bamportal %InstallationFolder%/BamPortal/BAMManagementService 和 %installationfolder%InstallationFolder%/BamPortal/BAMQueryService。  
  
6. 创建一个名为 BAMManagementService 在 BAM 下的虚拟目录。  
  
7. 将 BAMManagementService 的应用程序池更改为 BAMAppPool。  
  
   > [!NOTE]
   >  虚拟目录的目录路径应为 %installationfolder%/bamportal、 InstallationFolder%/BamPortal/BAMManagementService，%和 %installationfolder%InstallationFolder%/BamPortal/BAMQueryService。  
  
8. 创建一个名为 BAMQueryService 在 BAM 下的虚拟目录。  
  
9. 将 BAMQueryService 的应用程序池更改为 BAMAppPool。  
  
10. 使用位于虚拟目录属性 ASP NET 选项卡，INETMGR 更改 BAM、 BAMMANAGEMENTSERVICE 和 BAMQUERYSERVICE 设置为.NET Framework 4 的应用程序的版本的版本为。  
  
11. Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.  下面是 BAM 管理 Web 服务用户帐户指定的帐户。  
  
    > [!CAUTION]
    >  BAM 门户*仅*在 32 位模式下运行。 如果在 64 位计算机上安装 IIS，则必须在 32 位模式下启用 ASP.NET 2.0。 若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在中**启用 32 位应用程序**，选择**True**。  
    >   
    >  [规划 BAM 门户](../core/planning-for-the-bam-portal.md)列出了其他要求。  
  
12. 设置读 Acl 上 web 服务的应用程序池用户，通过运行 SubInACL，，管理员可以获取有关文件、 注册表项和服务，安全信息，并将此信息从本地传输用户的一个命令行工具或到组，并从域的域全局组。  
  
13. 下载从 SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990 ](http://go.microsoft.com/fwlink/?LinkId=61990)。  
  
14. 打开命令提示符。 若要执行此操作，请单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
15. 在命令提示符下键入以下内容： subinacl.exe /subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""/ 授予 = 网络服务 = R"  
  
    > [!NOTE]
    >  此命令的目的是授予 BAM 应用程序池用户读取访问权限 SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity 注册表项。 该示例使用网络服务，因为它是为应用程序池使用 IIS 的默认值。 如果不使用默认的 IIS 设置，则应该替换你的部署使用的应用程序池用户。  
  
16. 在命令提示符下键入以下内容： subinacl.exe /keyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0""/ 授予 =\<WebService 帐户\>"  
  
    > [!NOTE]
    >  此命令的目的是 BAM 管理 Web Service 用户向帐户授予读取 SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity 注册表项。  
  
17. 验证运行 BAMManagement Web 服务的应用程序池的标识具有对 ASPNET_SETREG 键读取访问。  
  
18. 使用计算机管理管理员工具向 IIS Worker Process 组 (IIS_WPG) 和 SharePoint services 组 (STS_WPG) 添加 BAM 管理 Web 服务用户和 BAM 应用程序池用户帐户。  
  
19. 为应用程序池和 Web 服务用户的临时 ASP.NET 文件夹上设置权限： c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ v2.0。\<最小版本号\>\Temporary ASP.NET Files"/T /E /G \<WebService 帐户\>: F  
  
    > [!NOTE]
    >  授予对 BAM 管理 Web 服务用户帐户和 BAM 应用程序池用户帐户的访问。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 门户](../core/managing-the-bam-portal.md)