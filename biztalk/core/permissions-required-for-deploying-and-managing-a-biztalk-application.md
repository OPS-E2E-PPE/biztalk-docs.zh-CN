---
title: "用于部署和管理 BizTalk 应用程序所需权限 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying [applications], security
- permissions, EDI adapters
- deploying, security
- security, applications
- security, EDI adapters
- assemblies, permissions
- permissions, deploying
- EDI adapters, security
- permissions, assemblies
- security, assemblies
- permissions, applications
- deploying, permissions
- applications, importing
- applications, exporting
- permissions, exporting
- installing, permissions
- applications, security
- security, permissions
- applications, installing
- assemblies, security
- managing, security
ms.assetid: 4a459ff1-661d-403a-99e0-d54b82e008d0
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608da93cd1960d26304f4dcebe239367de2404e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a>用于部署和管理 BizTalk 应用程序所需权限
应用程序部署包括部署 BizTalk 从 Visual Studio 的程序集，以及导入、 导出和安装 BizTalk 应用程序。 你需要执行这些任务的基本权限如下所示：  
  
-   作为 BizTalk Server Administrators 组的成员，你授予所需部署 BizTalk 从 Visual Studio 的程序集的权限。  
  
-   作为 BizTalk Server Administrators 组的成员，你授予所需 BizTalk 应用程序导入到 BizTalk 组的权限。 如果已指定选项以添加到上导入的全局程序集缓存 (GAC) 应用程序中包含的程序集，你还必须程序集文件夹具有写入权限。 作为本地 Administrators 组的成员，您将拥有此权限。  
  
-   作为 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员，您被授予所需的权限：  
  
    -   在导出 BizTalk 应用程序  
  
    -   启动和停止发送端口、 发送端口组和业务流程  
  
    -   启用和禁用接收位置  
  
    -   挂起、 继续和终止实例  
  
    -   启动和停止应用程序  
  
-   作为本地 Administrators 组的成员都被授予权限的本地计算机上安装 BizTalk 应用程序。  
  
 你可能想要提供的用户来执行这些任务的限制最严格权限。 此主题的其余部分，如下所示提供所需的权限，有关的更多详细信息。  
  
-   [部署 BizTalk 从 Visual Studio 的程序集的权限](#BKMK_Permissions_for_deploying)  
  
-   [用于导入应用程序的权限](#BKMK_Permissions_for_importing)  
  
-   [导出应用程序的权限](#BKMK_Permissions_for_exporting)  
  
-   [安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a>部署 BizTalk 从 Visual Studio 的程序集的权限  
 若要部署从 Visual Studio 中的 BizTalk 程序集，必须在 BizTalk 管理数据库中，至少具有写入权限。 您被授予此权限与 BizTalk Server Administrators 组的成员。  
  
##  <a name="BKMK_Permissions_for_importing"></a>用于导入应用程序的权限  
 要导入 BizTalk 应用程序，必须至少具有以下权限。 您已被授予所有所需的权限作为 BizTalk Server Administrators 组的成员，但如果你想要安装到 gac 中的任何程序集，还必须对程序集文件夹具有写入权限。  
  
|项|Permissions|在需要时|  
|----------|-----------------|-------------------|  
|BizTalk 管理数据库|读/写|始终要求。|  
|BizTalk 规则引擎数据库|读/写|才被必需的应用程序如果包括规则资源。|  
|BAM 数据库|读/写|如果该应用程序包括 BAM 资源仅必填项|  
|全局程序集缓存 (GAC)|读/写|如果应用程序包含程序集资源，并指定程序集将添加到导入 GAC 仅必填项。 （参见备注。）|  
  
> [!NOTE]
>  当使用导入向导导入程序集，可以指定将程序集添加到全局程序集缓存 (GAC) 选项。 在这种情况下，你必须在程序集文件夹具有写入权限。 有关程序集文件夹的详细信息，请参阅[安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)。  
>   
>  如果你的应用程序包括部署除列出的任何项的脚本，你必须具有相应权限，无法部署的其他项。  
  
##  <a name="BKMK_Permissions_for_exporting"></a>导出应用程序的权限  
 若要导出 BizTalk 应用程序，必须至少具有以下权限。 作为 BizTalk Operators 组的成员，您被授予所需的权限。  
  
|项|Permissions|在需要时|  
|----------|-----------------|-------------------|  
|BizTalk 管理数据库|读取|始终要求。|  
|BizTalk 规则引擎数据库|读取|才被必需的应用程序如果包括规则资源。|  
|证书存储|读取|才被必需的应用程序如果包括证书资源。|  
|Internet Information Services|读取|才被必需的应用程序如果包括虚拟目录资源。|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a>安装应用程序的权限  
 默认情况下，本地管理员组的成员具有在本地计算机上安装 BizTalk 应用程序所需的权限。 如果你想要向需要安装应用程序的用户提供更受限制的权限下, 表提供了你必须配置的最低权限。 除了这些权限，如果你的应用程序的资源需要额外权限，若要安装，例如创建新数据库或数据库表，你必须还具有这些权限。  
  
|项|Permissions|在需要时|  
|----------|-----------------|-------------------|  
|证书存储|读/写|才被必需的应用程序如果包括证书资源。|  
|Internet Information Services|读/写|才被必需的应用程序如果包括虚拟目录资源。|  
|GAC|读/写|如果应用程序包含程序集资源，并指定程序集将添加到安装在 gac 中仅必填项。 （请注意，下面。）|  
|文件系统|读/写|如果已为资源设置目标属性，则需要仅。|  
|注册表|读/写|如果存在**regsvcs**或**regasm**属性设置为 True，针对一个程序集资源，其中包含托管 COM 或 COM + 组件。|  
|注册表|读/写|所需应用程序如果包括非托管的 COM 资源|  
  
> [!NOTE]
>  从 BizTalk Server 管理控制台中，你可以指定程序集将添加到安装上的 GAC （右键单击资源文件夹中的程序集，然后单击修改）。 如果指定此选项，然后安装的 BizTalk 应用程序需要编写程序集文件夹，其中包含 gac 中的权限。 程序集文件夹的路径为 %systemroot%\assembly。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)