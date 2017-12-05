---
title: "附录 a： 无提示安装 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94ded6b3-13ca-47e6-a038-254514f500e7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03568f86b8c3b609fed74a9faf7f6057614151c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="appendix-a-silent-installation"></a>附录 A：无提示安装
本主题列出了创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无提示安装的步骤。  
  
## <a name="create-a-silent-installation"></a>创建无提示安装  
  
1.  依次单击“开始”、“所有程序”、“附件”，然后单击“命令提示符”。  
  
2.  转到安装位置。 在命令提示符中，键入 `setup.exe /``<command name> <options>`，然后按 **ENTER**。 日志文件会显示安装状态。  
  
|命令名称|选项|说明|  
|------------------|------------|-----------------|  
|/HELP、/? 或 /H||提供帮助和快速参考。|  
|/QUIET||在安装期间隐藏 UI — 所有对话框、错误或要求用户进行输入的提示。 所有消息都记录到安装程序日志文件中。 **注意：**对于升级安装，不能指定“安静”标志，因为升级需要用户对所选的选项进行确认。|  
|/CABPATH|\<*CAB 文件位置*\>|指示可再发行的 CAB 文件的位置。|  
|/S|\<*配置 XML 文件*\>|无提示安装在指定配置文件中找到的功能。 **注意：**若要安装所有功能，请将配置 XML 文件的 `InstalledFeature` 参数指定为 ALL。|  
|/PASSIVE||执行被动安装。 安装程序只显示进度栏。|  
|/NORESTART||不显示重新启动提示，在安装结束时自动重新启动。|  
|/FORCERESTART||安装完成后，始终强制重新启动。|  
|/PROMPTRESTART||重新启动前提示用户。|  
|/X 或 /UNINSTALL||卸载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|  
|/L|\<日志文件\>[i] [w] [e] [a] [r] [u] [c] [m] [p] [v] [*]|将日志信息写入到位于指定路径的日志文件中。 始终采用详细 Windows Installer 日志记录，并追加到现有文件。<br /><br /> 以下标志指明要记录的信息：<br /><br /> i - 状态消息<br /><br /> w - 一般错误警告<br /><br /> e - 所有错误消息<br /><br /> a - 操作的启动<br /><br /> r - 特定于操作的记录<br /><br /> u - 用户请求<br /><br /> c - 初始用户界面参数<br /><br /> m - 内存不足<br /><br /> p - 终端属性<br /><br /> v – 详细输出<br /><br /> * - 全部|  
|/IGNOREDEPENDENCIES||跳过可下载必备项检查。|  
|/ INSTALLDIR \<*安装路径*\>|\<*程序文件文件夹\>*|指定产品安装位置的完整路径。|  
|/COMPANYNAME|\<*公司名称*\>|设置公司或组织名称。|  
|/USERNAME|\<*用户名*\>|设置用户名。|  
|/ADDLOCAL ALL||安装所有功能。 有关 ADDLOCAL 命令的详细信息，请参阅 [ADDLOCAL 命令的值列表](http://go.microsoft.com/fwlink/p/?LinkID=189319)。|  
|/REMOVE ALL||删除所有功能。|  
|/REPAIR ALL||修复所有功能。|  
|/CEIP||启用客户体验改善计划 (CEIP)|  
|/PRODUCT UDDI||安装 UDDI|  
|msiexec.exe /i  [MSIPATH] INSTALLDIR=[INSTALLDIRPATH] DATADIR=[DATADIRPATH] SQLSERVERMACHINENAME=[SQLSERVERNAME] OVERWRITERFIDSTORE=1 INSTALLLEVEL=5 /lvxp RfidServicesInstall.txt /q<br /><br /> 例如： msiexec.exe /i "\\\ABC\XYZ\RFID_x86\RfidServices.msi" INSTALLDIR=“C:\Program Files\Microsoft BizTalk RFID\” DATADIR=“C:\Program Files\Microsoft BizTalk RFID\” SQLSERVERMACHINENAME=(local) OVERWRITERFIDSTORE=1 INSTALLLEVEL=5 /lvxp RfidServicesInstall.txt /q||安装 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] RFID|  
  
 **补充说明**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持自动的电子软件分发，也称为无提示安装。 无提示安装将执行以下操作：  
  
    -   将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在具有配置的计算机上。  
  
    -   允许系统管理员在无需用户干预的情况下，在远程计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    -   用户无需监视安装和提供输入。  
  
-   若要创建无提示安装，请使用命令行选项来禁止所有交互操作。  
  
-   当你完成无提示安装时，命令窗口将不会显示任何消息。 可使用安装日志文件查看状态。  
  
