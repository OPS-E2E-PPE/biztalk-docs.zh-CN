---
title: 从 PeopleSoft 接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3861d885188762b69a08359fbaf9161e02aa5759
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398083"
---
# <a name="receiving-from-peoplesoft"></a>从 PeopleSoft 接收
用于 PeopleSoft Enterprise 的 Microsoft 适配器是一个发送适配器。 适配器支持要求-响应，以便可以发送查询并获得响应。 但是，如果只想从 PeopleSoft 接收数据，必须执行额外两个步骤：  
  
1.  创建使用设置 Namespace 管道组件的自定义接收管道。  
  
2.  创建可接收端口从访问 PeopleSoft 如使用 HTTP 适配器的端口。 使用自定义接收管道与接收端口。  
  
## <a name="set-namespace-pipeline-component"></a>设置 Namespace 管道组件  
 从 PeopleSoft 接收的消息不包括命名空间。 设置 Namespace 管道组件，可将一个命名空间添加到传入的消息。  
  
 设置 Namespace 管道组件的默认位置是 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline 组件。 您需要将该组件，Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll，复制到 biztalk 使用的管道组件的目录。 您还需要将组件添加到 Visual Studio 工具箱中，以在管道设计器中使用它。  
  
 有关在何处安装该组件的信息，请参阅[部署管道组件](../core/deploying-pipeline-components.md)。  
  
 有关将组件添加到 Visual Studio 工具箱的信息，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。  
  
## <a name="configure-the-set-namespace-pipeline-component"></a>配置集 Namespace 管道组件  
 设置 Namespace 管道组件具有两个属性可以设置：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**默认目标 Namespace**|将传入消息中的固定的命名空间。|  
|**目标 Namespace XPath**|从指定的 xpath 的位置将其传入消息中提取命名空间。 如果该组件未找到有效的命名空间，它在应用程序事件日志中记录一个警告，并且如果指定，将使用默认目标 Namespace。|  
  
 如果将这两个属性留空，该组件不会对传入消息分配命名空间，而 does 写入警告应用程序事件日志。  
  
## <a name="see-also"></a>请参阅  
 [开发应用程序](../core/developing-applications4.md)