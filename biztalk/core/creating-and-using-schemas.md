---
title: 创建和使用架构中 TIBCO |Microsoft Docs
description: 使用 BizTalk 编辑器创建架构的 BizTalk 适配器用于 TIBCO Enterprise Message Service，并为 BizTalk Server 在架构中设置的目标命名空间
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 151ddefb45afd41c343b43de44786d7d99ff9b94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353672"
---
# <a name="create-and-use-tibco-schemas"></a>创建和使用 TIBCO 架构

## <a name="overview"></a>概述
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器将使用 （仅当在业务流程中使用适配器） 使用在 Visual Studio 中的 XML 编辑器或 BizTalk Server 编辑器创建架构。 此架构描述您期望的信息的类型。 本主题包含有关发送和接收处理程序的信息。  
  
创建供使用的 BizTalk 适配器用于 TIBCO Enterprise Message Service 的架构必须具有目标命名空间。 BizTalk Server 需要的目标命名空间，因为它是将给定的消息实例与给定的业务流程相关联的密钥。 换而言之，业务流程订阅任何消息具有特定的目标命名空间，并且具有该目标命名空间的传入 XML 消息将提供给每个订阅该消息的业务流程。 如果 XML 文档架构没有目标命名空间，BizTalk Server 使用根元素的名称作为键。  

以下步骤说明如何生成架构，以及如何设置目标命名空间。  
  
## <a name="generate-a-schema"></a>生成架构    
 
1.  在 BizTalk 编辑器中，打开你的项目。  
  
2.  在解决方案资源管理器在右上角，选择**外**，然后选择**添加生成的项**。  
  
3.  在中**模板**窗格中，选择**生成架构**，然后单击**添加**。  
  
4.  在中**生成架构**对话框中**文档类型**列表中，选择**格式正确的 XML**。  
  
5.  单击**浏览**以找到你要为其生成架构，然后依次输入的文件**确定**。  
  
接下来，设置目标命名空间。  
  
## <a name="set-the-target-namespace"></a>设置目标命名空间  
  
1. 在 BizTalk 编辑器中打开架构文件，右键单击**\<架构\>**，然后选择**属性**。  
  
2. 在中**属性**窗格中，找到**Namespace**字段并键入一个名称，例如， `testNameSpace`。  
  
   然后可以继续使用消息的业务流程。 当提取消息时，BizTalk Server 会查找与设置目标命名空间，使用的架构的业务流程，其后的业务流程。  
  
## <a name="see-also"></a>请参阅  
 [开发应用程序](../core/developing-applications5.md)