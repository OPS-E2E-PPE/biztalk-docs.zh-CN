---
title: 如何添加容错 Message1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9bcaab8db10ee0be664b02028af9b9a79981d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343847"
---
# <a name="how-to-add-a-fault-message"></a>如何添加错误消息
当你首次创建该端口与后端系统时，它包含请求和响应。 您必须添加错误来捕获异常。  
  
### <a name="to-add-a-fault-message"></a>若要添加错误消息  
  
1.  右键单击**端口操作**，然后选择**新建错误消息**。  
  
     一个**容错**下显示**请求和响应**端口中。  
  
2.  上**业务流程视图**屏幕上，右键单击**消息**，然后选择**新消息**。  
  
     这将创建 Message_3，您可以将其分配特定于该错误。  
  
3.  右键单击**Message_3**访问**属性**窗口。  
  
    1.  设置**消息类型**。  
  
    2.  选择**架构**，然后选择从**引用程序集**。  
  
         这将打开**选择项目类型**窗口。  
  
    3.  向下滚动并选择完全限定的错误。  
  
         名称是**BTS。SOAP_Envelope_1__1.fault**。 单击**确定**以接受选择并关闭窗口。  
  
4.  右键单击**容错**访问**属性**窗口。  
  
    1.  设置**消息类型**。  
  
    2.  选择**架构**然后选择从**ref**程序集。  
  
         这将打开**选择项目类型**窗口。  
  
    3.  向下滚动并选择完全限定的错误。  
  
         名称是**BTS。SOAP_Envelope_1__1.fault**。  
  
    4.  单击**确定**以接受选择并关闭窗口。  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  该错误命名后，您将此名称设置为 CatchException 的异常对象类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling2.md)