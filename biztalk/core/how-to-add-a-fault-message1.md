---
title: "如何添加错误 Message1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a>如何添加错误消息
首次创建通向后端系统的端口时，该端口中包含了请求和响应通信。 必须添加错误来捕获异常。  
  
### <a name="to-add-a-fault-message"></a>添加错误消息  
  
1.  右键单击**端口操作**，然后选择**新的错误消息**。  
  
     A**错误**下显示**请求和响应**端口中。  
  
2.  上**业务流程视图**屏幕上，右键单击**消息**，然后选择**新消息**。  
  
     由此将创建 Message_3，您可将其明确分配给该错误。  
  
3.  右键单击**Message_3**访问**属性**窗口。  
  
    1.  设置**消息类型**。  
  
    2.  选择**架构**，然后选择从**ref 程序集**。  
  
         这将打开**选择项目类型**窗口。  
  
    3.  向下滚动选择该完全限定的错误。  
  
         名称是**BTS。SOAP_Envelope_1__1.fault**。 单击**确定**以接受所选内容并关闭窗口。  
  
4.  右键单击**错误**访问**属性**窗口。  
  
    1.  设置**消息类型**。  
  
    2.  选择**架构**，然后选择从**ref**程序集。  
  
         这将打开**选择项目类型**窗口。  
  
    3.  向下滚动选择该完全限定的错误。  
  
         名称是**BTS。SOAP_Envelope_1__1.fault**。  
  
    4.  单击**确定**以接受所选内容并关闭窗口。  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  对该错误命名后，您需将此名称的类型设置为 CatchException 的异常对象类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling2.md)