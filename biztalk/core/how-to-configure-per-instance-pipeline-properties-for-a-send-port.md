---
title: "如何配置发送端口的每个实例管道属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb9927dca890a7f84baf372c4fa250a8ced17c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>如何为发送端口配置基于实例的管道属性
本主题介绍如何使用 BizTalk Server 管理控制台来配置发送端口的管道属性，管道已部署到 BizTalk 组后。 您所做更改覆盖默认管道仅，此发送端口属性，这样如果你想，可以将每个发送端口的不同管道属性配置 BizTalk 组中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
> [!NOTE]
>  使用每个实例管道属性设置的值时**DocumentSpecNames**必须在相同的项目中定义管道、 指定的文档架构和管道的 XML 反汇编程序组件中的属性。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>若要配置每个实例管道发送端口属性  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含你想要配置管道属性中，展开发送端口的 BizTalk 组**应用程序**，，然后展开包含发送端口的应用程序。  
  
3.  单击**发送端口**文件夹，右键单击发送端口，然后单击**属性**。  
  
4.  单击省略号 (**...**) 的右侧的按钮**发送管道**框。  
  
5.  配置属性，然后单击**确定**。 单击**帮助**详细信息的属性页上。  
  
    > [!IMPORTANT]
    >  请确保输入正确的管道属性的信息。 如果输入无效值，例如字符串而不是数字，它将生成一个错误。  
  
6.  如果这是请求-响应发送端口，单击省略号 (**...**) 的右侧的按钮**接收管道**框。  
  
7.  配置属性，然后单击**确定**两次。 单击**帮助**详细信息的属性页上。  
  
## <a name="see-also"></a>另请参阅  
 [管理管道](../core/managing-pipelines.md)   
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [管理接收位置](../core/managing-receive-locations.md)