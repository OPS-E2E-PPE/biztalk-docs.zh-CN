---
title: 如何将绑定导入 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30cd7c587f09911b1ce3e16c21aae265a0a94ea8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385006"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>如何将绑定导入 BizTalk 应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行来绑定导入到 BizTalk 应用程序从.xml 文件。 您还可以导入绑定到 BizTalk 组，如中所述[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。  
  
 您可以导入已从程序集、 应用程序或组中导出的绑定。 如果导入组绑定，仅具有相同名称的应用程序的绑定应用到应用程序在其中导入绑定。 您还可以从具有不同名称的应用程序导入绑定。 有关导出绑定的说明，请参阅[导出绑定](../core/exporting-bindings6.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>绑定导入到 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开应用程序。  
  
3. 右键单击您要向其中导入绑定，指向应用的程序**导入**，然后单击**绑定**。  
  
4. 单击绑定文件，然后单击**打开**。  
  
    绑定文件中的项目将写入到应用程序。 它们显示在应用程序的相应文件夹中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ImportBindings /Source:** *value* [**/ApplicationName:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如，以下命令将绑定到默认 BizTalk 组中名为 MyApplication 的应用程序导入。  
  
    **BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/Source**|要导入，其中包括文件名的绑定文件的完整路径。 包含空格的路径必须括在引号 （"）。|  
   |**/ApplicationName**|在其中绑定是要导入 BizTalk 应用程序的名称。 该应用程序必须存在，或导入操作将失败。 如果未指定此参数，则使用默认 BizTalk 应用程序。 包含空格的应用程序名必须括在引号 （"）。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings 命令](../core/importbindings-command.md)