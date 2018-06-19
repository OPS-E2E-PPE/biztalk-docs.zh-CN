---
title: 如何将服务器添加到组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db5c7b760167f3e17d3ea82bf1023884b65e725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247677"
---
# <a name="how-to-add-a-server-to-a-group"></a>如何将服务器添加到组
您可以使用 BizTalk Server 配置向 BizTalk 组添加服务器。 通过向 BizTalk 组添加其他服务器可以对 BizTalk Server 环境进行扩展。  
  
 一台服务器只能与一个 BizTalk 组相关联。 如果某个服务器已属于其他组，则必须首先从其当前组中删除该服务器，然后才可以将该服务器添加到新的组。 有关从 BizTalk 组中删除服务器的信息，请参阅[如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)。  
  
> [!NOTE]
>  与 BizTalk Server 环境中不同服务器关联的 BizTalk 组除交换消息之外不会进行任何其他交互。  
  
> [!IMPORTANT]
>  必须在要添加到 BizTalk 组的计算机上安装 BizTalk Server 运行时。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SSO Administrators 组成员和 Windows Administrators 组成员的身份登录。  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a>向 BizTalk 组添加服务器  
  
1.  在你想要添加到 BizTalk Server 组添加到的计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.  
  
2.  在**Microsoft BizTalk Server 配置**，选择**自定义配置**。  
  
3.  在**数据库服务器名称**，服务器将加入 BizTalk 组键入 SQL Server 的名称。  
  
4.  在**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。  
  
5.  在屏幕左侧的导航树中，单击**企业 SSO**。  
  
6.  上**企业单一登录**页上，单击**加入现有 SSO 系统**。  
  
     确保服务器名称和数据库名称均指向该服务器要添加到的 BizTalk Server 组的主 SSO 数据库服务器。  
  
7.  在屏幕左侧的导航树中，单击**组**。  
  
8.  上**组**页上，单击**加入现有的 BizTalk 组**。  
  
     确保服务器名称和数据库名称均指向该服务器要添加到的 BizTalk Server 组的数据库。  
  
9. 在菜单栏中，单击**应用配置**若要在此计算机上配置企业单一登录和组。  
  
## <a name="see-also"></a>另请参阅  
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [管理组](../core/managing-groups.md)   
 [BizTalk 组](../core/biztalk-groups.md)   
 [如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)   
 [如何修改组属性](../core/how-to-modify-group-properties.md)   
 [管理服务器](../core/managing-servers.md)