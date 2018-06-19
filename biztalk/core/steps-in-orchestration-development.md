---
title: 业务流程开发中的步骤 |Microsoft 文档
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
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277389"
---
# <a name="steps-in-orchestration-development"></a>业务流程开发中的步骤
若要开发一个业务流程，您通常执行以下基本操作：  
  
-   添加形状以表示您的业务流程。  
  
     业务流程设计器为你提供可以用来表示不同的操作或其他抽象的形状的工具箱。 有关详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。  
  
-   定义架构来描述消息的格式。  
  
     你可以定义架构使用 BizTalk 编辑器。 有关详细信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。  
  
-   定义的端口通过其发送和接收消息。  
  
     你可以定义端口，以指定如何以及在何处发送和接收消息。 有关详细信息，请参阅[在业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
-   将绑定**发送**和**接收**形状链接到端口。  
  
     你可以连接你**发送**和**接收**形状到端口，并指定它们使用的端口操作。 有关详细信息，请参阅[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。 另请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。  
  
-   分配或转换消息之间的数据。  
  
     你可以使用**构造消息**调整赋值消息或执行消息转换。 有关详细信息，请参阅[构造消息](../core/constructing-messages.md)。  
  
-   标识你可能想要将添加为引用中运行您的业务流程或编写任何自定义组件。  
  
> [!NOTE]
>  如果**Copy Local**引用程序集的属性设置为**True**，业务流程将无法以拾取之后的初始添加引用发生在对外部程序集所做任何更改BizTalk 项目。  
  
-   定义并将用于管理运行业务流程中的数据的业务流程变量。  
  
     你可以使用在业务流程视图窗口中变量文件夹声明你的业务流程变量和 BizTalk 表达式编辑器来编辑表达式分配并使用各种形状中的变量。 有关详细信息，请参阅[XLANG-s 数据类型](../core/xlang-s-data-types.md)。  
  
-   生成您的业务流程，以出于完整性的考虑对其进行测试。  
  
     编译项目或包含它的解决方案时，你可以生成您的业务流程。 有关详细信息，请参阅[如何构建业务流程](../core/how-to-build-orchestrations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [生成并运行业务流程](../core/building-and-running-orchestrations.md)   
 [管理业务流程](../core/managing-orchestrations.md)   
 [创建使用业务流程设计器的业务流程](../core/creating-orchestrations-using-orchestration-designer.md)