---
title: 使用 BizTalk 服务器项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>使用 BizTalk 服务器项目中的 WCF LOB 适配器 SDK 适配器
本主题介绍如何使用适配器使用生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
> [!NOTE]
>  若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，必须安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]上相同的计算机承载工具[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  
 
  
1.  打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]中**项目**窗格中，右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目，，然后选择**添加**&#124;**添加生成的项** &#124; **使用适配器服务**。  
  
3.  在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]屏幕上，选择适配器绑定。  
  
4.  单击**配置**以配置所选的适配器绑定的连接 URI 并提供任何凭据、 URI 属性和绑定属性。 实际要求将因所选的适配器绑定上。  
  
5.  单击**确定**配置 URI 时。  
  
6.  单击 **“连接”**。 连接 URI 是否有效并且接受客户端凭据 （如果有），**类别**窗格中应使用的类别和操作提供的适配器来填充。  
  
7.  如果适配器支持搜索，搜索字段将处于活动状态。 否则为你可以按协定类型和筛选浏览通过单击中的节点的类型和操作**类别**窗格。  
  
8.  单击**确定**生成代理项目。 项目数而异的协定类型：  
  
    |协定类型|项目|Description||  
    |-------------------|--------------|-----------------|-|  
    |出站|XML 架构|包含所选的类型和操作的架构。||  
    |出站||WCF 自定义发送端口绑定信息 XML|包含 WCF 自定义发送端口的配置 XML。|  
    |入站|XML 架构|包含所选的类型和操作的架构。||  
    |入站||WCF 自定义接收端口绑定信息 XML|WCF 自定义接收端口，则包含配置 XML。|  
  
9. 你现在可以使用中的 XML 架构文件你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
## <a name="deploy-the-biztalk-server-project"></a>部署 BizTalk Server 项目  
  
1.  打开 **“BizTalk Server 管理”**。  
  
2.  导入要创建的物理端口的端口绑定 XML 文件。 右键单击受测应用程序**应用程序**组中，选择**导入绑定**，然后导航到并选择适当的端口绑定信息 XML 文件。  
  
3.  在中定义的逻辑端口映射你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]到新创建的物理端口的业务流程。  
  
4.  单击**业务流程**下你的应用程序，右键单击业务流程，以登记，然后单击**Enlist**。  
  
5.  单击**业务流程**下你的应用程序，右键单击业务流程，以登记，然后单击**启动**。  
  
6.  右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，，然后单击**启动**。  
  
## <a name="generate-multiple-schemas"></a>生成多个架构  
 如果使用使用适配器服务向导来生成多个架构，可能导致编译失败的架构中与一个或多个元素的重复[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 你可以通过选择来避免这**生成唯一的架构类型**复选框以确保与唯一的命名空间，将生成的架构类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用使用 WCF LOB 适配器 SDK 创建的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)