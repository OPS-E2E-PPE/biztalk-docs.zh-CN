---
title: 从管道组件的错误报告 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c111a0c10f4316e7b29e873adf53a8e6b9a9acd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976035"
---
# <a name="reporting-errors-from-pipeline-components"></a>从管道组件的报告错误
管道组件用两种方式报告错误：  
  
-   对于基于 .NET 的组件，通过引发异常。  
  
-   对于基于 COM 的组件，通过设置**ErrorInfo**对象并返回失败 HRESULT。  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>报告来自 .NET 管道组件的错误  
 若要报告某一错误，基于 .NET 的管道组件需要引发一个异常，以便报告错误说明。 若要报告引发错误的组件的名称，设置**源**属性**异常**对象。  
  
 The Messaging Engine 使用**消息**和**源**属性**异常**对象以报告的错误。 下面的消息将写入事件日志：  
  
 "出现故障执行 [接收 &#124; 发送] 管道：\<管道名称\>源：\<源\>[接收位置 &#124;发送端口:]\<位置 &#124; 端口名称\>原因：\<消息\>。"  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>报告来自 COM 管道组件的错误  
 若要报告某一错误，基于 COM 的管道组件快执行以下操作：  
  
1.  管道组件集**IErrorInfo**对象通过调用**SetErrorInfo**方法。  
  
2.  管道组件将失败的 HRESULT 返回到消息引擎。  
  
 The Messaging Engine 使用**GetSource**和**GetDescription**属性**IErrorInfo**对象以报告的错误。 如果未设置源，则使用该组件的名称。 如果描述不是组或整个**ErrorInfo**未设置对象，而不是说明报告返回的 HRESULT。 下面的消息将写入事件日志：  
  
 "出现故障执行 [接收 &#124; 发送] 管道：\<管道名称\>源： \<GetSource\> [接收位置 &#124;发送端口:]\<位置 &#124; 端口名称\>原因： \<GetDescription 或 HRESULT\>。"  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)