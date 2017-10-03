---
title: "如何配置每个实例的管道属性接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e14483c5d17d968fc79126c65506720b501b6da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>如何配置每个实例的管道属性接收位置
本主题介绍在将管道部署到 BizTalk 组之后如何使用 BizTalk Server 管理控制台为接收位置配置管道属性。 您所做的更改将只覆盖此接收位置的默认管道属性，因此如果需要，可以为 BizTalk 组中的每个接收位置配置不同的管道属性。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
> [!NOTE]
>  使用每个实例管道属性设置的值时**DocumentSpecNames**必须在相同的项目中定义管道、 指定的文档架构和管道的 XML 反汇编程序组件中的属性。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>为接收位置配置基于实例的管道属性  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含要配置管道属性，请展开的接收位置的 BizTalk 组**应用程序**，，然后展开包含接收位置的应用程序。  
  
3.  单击**接收位置**文件夹，右键单击接收位置，然后单击**属性**。  
  
4.  单击右侧的省略号 （...）**接收管道**框。  
  
5.  配置属性，然后单击**确定**。 有关详细信息，请单击**帮助**的属性页上。  
  
    > [!IMPORTANT]
    >  请确保输入正确的管道属性的信息。 如果输入无效值，例如字符串而不是数字，它将生成一个错误。  
  
6.  如果这是请求-响应接收位置，单击右侧的省略号 （...）**发送管道**框。  
  
7.  配置属性，然后单击**确定**两次。 有关详细信息，请单击**帮助**的属性页上。  
  
## <a name="see-also"></a>另请参阅  
 [管理管道](../core/managing-pipelines.md)   
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [管理接收位置](../core/managing-receive-locations.md)