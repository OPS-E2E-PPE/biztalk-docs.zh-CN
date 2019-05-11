---
title: 如何配置每个实例为发送端口的管道属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ab5b83ae12cd6de262e23ed2136f1c9a886d57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341235"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>如何配置每个实例为发送端口的管道属性
本主题介绍如何使用 BizTalk Server 管理控制台后管道部署到 BizTalk 组配置为发送端口的管道属性。 所做的更改覆盖默认管道，此发送端口属性，因此如果希望，可以将不同的管道属性的每个发送端口配置 BizTalk 组中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
> [!NOTE]
>  使用每个实例的管道属性设置的值时**DocumentSpecNames** XML 拆装器组件的管道、 指定的文档架构和管道中的属性必须在同一项目中定义。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>若要配置每个实例为发送端口的管道属性  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开包含您要为其配置管道属性中，展开的发送端口的 BizTalk 组**应用程序**，，然后展开包含发送端口的应用程序。  
  
3. 单击**发送端口**文件夹中，右键单击该发送端口，然后依次**属性**。  
  
4. 单击省略号 (**...**) 右侧的按钮**发送管道**框。  
  
5. 配置属性，然后单击**确定**。 单击**帮助**的详细信息的属性页上。  
  
   > [!IMPORTANT]
   >  请确保输入正确的管道属性的信息。 如果输入无效值，例如一个字符串，而不是数字，它将生成一个错误。  
  
6. 如果这是要求响应发送端口，单击省略号 (**...**) 右侧的按钮**接收管道**框。  
  
7. 配置属性，然后单击**确定**两次。 单击**帮助**的详细信息的属性页上。  
  
## <a name="see-also"></a>请参阅  
 [管理管道](../core/managing-pipelines.md)   
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [管理接收位置](../core/managing-receive-locations.md)