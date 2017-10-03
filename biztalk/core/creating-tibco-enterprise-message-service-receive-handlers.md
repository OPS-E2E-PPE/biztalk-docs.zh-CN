---
title: "创建 TIBCO 企业消息服务接收处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive handlers
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83163701f897b782d577351cd08b3f2650ae6fb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-tibco-enterprise-message-service-receive-handlers"></a><span data-ttu-id="30753-102">创建 TIBCO Enterprise Message Service 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="30753-102">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>
<span data-ttu-id="30753-103">TIBCO Enterprise Message Service 接收器是一种侦听服务，可以注册特殊的队列或主题，并接收相关消息。</span><span class="sxs-lookup"><span data-stu-id="30753-103">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="30753-104">TIBCO Enterprise Message Service 的 BizTalk 适配器首先通过打开一个新会话向 TIBCO Enterprise Message Service 注册，然后继续轮询以接收消息。</span><span class="sxs-lookup"><span data-stu-id="30753-104">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="30753-105">该部分介绍了如何设置接收端口以连接到 TIBCO Enterprise Message Service，如何在您的业务流程中加入 XML 以在运行时与 TIBCO EMS 进行交互。</span><span class="sxs-lookup"><span data-stu-id="30753-105">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30753-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="30753-106">In This Section</span></span>  
  
-   [<span data-ttu-id="30753-107">如何创建在 TIBCO 企业消息服务接收端口</span><span class="sxs-lookup"><span data-stu-id="30753-107">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>](../core/how-to-create-receive-ports-in-tibco-enterprise-message-service.md)  
  
-   [<span data-ttu-id="30753-108">设置 TIBCO 企业消息服务传输属性接收端口</span><span class="sxs-lookup"><span data-stu-id="30753-108">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)  
  
-   [<span data-ttu-id="30753-109">如何设置 TIBCO 企业消息服务接收管道</span><span class="sxs-lookup"><span data-stu-id="30753-109">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)