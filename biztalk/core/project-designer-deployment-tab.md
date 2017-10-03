---
title: "项目设计器： 部署选项卡 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="project-designer-deployment-tab"></a>项目设计器：“部署”选项卡
**部署**项目设计器的属性选项卡允许你配置 BizTalk 项目的部署属性。 你必须配置这两**服务器**和**配置数据库**（也称为 BizTalk 管理数据库） 与用于部署成功的集的属性。  
  
## <a name="application-name"></a>应用程序名称  
 指定在其中部署程序集的 BizTalk 应用程序。 如果此项为空，则项目将部署到默认应用程序中。  
  
## <a name="configuration-database"></a>配置数据库  
 使用此字段可为已部署的程序集指定 BizTalk 配置数据库的名称。 此项适用于已将 BizTalk 项目配置为部署项目的情况。  
  
> [!NOTE]
>  BizTalk 配置数据库也称为 BizTalk 管理数据库。  
  
 默认配置数据库的名称为 BizTalkMgmtDb。  
  
## <a name="server"></a>Server  
 这是配置存储库（也称为 BizTalk 管理数据库或配置数据库）所在的服务器的名称。 如果将 BizTalk 项目配置为“部署”，则会将该 BizTalk 项目部署到此服务器。  
  
## <a name="redeploy"></a>重新部署  
 你使用**重新部署**属性以确定是否要删除现有的配置并重新创建的配置部署程序集，每次。 默认值是`True`。  
  
## <a name="install-to-global-assembly-cache"></a>安装到全局程序集缓存  
 你使用**安装到全局程序集缓存**属性以指示如果[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]需要将 BizTalk 程序集安装到全局程序集缓存 (GAC)。  
  
## <a name="restart-host-instances"></a>重新启动主机实例  
 如果你设置**重新启动主机实例**到**True**，将项目部署时重新启动本地计算机上的主机实例[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 在开发周期中要进行更改并经常重新部署时，使用此选项将十分有用，因为您无需手动重新启动相关的主机实例。  
  
 如果不重新启动相关的主机实例，则最新更改可能无法反映到 BizTalk 应用程序上，因为旧版本可能仍存在于缓存中。 重新启动主机实例将清除缓存的程序集。  
  
## <a name="enable-unit-testing"></a>启用单元测试  
 指定是否为项目启用单元测试。  
  
## <a name="see-also"></a>另请参阅  
 [如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk 项目属性窗口](../core/biztalk-project-properties-window.md)