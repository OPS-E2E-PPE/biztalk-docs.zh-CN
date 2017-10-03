---
title: "如何在 NLB 群集上配置到工作 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73bd5013cd2a09d240fa58b7cf5283c8d1903c69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a>如何配置要在 NLB 群集上使用的 BAM 门户
可以将 BAM 门户配置为在网络负载平衡 (NLB) 群集中使用。  
  
> [!IMPORTANT]
>  BAM 门户*仅*在 32 位模式下运行。 如果 IIS 安装在 64 位计算机上，请确认在 32 位模式下启用了 ASP.NET 2.0。 若要执行此操作，打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在“启用 32 位应用程序”中，选择 **True**。  
>   
>  有关其他 BAM 门户要求，请参阅[规划 BAM 门户](../core/planning-for-the-bam-portal.md)。  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a>准备在 NLB 群集上配置 BAM 门户  
  
1.  在第一台计算机上安装并配置门户。  
  
    > [!NOTE]
    >  只在第一台计算机上配置门户。 你可以选择在群集中的其他计算机上启用 BAM 门户，但只在第一台计算机上进行配置。  
  
2.  在所有要包括在 NLB 群集中的计算机上安装门户组件，然后将群集中的其他计算机加入到已配置门户的计算机的 BizTalk 组中。 必须启用 BizTalk 组并加入相应组。  
  
3.  选择为安装门户的计算机配置的 BizTalk 管理数据库。  
  
4.  创建 NLB 群集。 有关如何创建和管理网络负载平衡群集的详细信息，请参阅"创建和管理网络负载平衡群集"在[http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206)。  
  
    > [!NOTE]
    >  继续操作之前，应该确认 NLB 群集在 BizTalk Server 上下文以外工作正常。  
  
    > [!NOTE]
    >  若要设置基于硬件的 NLB，请参阅硬件提供商的文档。  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a>更新 BAM 配置以反映群集的位置  
  
1.  使用 BAM 管理实用程序获得当前 BAM 配置。 若要执行此操作，请单击**启动**，单击**运行**，和类型[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config-FileName:MyConfig.xml。  
  
2.  将本地主机名换为 NLB 群集的名称。 若要执行此操作，请单击**启动**，单击**运行**，和类型记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml。  
  
3.  仅对于基于硬件的 NLB，验证配置文件具有以下内容：  
  
    ```  
    <GlobalProperty Name="BAMVRoot">  
    http://<NLB IP Address>:portname/BAM</GlobalProperty>  
    ```  
  
    > [!NOTE]
    >  在更新基于硬件的 NLB 上的 BAM 配置时，不必执行步骤 4 和 5。  
  
4.  将以下行中的计算机名 (machinename) 改为群集名以指向 NLB 群集：  
  
    ```  
    <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
    </GlobalProperty>   
    ```  
  
5.  保存新配置。 若要执行此操作，请单击**启动**，单击**运行**，和类型[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm 更新-config-FileName:MyConfig.xml。  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a>编辑 BAM 门户 web.config 文件中的 BAMmanagementService 和 QueryService URL 使之改为指向 NLB 服务器名。 注意： 此过程不是基于硬件的 NLB 所需的。  
  
1.  打开 web.config 文件通过单击使用记事本**启动**、 单击**运行**，键入记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。  
  
2.  在以下两行中修改其中的计算机名 (machinename) 和端口名，使其指向群集名：  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
    ```  
  
3.  保存该文件。 若要执行此操作，请单击**文件**，然后单击**保存**记事本菜单栏上。  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a>配置群集中的其他计算机  
  
1.  将 web.config 文件复制到群集中每个其他计算机的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal 文件夹中。  
  
    > [!NOTE]
    >  在下面的示例步骤对所有引用**Program Files**文件夹将为**Program Files (x86)**的 64 位计算机。  
  
    > [!IMPORTANT]
    >  在以下步骤中，创建虚拟目录时，请进行查看以确保它们与 BizTalk Server 配置在第一台计算机上所创建的三个 BAM 虚拟目录的设置相同。 确认文件路径、ASP.NET 版本、目录权限和应用程序池。  使用与你设置第一台计算机时使用的相同的域服务帐户在要设置的计算机上运行 BAMAppPool。 确保 BAMAppPool 在所有计算机上运行。 你必须复制两个 web.config 文件。  
    >   
    >  除 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal 中的 web.config 文件之外，还必须将 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService 和 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService 中的 web.config 文件复制到此计算机的相同文件夹中。  
  
2.  仅对于基于硬件的 NLB，在以下两行中修改其中的计算机名 (machinename) 和端口名，使其指向群集名：  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
    ```  
  
3.  创建一个称为 BAMAppPool 的应用程序池。  
  
    > [!NOTE]
    >  虚拟目录的目录路径应为 %installationfolder%/bamportal、 %installationfolder%/bamportal/bammanagementservice，和 %installationfolder%/bamportal/bamqueryservice。  
  
4.  在默认网站下创建名为 BAM 的虚拟目录。  
  
5.  将 BAM 虚拟目录的应用程序池更改为 BAMAppPool。  
  
    > [!NOTE]
    >  虚拟目录的目录路径应为 %InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService 和 %InstallationFolder%/BamPortal/BAMQueryService。  
  
6.  在 BAM 下创建名为 BAMManagementService 的虚拟目录。  
  
7.  将 BAMManagementService 的应用程序池改为 BAMAppPool。  
  
    > [!NOTE]
    >  虚拟目录的目录路径应为 %installationfolder%/bamportal、 %installationfolder%/bamportal/bammanagementservice，和 %installationfolder%/bamportal/bamqueryservice。  
  
8.  在 BAM 下创建名为 BAMQueryService 的虚拟目录。  
  
9. 将 BAMQueryService 的应用程序池改为 BAMAppPool。  
  
10. 在虚拟目录属性 ASP NET 选项卡上，使用 INETMGR 更改 BAM 的版本，使用 BAMMANAGEMENTSERVICE 和 BAMQUERYSERVICE 将应用程序的版本设置为 .NET Framework 4。  
  
11. 运行 aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password。  此处指定的帐户是 BAM 管理 Web Services 用户帐户。  
  
    > [!CAUTION]
    >  BAM 门户*仅*在 32 位模式下运行。 如果 IIS 安装在 64 位计算机上，必须在 32 位模式下启用 ASP.NET 2.0。 若要执行此操作，打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在“启用 32 位应用程序”中，选择 **True**。  
    >   
    >  [规划 BAM 门户](../core/planning-for-the-bam-portal.md)列出了其他要求。  
  
12. 运行 SubInACL，为 Web Services 上的应用程序池用户设置读 ACL。SubInACL 是一个命令行工具，使用它可以使管理员获取有关文件、注册表项和服务的安全信息，并将此信息从一个用户传递到另一个用户，从本地传递到全局，从一个组传递到另一个组，以及从一个域传递到另一个域。  
  
13. 下载从 SubInAcl [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990)。  
  
14. 打开命令提示符。 若要执行此操作，请单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
15. 在命令提示符下键入以下内容： subinacl.exe /subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""/ 授予 = 网络服务 = R"  
  
    > [!NOTE]
    >  此命令的用途是授予 SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity 注册表项 BAM 应用程序池用户读取访问权限。 由于默认情况下，IIS 对应用程序池使用网络服务，因此本示例使用网络服务。 如果你不想使用默认的 IIS 设置，则应该替换你的部署所使用的应用程序池用户。  
  
16. 在命令提示符下键入以下内容： subinacl.exe /keyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0""/ 授予 =\<BAM WebService 帐户 >"  
  
    > [!NOTE]
    >  此命令的目的是向 BAM 管理 Web Services 用户帐户授予读取 SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity 注册表项的权限。  
  
17. 验证应用程序池用于运行 BAMManagement Web 服务的身份具有对 ASPNET_SETREG 键的读访问权限。  
  
18. 使用“计算机管理”管理员工具向 IIS Worker Process 组 (IIS_WPG) 和 SharePoint services 组 (STS_WPG) 添加 BAM 管理 Web Services 用户和 BAM 应用程序池帐户。  
  
19. 在应用程序池和 Web 服务用户的临时 ASP.NET 文件夹上设置权限： c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ v2.0。\<min 版本号 > \Temporary ASP.NET 文件"/T /E /G \<BAM WebService 帐户 >: F  
  
    > [!NOTE]
    >  你要同时向 BAM 管理 Web Services 用户帐户和 BAM 应用程序池用户帐户授予权限。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 门户](../core/managing-the-bam-portal.md)