---
title: 接收适配器操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d4e5ee9d9afbbb687f415b42652d76a50bac4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980118"
---
# <a name="receive-adapter-operations"></a>接收适配器操作
接收适配器可执行以下操作：  

- **单向提交： void SubmitMessage (IBaseMessage msg)。** 后从接收端口接收消息，适配器将消息提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要处理的订阅业务流程或发送端口。  

- **挂起： void MoveToSuspendQ (IBaseMessage msg)。** 在提交后当适配器确定发生了解析、传输、序列化或其他有关错误时，该适配器会将消息移到“挂起”队列。  

- **提交请求： void SubmitRequestMessage （IBaseMessage requestMsg，字符串 correlationToken，[marshalas （unmanagedtype.bool)] bool firstResponseOnly，DateTime expirationTime，IBTTransmitter responseCallback）。** 接收适配器将提交到传入消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求-响应对中。 之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成功处理此请求消息，它将发送到适配器以将其传输到特定终结点的响应。
