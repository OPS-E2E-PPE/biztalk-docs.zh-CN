---
title: "接收来自 PeopleSoft |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca87df1875f648abe2a986fb0d94b16865ee72f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="receiving-from-peoplesoft"></a>接收来自 PeopleSoft
PeopleSoft 企业 Microsoft 适配器是发送适配器。 该适配器支持要求响应，从而您可以发送查询并获得响应。 但是，如果你只希望从 PeopleSoft 接收数据，你必须执行两个附加步骤：  
  
1.  创建使用设置 Namespace 管道组件的自定义接收管道。  
  
2.  接收端口访问从创建 PeopleSoft 例如端口使用 HTTP 适配器。 使用与接收端口的自定义接收管道。  
  
## <a name="set-namespace-pipeline-component"></a>设置 Namespace 管道组件  
 从 PeopleSoft 接收的消息不包括命名空间。 设置 Namespace 管道组件，可将命名空间添加到传入的消息。  
  
 设置 Namespace 管道组件的默认位置是 C:\Program Files\Microsoft BizTalk 适配器企业 Applications\Pipeline 组件。 你需要将该组件，Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll，复制到由 BizTalk 使用的管道组件的目录。 你还需要将该组件添加到 Visual Studio 工具箱中，以在管道设计器中使用它。  
  
 有关在何处安装组件的信息，请参阅[部署管道组件](../core/deploying-pipeline-components.md)。  
  
 有关将组件添加到 Visual Studio 工具箱的信息，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。  
  
## <a name="configure-the-set-namespace-pipeline-component"></a>配置集 Namespace 管道组件  
 设置 Namespace 管道组件具有两个属性可以设置：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**默认目标 Namespace**|传入消息中将固定的命名空间。|  
|**目标 Namespace XPath**|从传入的消息将其从指定的 XPath 位置提取命名空间。 如果组件未找到有效的命名空间，它记录应用程序事件日志中的警告，并且如果指定，将使用默认目标 Namespace。|  
  
 如果将这两个属性保留为空，则该组件不会对传入消息分配命名空间，而未写入警告到应用程序事件日志中。  
  
## <a name="see-also"></a>另请参阅  
 [开发应用程序](../core/developing-applications4.md)