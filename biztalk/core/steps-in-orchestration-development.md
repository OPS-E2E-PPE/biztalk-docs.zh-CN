---
title: 业务流程开发中的步骤 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 062cff21e067f9e7139c849cf0dd73af5eed1748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244170"
---
# <a name="steps-in-orchestration-development"></a>业务流程开发中的步骤
若要开发业务流程，通常执行以下基本操作：  
  
-   添加形状以表示您的业务流程。  
  
     业务流程设计器为您提供了可用于表示不同的操作或其他抽象形状的工具箱。 有关详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。  
  
-   定义架构来描述消息的格式。  
  
     您可以定义架构使用 BizTalk 编辑器。 有关详细信息，请参阅[如何创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)。  
  
-   定义发送和接收消息是通过该端口。  
  
     您可以定义端口，以指定如何以及在何处发送和接收消息。 有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
-   将绑定**发送**并**接收**到端口形状。  
  
     你可以连接您**发送**并**接收**到端口形状，并指定它们使用的端口操作。 有关详细信息，请参阅[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。 另请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。  
  
-   分配或转换消息之间的数据。  
  
     可以使用**构造消息**形状来分配消息值或执行操作消息的转换。 有关详细信息，请参阅[构造消息](../core/constructing-messages.md)。  
  
-   确定你可能想要编写或将作为引用中运行您的业务流程添加任何自定义组件。  
  
> [!NOTE]
>  如果**Copy Local**引用程序集的属性设置为**True**，业务流程将无法再选取任何初始添加引用发生后对外部程序集所做的更改BizTalk 项目。  
  
-   定义并将业务流程变量来管理在正在运行的业务流程中的数据。  
  
     可以使用在业务流程视图窗口中的变量文件夹来声明你的业务流程变量和 BizTalk 表达式编辑器来编辑分配并使用各种形状中的变量的表达式。 有关详细信息，请参阅[xlang-s 数据类型](../core/xlang-s-data-types.md)。  
  
-   构建您的业务流程来测试出于完整性的考虑。  
  
     编译项目或解决方案，其中包含它时，您构建您的业务流程。 有关详细信息，请参阅[如何生成业务流程](../core/how-to-build-orchestrations.md)。  
  
## <a name="see-also"></a>请参阅  
 [生成和运行业务流程](../core/building-and-running-orchestrations.md)   
 [管理业务流程](../core/managing-orchestrations.md)   
 [使用业务流程设计器创建业务流程](../core/creating-orchestrations-using-orchestration-designer.md)