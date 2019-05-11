---
title: 如何将服务器添加到组 |Microsoft Docs
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
ms.openlocfilehash: d26d3133c6c81bddc04b9fbc8868066a538599cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343377"
---
# <a name="how-to-add-a-server-to-a-group"></a>如何将服务器添加到组
BizTalk Server 配置可用于将服务器添加到 BizTalk 组。 将其他服务器添加到 BizTalk 组，以向外扩展 BizTalk Server 环境。  
  
 一台服务器只能与一个 BizTalk 组相关联。 如果服务器已属于另一个组，则必须首先删除该服务器从其当前组之前可以将其添加到新的组。 有关从 BizTalk 组中删除服务器的信息，请参阅[如何从一个组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)。  
  
> [!NOTE]
>  与 BizTalk Server 环境中的不同服务器相关联的 BizTalk 组除交换消息不进行交互。  
  
> [!IMPORTANT]
>  必须在你想要添加到 BizTalk 组的计算机上安装 BizTalk Server 运行时。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须为 SSO Administrators 组的成员和 Windows Administrators 组的成员身份登录。  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a>若要将服务器添加到 BizTalk 组  
  
1. 在你想要添加到 BizTalk Server 组添加到的计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.  
  
2. 在中**Microsoft BizTalk Server 配置**，选择**自定义配置**。  
  
3. 在中**数据库服务器名称**，服务器将加入 BizTalk 组中键入的 SQL Server 的名称。  
  
4. 在中**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。  
  
5. 在屏幕左侧导航树中，单击**企业 SSO**。  
  
6. 上**企业单一登录**页上，单击**加入现有 SSO 系统**。  
  
    请确保服务器名称和数据库名称指向该服务器将加入的 BizTalk Server 组的主 SSO 数据库服务器。  
  
7. 在屏幕左侧导航树中，单击**组**。  
  
8. 上**组**页上，单击**加入现有 BizTalk 组**。  
  
    请确保服务器名称和数据库名称指向该服务器加入 BizTalk Server 组的数据库。  
  
9. 在菜单栏上，单击**应用配置**若要在此计算机上配置企业单一登录和组。  
  
## <a name="see-also"></a>请参阅  
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [管理组](../core/managing-groups.md)   
 [BizTalk 组](../core/biztalk-groups.md)   
 [如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [如何从一个组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)   
 [如何修改组属性](../core/how-to-modify-group-properties.md)   
 [管理服务器](../core/managing-servers.md)