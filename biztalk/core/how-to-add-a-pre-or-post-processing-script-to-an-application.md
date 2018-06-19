---
title: 如何将一个预或后续处理脚本添加到应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding scripts
- managing [scripts], applications
- applications, scripts
- managing [scripts], adding
- scripts, adding to applications
- scripts
ms.assetid: 729cb236-b9cf-468a-8b98-a24d86e60d3c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0646bc9e896e7b4e4d9264efba7c9bb5f0eb66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248445"
---
# <a name="how-to-add-a-pre--or-post-processing-script-to-an-application"></a>如何向应用程序添加预处理脚本和后处理脚本
本主题描述如何使用 BizTalk Server 管理控制台或命令行向应用程序添加预处理脚本或后处理脚本。 在您将某一脚本添加到应用程序时，该脚本包括在应用程序的 .msi 文件中，并且在导入、安装或卸载该应用程序时运行。  
  
 添加脚本时，您必须指定它是预处理脚本（在应用程序导入或安装开始前运行）还是后处理脚本（在应用程序导入或安装完成运行）。 前期和后期处理脚本还在卸载时，到在安装运行相反的顺序运行： 预处理脚本运行卸载后并在卸载之前运行的后续处理脚本。  
  
 您也可以从应用程序中删除脚本。 有关说明，请参阅[如何从应用程序删除预或后续处理脚本](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-script-to-an-application"></a>向应用程序添加脚本  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  依次展开 BizTalk 组和“应用程序”，然后右键单击要向其添加脚本的应用程序的文件夹。  
  
3.  指向**添加**，并执行下列操作之一：  
  
    -   单击**预处理脚本**如果想要在应用程序导入前运行的脚本或者开始安装或卸载后。  
  
    -   单击**后处理脚本**如果你想要运行应用程序导入或之后安装，或者在卸载之前的脚本。  
  
4.  单击**添加**并浏览到要添加的脚本文件。  
  
5.  选择脚本文件，然后单击**打开**。  
  
6.  如果你想要覆盖已存在应用程序，选择中的脚本文件**覆盖所有**复选框。 该脚本文件必须与所添加的、要覆盖的文件同名。 否则，将添加新的脚本，现有脚本仍将保留在应用程序中且没有任何改变。  
  
7.  单击**文件类型**下拉列表，然后单击文件类型 – 请**System.BizTalk:PreprocessingScript**或**System.BizTalk:PostprocessingScript**。  
  
8.  如有必要，在**目标位置**类型希望该脚本的路径文件安装应用程序时，要复制，然后单击**确定**。 如果选择默认路径，则会将脚本安装到应用程序安装文件夹 (%BTAD_InstallDir%) 中。  
  
> [!NOTE]
>  如果未提供此路径，则在安装时该脚本将不会复制到本地文件系统。 如果在卸载应用程序时此脚本应运行，则确保提供该路径；否则，此脚本将不会在本地文件系统中存在，因此在卸载期间将无法运行。  
  
 该脚本将添加到应用程序中，并且显示在应用程序的“资源”文件夹中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:PreProcessingScript**&#124;**System.BizTalk:PostProcessingScript** [**/覆盖**] **/source:***值*[**/Destination:** *值*] [**/Server:***值*] [**/数据库：***值*] [**/Property:Args ="***自变量列表***"**]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:PreProcessingScript / 覆盖 /Source:"C:\Source Scripts\MyScript.vbs"/Destination:"C:\New Scripts\MyScript.vbs"/Server:MyDatabaseServer /Database:BizTalkMgmtDb/Property:Args ="argument1 argument2"**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|脚本要添加到的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:PreProcessingScript**或**System.BizTalk:PostProcessingScript**，具体取决于要添加脚本的类型。 使用**System.BizTalk:PreProcessingScript**如果你想要运行应用程序导入或安装之前或之后卸载的脚本。 使用**System.BizTalk:PostProcessingScript**如果你想要运行应用程序导入或之后安装，或者在卸载之前的脚本。|  
    |**/ 覆盖**|更新现有脚本。 如果未指定，且应用程序中已经存在与要添加的脚本文件同名的脚本文件，则添加操作将失败。|  
    |**/ 源**|脚本文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/ 目标**|从 MSI 文件安装应用程序时，脚本文件要复制到的位置的完整路径。 如果未提供，不复制文件到本地文件系统在安装过程。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
    |**/Property:Args =**|零或更多参数。 此处提供的参数将在调用脚本时传递到该脚本中。|  
  
## <a name="see-also"></a>另请参阅  
 [管理前期和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)   
 [AddResource 命令： 预处理脚本](../core/addresource-command-preprocessing-script.md)   
 [AddResource 命令： 后处理脚本](../core/addresource-command-postprocessing-script.md)