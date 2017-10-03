---
title: "如何将服务器从一个组移到另一个 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9e5dfdf266d2205283afa7cd9804c31fc93ff3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a>如何将服务器从一个组移到另一个
一台服务器只能与一个 BizTalk Server 组相关联。 若要将服务器从一个组移至另一个组，则必须首先通过取消原始组中对该服务器的配置将其从组中删除，然后再将该服务器添加到新组中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SSO Administrators 组成员和 Windows Administrators 组成员的身份登录。  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a>将服务器从一个 BizTalk 组移至另一个 BizTalk 组  
  
1.  在你想要从 BizTalk 组移到另一个计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.  
  
2.  在菜单栏中，单击**取消配置功能**。  
  
3.  在**取消配置功能**对话框中，选择**企业 SSO**，选择**组**，然后单击**确定**。  
  
    > [!CAUTION]
    >  取消组配置还将取消配置该计算机上已配置的所有依存功能。  
  
4.  单击 **“是”**。  
  
5.  在**Microsoft BizTalk Server 配置**窗口中，单击**下一步**。  
  
     这样就取消了对企业 SSO、组及其依存功能的配置。  
  
6.  单击 **“完成”**。  
  
7.  在**Microsoft BizTalk Server 配置**窗口中，选择**自定义配置**。  
  
8.  在**数据库服务器名称**，其中将服务器转移 BizTalk 组键入 SQL server 的名称。  
  
9. 在**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。  
  
10. 在屏幕左侧的导航树中，单击**企业 SSO**。  
  
11. 上**企业单一登录**页上，单击**加入现有 SSO 系统**。  
  
     确保服务器名称和数据库名称均指向该服务器要移动到的 BizTalk Server 组的主 SSO 数据库服务器。  
  
12. 在屏幕左侧的导航树中，单击**组**。  
  
13. 上**组**页上，单击**加入现有的 BizTalk 组**。  
  
     确保服务器名称和数据库名称均指向该服务器要移动到的 BizTalk Server 组的数据库。  
  
14. 在菜单栏中，单击**应用配置**若要在此计算机上配置企业单一登录和组。  
  
## <a name="see-also"></a>另请参阅  
 [管理组](../core/managing-groups.md)   
 [BizTalk 组](../core/biztalk-groups.md)   
 [如何将服务器添加到组](../core/how-to-add-a-server-to-a-group.md)   
 [如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)   
 [如何修改组属性](../core/how-to-modify-group-properties.md)   
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   
 [如何添加的主机实例](../core/how-to-add-a-host-instance.md)   
 [管理服务器](../core/managing-servers.md)