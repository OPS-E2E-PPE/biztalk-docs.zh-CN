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
ms.openlocfilehash: 7debc394b29676b15f330a8b5c22fbfe4656d0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351544"
---
# <a name="developing-a-general-pipeline-component"></a>开发常规管道组件

## <a name="interfaces"></a>界面
常规管道组件是.NET 或 COM 组件，可实现以下接口：  
  
- IBaseComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponentUI 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- [IPersistPropertyBag](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  常规管道组件从 BizTalk 消息引擎获取一条消息、 处理它，并返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。 常规组件也可以实现，以便它们不向服务器返回的消息。 此类组件称为使用组件，因为该组件接收消息，而不生成任何结果消息。  
  
> [!NOTE]
>  自定义管道组件应从输入消息复制到输出消息任何其他部分。 这会保留它们在管道中做进一步处理。  
  
## <a name="more-pipeline-resources"></a>更多管道资源
 [开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md)   
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)   
 [开发探测管道组件](../core/developing-a-probing-pipeline-component.md)   
 [报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [部署管道组件](../core/deploying-pipeline-components.md)   
 [CustomComponent（BizTalk Server 示例）](../core/customcomponent-biztalk-server-sample.md)