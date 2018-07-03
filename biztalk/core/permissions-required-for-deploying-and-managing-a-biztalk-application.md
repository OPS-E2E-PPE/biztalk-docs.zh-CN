---
title: 用于部署和管理 BizTalk 应用程序所需的权限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4dcf35fb7975e878e6603712d5a56d2bd89a89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019648"
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a>用于部署和管理 BizTalk 应用程序所需的权限
应用程序部署包括部署 BizTalk 程序集从 Visual Studio，以及导入、 导出和安装 BizTalk 应用程序。 若要执行这些任务所需的基本权限如下所示：  
  
- 作为 BizTalk Server Administrators 组的成员，将授予部署 BizTalk 程序集从 Visual Studio 所需的权限。  
  
- 作为 BizTalk Server Administrators 组的成员，授予所需将 BizTalk 应用程序导入 BizTalk 组的权限。 如果已指定该选项可以添加到全局程序集缓存 (GAC) 上导入应用程序中包括程序集，您还必须写入权限的程序集文件夹。 作为本地 Administrators 组的成员，您将拥有此权限。  
  
- 作为 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员，被授予所需的权限：  
  
  -   导出 BizTalk 应用程序  
  
  -   启动和停止发送端口、 发送端口组和业务流程  
  
  -   启用和禁用接收位置  
  
  -   挂起、 继续和终止实例  
  
  -   启动和停止应用程序  
  
- 作为本地 Administrators 组的成员授予权限以在本地计算机上安装 BizTalk 应用程序。  
  
  您可能想要提供限制性最强的权限，用户才能执行这些任务。 此主题的其余部分，如下所示提供所需权限的更多详细信息。  
  
- [用于部署 BizTalk 程序集从 Visual Studio 的权限](#BKMK_Permissions_for_deploying)  
  
- [导入应用程序的权限](#BKMK_Permissions_for_importing)  
  
- [导出应用程序的权限](#BKMK_Permissions_for_exporting)  
  
- [安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a> 用于部署 BizTalk 程序集从 Visual Studio 的权限  
 若要部署 BizTalk 程序集从 Visual Studio 中的，必须在 BizTalk 管理数据库中，至少具有写入权限。 授予此权限作为 BizTalk Server Administrators 组的成员。  
  
##  <a name="BKMK_Permissions_for_importing"></a> 导入应用程序的权限  
 要导入 BizTalk 应用程序，必须至少具有以下权限。 您已被授予所有所需的权限作为 BizTalk Server Administrators 组的成员，但如果你想要安装到 GAC 中的任何程序集，还必须对程序集文件夹具有写权限。  
  
|项|权限|在需要时|  
|----------|-----------------|-------------------|  
|BizTalk 管理数据库|读/写|始终要求。|  
|BizTalk 规则引擎数据库|读/写|才被必需的应用程序如果包括规则资源。|  
|BAM 数据库|读/写|才被必需的应用程序如果包括 BAM 资源|  
|全局程序集缓存 (GAC)|读/写|如果应用程序包括程序集资源，并且你指定的程序集都添加到 GAC 上导入必需的仅。 （参见备注。）|  
  
> [!NOTE]
>  在使用导入向导导入程序集，可以指定将程序集添加到全局程序集缓存 (GAC) 的选项。 在这种情况下，您必须对程序集文件夹具有写入权限。 有关程序集文件夹的详细信息，请参阅[安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)。  
>   
>  如果你的应用程序包括用于部署所列内容之外的任何项的脚本，必须具有适当的权限来部署的其他项。  
  
##  <a name="BKMK_Permissions_for_exporting"></a> 导出应用程序的权限  
 若要导出 BizTalk 应用程序，必须至少具有以下权限。 为 BizTalk Operators 组的成员具有所需的权限。  
  
|项|权限|在需要时|  
|----------|-----------------|-------------------|  
|BizTalk 管理数据库|读取|始终要求。|  
|BizTalk 规则引擎数据库|读取|才被必需的应用程序如果包括规则资源。|  
|证书存储区|读取|才被必需的应用程序如果包括证书资源。|  
|Internet Information Services|读取|才被必需的应用程序如果包括虚拟目录资源。|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a> 安装应用程序的权限  
 默认情况下，本地管理员组的成员具有在本地计算机上安装 BizTalk 应用程序所需的权限。 如果你想要向需要安装应用程序的用户提供更受限制的权限下, 表提供了您必须配置的最低权限。 除了这些权限，如果你的应用程序包含具有其他权限才能安装，例如，创建一个新的数据库或数据库表的资源您必须还具有这些权限。  
  
|项|权限|在需要时|  
|----------|-----------------|-------------------|  
|证书存储区|读/写|才被必需的应用程序如果包括证书资源。|  
|Internet Information Services|读/写|才被必需的应用程序如果包括虚拟目录资源。|  
|GAC|读/写|如果应用程序包括程序集资源，并且你指定的程序集都添加到 GAC 上安装必需的仅。 （请注意，参阅下面。）|  
|文件系统|读/写|才被必需的目标属性是否已设置的资源。|  
|注册表|读/写|需要**regsvcs**或**regasm**属性设置为 True，为一个程序集资源，其中包含托管 COM 或 COM + 组件。|  
|注册表|读/写|所需的应用程序如果包括非托管的 COM 资源|  
  
> [!NOTE]
>  从 BizTalk Server 管理控制台中，可以指定将程序集添加到安装在 GAC （右键单击资源文件夹中的程序集，然后单击修改）。 如果指定此选项，然后安装的 BizTalk 应用程序需要编写程序集文件夹，其中包含在 GAC 上的权限。 程序集文件夹的路径为 %systemroot%\assembly。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)