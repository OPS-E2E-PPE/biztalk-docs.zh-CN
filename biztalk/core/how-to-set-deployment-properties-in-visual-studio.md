---
title: 如何在 Visual Studio 中设置部署属性 |Microsoft Docs
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
ms.openlocfilehash: be4adfcb8061b296fe8765b0cd910f92bc1db266
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383941"
---
# <a name="how-to-set-deployment-properties-in-visual-studio"></a>如何在 Visual Studio 中设置部署属性
您可以从部署解决方案之前[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序，您必须首先设置项目属性。 如果解决方案中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]包含多个项目，必须单独配置每个项目的属性。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须在本地文件系统上具有读/写权限的帐户登录。 在本地计算机上的管理员帐户拥有此权限。  
  
### <a name="to-enable-project-deployment-in-configuration-manager"></a>若要启用 Configuration Manager 中的项目部署  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]单击**构建**在主菜单上，然后单击**Configuration Manager**。  
  
2. 检查**部署**需要从打开的解决方案部署的每个项目的选项。  
  
### <a name="to-configure-project-properties"></a>若要配置项目属性  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器中右键单击您要为其配置属性，然后单击某个的项目**属性**。  
  
2. 单击**部署**项目设计器中的选项卡。  
  
3. 下表中所述配置项目属性，然后单击**确定**。  
  
4. 为解决方案中每个项目重复步骤 1、 2 和 3。  
  
   |属性|ReplTest1|解释|  
   |--------------|-----------|-----------------|  
   |应用程序名称|\<名称\>|要将此项目中的程序集部署到 BizTalk 应用程序的名称。 如果应用程序已存在，这些程序集在部署项目将添加到它。 如果应用程序不存在，将创建应用程序。 如果此字段为空，则程序集将部署到当前组中的默认 BizTalk 应用程序。 包含空格的名称必须用双引号引起来 （'） 括起来。|  
   |配置数据库|\<BizTalk 管理数据库名称\>|对于组，默认情况下 BizTalkMgmtDb BizTalk 管理数据库的名称。|  
   |“服务器”|\<服务器名称\>|承载在本地计算机上的 BizTalk 管理数据库的 SQL Server 实例的名称。 在单计算机安装中，这通常是本地计算机的名称。 **注意：** 如果将此 BizTalk 项目移到另一台计算机，你可能需要修改服务器属性，使之反映新的计算机名称，然后你将能够部署程序集。|  
   |重新部署|True 或 False|此项设置为 True （默认值），可在不更改版本号的情况下重新部署 BizTalk 程序集。|  
   |安装到全局程序集缓存|True 或 False|此项设置为 True （默认值） 程序集安装到全局程序集缓存 (GAC) 在本地计算机上安装应用程序时。 将此设置为 False 仅当你打算为此安装，如 gacutil 使用其他工具。|  
   |重新启动主机实例|True 或 False|此项设置为 True 会自动重新启动时重新部署程序集在本地计算机上运行的所有主机实例。 如果设置为 False （默认值），则必须手动重新启动主机实例时重新部署程序集。 **注意：** 如果要重新部署程序集从解决方案级，主机实例将重新启动一次每个项目，此选项设置为 True。 这可能会导致多次重新启动。 如果您计划在解决方案级重新部署，可能想要将此属性设置为 True 上只有一个项目中的解决方案，以避免多次主机实例重新启动。 此属性应设置将在重新部署解决方案中的最后一个项目。 此外，如果主机实例停止时执行重新部署，它将不会启动。|  
   |启用单元测试|True 或 False|指定是否为项目启用单元测试。|  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)