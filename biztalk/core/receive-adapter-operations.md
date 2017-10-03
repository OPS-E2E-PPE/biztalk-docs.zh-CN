---
title: "接收适配器操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804a136841c33977b350b8d59dfbf18c7108cc79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-adapter-operations"></a>接收适配器操作
接收适配器可执行以下操作：  
  
-   **单向提交： void SubmitMessage (IBaseMessage msg)。** 接收端口从接收消息之后, 该适配器将其提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由订阅业务流程处理或发送端口。  
  
-   **挂起： void MoveToSuspendQ (IBaseMessage msg)。** 在提交后当适配器确定发生了解析、传输、序列化或其他有关错误时，该适配器会将消息移到“挂起”队列。  
  
-   **提交请求： void SubmitRequestMessage （IBaseMessage requestMsg，字符串 correlationToken，[MarshalAs(UnmanagedType.Bool)] bool firstResponseOnly，DateTime expirationTime，IBTTransmitter responseCallback）。** 接收适配器传入将消息提交至[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求-响应对中。 后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成功处理此请求消息，它将响应发送到适配器无法传送到特定终结点。