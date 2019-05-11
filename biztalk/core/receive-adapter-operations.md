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
ms.openlocfilehash: 865ad83aa9dc7e19b87f193326dd9061736c2fc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398266"
---
# <a name="receive-adapter-operations"></a>接收适配器操作
接收适配器可执行以下操作：  

- **单向提交： void SubmitMessage (IBaseMessage msg)。** 后从接收端口接收消息，适配器将消息提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要处理的订阅业务流程或发送端口。  

- **挂起： void MoveToSuspendQ (IBaseMessage msg)。** 如果适配器确定了解析、 传输、 序列化或其他有关错误发生提交后，它会将消息移至挂起队列中。  

- **提交请求： void SubmitRequestMessage （IBaseMessage requestMsg，字符串 correlationToken，[marshalas （unmanagedtype.bool)] bool firstResponseOnly，DateTime expirationTime，IBTTransmitter responseCallback）。** 接收适配器将提交到传入消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求-响应对中。 之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成功处理此请求消息，它将发送到适配器以将其传输到特定终结点的响应。
