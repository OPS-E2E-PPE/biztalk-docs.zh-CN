---
title: 开发常规管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca387b139a32606dea89f7c931c86245d151dcb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966686"
---
# <a name="developing-a-general-pipeline-component"></a>开发常规管道组件

## <a name="interfaces"></a>界面
常规管道组件是一种 .NET 或 COM 组件，可实现以下接口：  
  
- IBaseComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponentUI 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- [IPersistPropertyBag](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  常规管道组件从 BizTalk 消息引擎获取一条消息，然后处理该消息，并将已处理的消息返回到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎。 常规组件也可被实现，以便它们不再将消息返回到服务器。 这样的组件称为使用组件，因为这类组件只接收消息，而不生成任何结果消息。  
  
> [!NOTE]
>  自定义管道组件应将输入消息的所有附加部分复制到输出消息。 这样可以在管道中对它们作进一步处理。  
  
## <a name="more-pipeline-resources"></a>更多管道资源
 [开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md)   
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)   
 [开发探测管道组件](../core/developing-a-probing-pipeline-component.md)   
 [报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [部署管道组件](../core/deploying-pipeline-components.md)   
 [CustomComponent（BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)