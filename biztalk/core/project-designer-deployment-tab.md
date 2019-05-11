---
title: 项目设计器：部署选项卡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6cf82e112834dbacc021e3ce5564866a2e8cbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395618"
---
# <a name="project-designer-deployment-tab"></a>项目设计器：部署选项卡
**部署**项目设计器的属性选项卡允许你配置的 BizTalk 项目的部署属性。 您必须同时配置两者**服务器**并**配置数据库**（也称为 BizTalk 管理数据库） 属性作为组进行部署才能成功。  
  
## <a name="application-name"></a>应用程序名称  
 指定要在其中部署该程序集的 BizTalk 应用程序。 如果它为空，则项目将部署到默认应用程序。  
  
## <a name="configuration-database"></a>配置数据库  
 使用此字段为部署的程序集指定 BizTalk 配置数据库的名称。 如果将 BizTalk 项目配置为部署项目是如此。  
  
> [!NOTE]
>  BizTalk 配置数据库也称为 BizTalk 管理数据库。  
  
 默认配置的数据库名称为 BizTalkMgmtDb。  
  
## <a name="server"></a>“服务器”  
 这是服务器的配置存储库 （也称为 BizTalk 管理数据库或配置数据库） 所在的名称。 如果配置为"部署"。 在 BizTalk 项目到此服务器部署 BizTalk 项目  
  
## <a name="redeploy"></a>重新部署  
 您使用**重新部署**属性来确定是否删除现有配置并重新创建配置每次部署程序集。 默认值是 `True`。  
  
## <a name="install-to-global-assembly-cache"></a>安装到全局程序集缓存  
 您使用**安装到全局程序集缓存**属性以指示如果[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]需要 BizTalk 程序集安装到全局程序集缓存 (GAC)。  
  
## <a name="restart-host-instances"></a>重新启动主机实例  
 如果您设置**重新启动主机实例**到**True**，将部署项目时重新启动本地计算机上的主机实例[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 这可在开发周期时，您要进行更改，并经常重新部署;您不需要手动重新启动相关的主机实例。  
  
 如果不重新启动相关的主机实例，最新的更改可能不反映在 BizTalk 应用程序中，因为旧版本仍可进行缓存。 重新启动主机实例将清除缓存的程序集。  
  
## <a name="enable-unit-testing"></a>启用单元测试  
 指定是否启用单元测试项目。  
  
## <a name="see-also"></a>请参阅  
 [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [BizTalk 项目属性窗口](../core/biztalk-project-properties-window.md)