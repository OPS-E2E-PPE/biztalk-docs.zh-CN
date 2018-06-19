---
title: 如何在 Visual Studio 中设置部署属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2c6752e-c50d-4dd0-ac07-bf36ca10559c
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f448ec0569d64a3b3a14738bf08e68e083b80f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972987"
---
# <a name="how-to-set-deployment-properties-in-visual-studio"></a>如何在 Visual Studio 中设置部署属性
从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将解决方案部署到 BizTalk 应用程序之前，必须先设置项目属性。 如果 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的解决方案包含多个项目，必须为每个项目单独配置属性。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中所述的过程，必须用在本地文件系统上具有读/写权限的帐户进行登录。 本地计算机的管理员帐户拥有此权限。  
  
### <a name="to-enable-project-deployment-in-configuration-manager"></a>启用“配置管理器”中的项目部署  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]单击**生成**在主菜单中，然后单击**Configuration Manager**。  
  
2.  检查**部署**需要从打开的解决方案进行部署的每个项目的选项。  
  
### <a name="to-configure-project-properties"></a>若要配置项目属性  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器右键单击你想要配置属性，，然后单击某个的项目**属性**。  
  
2.  单击**部署**项目设计器中的选项卡。  
  
3.  下表中所述配置项目属性，然后单击**确定**。  
  
4.  对于解决方案中的每个项目，重复执行步骤 1、2 和 3。  
  
    |属性|值|解释|  
    |--------------|-----------|-----------------|  
    |应用程序名称|\<名称\>|用于将此项目中的程序集部署到的 BizTalk 应用程序的名称。 如果该应用程序已存在，则在你部署该项目时这些程序集将添加到该应用程序中。 如果该应用程序不存在，则将创建该应用程序。 如果此字段为空，则这些程序集将部署到当前组中的默认 BizTalk 应用程序中。 包含空格的名称必须括在双引号 (") 中。|  
    |配置数据库|\<BizTalk 管理数据库名称\>|用于组的 BizTalk 管理数据库的名称，默认情况下为 BizTalkMgmtDb。|  
    |Server|\<服务器名称\>|作为本地计算机上 BizTalk 管理数据库宿主的 SQL Server 实例的名称。 在单台计算机安装中，该名称通常是本地计算机的名称。 **注意：** 如果此 BizTalk 项目移动到另一台计算机时，你可能需要修改服务器属性，以反映新的计算机名称，然后你将能够部署程序集。|  
    |重新部署|True 或 False|如果将此项设置为 True（默认设置），你将能够在不更改版本号的情况下重新部署 BizTalk 程序集。|  
    |安装到全局程序集缓存|True 或 False|如果将此项设置为 True（默认设置），则可以在安装应用程序时将程序集安装到本地计算机上的全局程序集缓存 (GAC) 中。 只有当您计划将其他工具用于此安装（如 gacutil）时，才需要将此值设置为 False。|  
    |重新启动主机实例|True 或 False|如果将此项设置为 True，则可以在重新部署程序集时自动重新启动在本地计算机上运行的所有主机实例。 如果将此项设置为 False（默认设置），则必须在你重新部署某一程序集时手动重新启动这些主机实例。 **注意：** 如果要重新部署解决方案级别中的程序集，主机实例将重新启动一次每个项目具有此选项设置为 True。 这样可能导致多次重新启动。 如果计划在解决方案级重新部署，你可能希望针对解决方案中的一个项目将此属性设置 True，以避免多次主机实例重新启动。 此设置应针对将在解决方案中重新部署的最后一个项目进行。 此外，如果在你执行重新部署时，主机实例停止，它将不会被启动。|  
    |启用单元测试|True 或 False|指定是否启用项目的单元测试。|  
  
## <a name="see-also"></a>另请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)