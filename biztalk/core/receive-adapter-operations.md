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
# <a name="receive-adapter-operations"></a><span data-ttu-id="3c2b1-102">接收适配器操作</span><span class="sxs-lookup"><span data-stu-id="3c2b1-102">Receive Adapter Operations</span></span>
<span data-ttu-id="3c2b1-103">接收适配器可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3c2b1-103">Receive adapters can perform the following operations:</span></span>  

- <span data-ttu-id="3c2b1-104">**单向提交： void SubmitMessage (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="3c2b1-104">**One-way submit: void SubmitMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="3c2b1-105">后从接收端口接收消息，适配器将消息提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要处理的订阅业务流程或发送端口。</span><span class="sxs-lookup"><span data-stu-id="3c2b1-105">After receiving a message from a receive port, the adapter submits it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be processed by a subscribing orchestration or send port.</span></span>  

- <span data-ttu-id="3c2b1-106">**挂起： void MoveToSuspendQ (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="3c2b1-106">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="3c2b1-107">如果适配器确定了解析、 传输、 序列化或其他有关错误发生提交后，它会将消息移至挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="3c2b1-107">When the adapter determines a parsing, transmission, serialization, or other applicable failure has occurred after submission, it moves the message to the Suspended queue.</span></span>  

- <span data-ttu-id="3c2b1-108">**提交请求： void SubmitRequestMessage （IBaseMessage requestMsg，字符串 correlationToken，[marshalas （unmanagedtype.bool)] bool firstResponseOnly，DateTime expirationTime，IBTTransmitter responseCallback）。**</span><span class="sxs-lookup"><span data-stu-id="3c2b1-108">**Submit request: void SubmitRequestMessage(IBaseMessage requestMsg, string correlationToken, [MarshalAs(UnmanagedType.Bool)]bool firstResponseOnly, DateTime expirationTime, IBTTransmitter responseCallback).**</span></span> <span data-ttu-id="3c2b1-109">接收适配器将提交到传入消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请求-响应对中。</span><span class="sxs-lookup"><span data-stu-id="3c2b1-109">A receive adapter submits an incoming message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a request-response pair.</span></span> <span data-ttu-id="3c2b1-110">之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]成功处理此请求消息，它将发送到适配器以将其传输到特定终结点的响应。</span><span class="sxs-lookup"><span data-stu-id="3c2b1-110">After [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] successfully processes this request message, it sends the response to the adapter to transmit it to the specific endpoint.</span></span>
