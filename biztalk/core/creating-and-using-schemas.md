---
title: "在创建和使用架构 TIBCO |Microsoft 文档"
description: "使用 BizTalk 编辑器创建架构的 BizTalk Adapter TIBCO 企业消息服务，并为 BizTalk Server 设置在架构中的目标命名空间"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384d140832c123f46ecf531e64b3c1ca11e64f4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-and-use-tibco-schemas"></a>创建和使用 TIBCO 架构

## <a name="overview"></a>概述
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器使用通过 Visual Studio 中的 XML 编辑器或 BizTalk Server 编辑器创建的架构（仅当在业务流程中使用适配器时）。 此架构描述您期望的信息类型。 本主题包含有关发送和接收处理程序的信息。  
  
为与用于 TIBCO Enterprise Message Service 的 BizTalk 适配器一起使用而创建的架构必须有目标命名空间。 BizTalk Server 需要此目标命名空间是因为，它是将给定消息实例与给定业务流程相关联的关键。 换言之，业务流程订阅有特定目标命名空间的任何消息，并且具有该目标命名空间的传入 XML 消息将提供给订阅该消息的每个业务流程。 如果 XML 文档架构没有目标命名空间，BizTalk Server 将使用根元素的名称作为关键。  

以下步骤显示如何生成架构，以及如何设置的目标命名空间。  
  
## <a name="generate-a-schema"></a>生成架构    
 
1.  在 BizTalk 编辑器中，打开您的项目。  
  
2.  在解决方案资源管理器右上角中，选择**添加**，然后选择**添加生成的项**。  
  
3.  在**模板**窗格中，选择**生成架构**，然后单击**添加**。  
  
4.  在**生成架构**对话框中，在**文档类型**列表中，选择**格式正确 XML**。  
  
5.  单击**浏览**以找到你要为其生成架构，并依次输入的文件**确定**。  
  
接下来，设置的目标命名空间。  
  
## <a name="set-the-target-namespace"></a>设置的目标命名空间  
  
1.  在 BizTalk 编辑器中，打开架构文件，右键单击**\<架构\>**，然后选择**属性**。  
  
2.  在**属性**窗格中，找到**Namespace**字段并键入一个名称，例如， `testNameSpace`。  
  
 然后，可以使用消息继续您的业务流程。 选择消息时，BizTalk Server 会查找使用相应架构（具有设置的目标命名空间）的业务流程，然后开始业务流程进程。  
  
## <a name="see-also"></a>另请参阅  
 [开发应用程序](../core/developing-applications5.md)