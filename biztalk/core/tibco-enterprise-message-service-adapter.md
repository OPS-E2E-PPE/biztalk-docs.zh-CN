---
title: "TIBCO Enterprise 消息服务适配器 |Microsoft 文档"
description: "安装、 逐步调试教程，了解体系结构、 使用 SSO 安全、 创建你的应用程序、 导入绑定文件中，并为 TIBCO EMS BizTalk Server 中使用 BizTalk 适配器时添加异常处理"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 362556d2-295c-4496-a429-ad7ecc44db76
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c7993dd407cb90e267e713a3195f897de9ceb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="05bf1-103">TIBCO Enterprise Message Service 适配器</span><span class="sxs-lookup"><span data-stu-id="05bf1-103">TIBCO Enterprise Message Service Adapter</span></span>
<span data-ttu-id="05bf1-104">Microsoft BizTalk Adapter for TIBCO 企业消息服务使你可以发布和订阅队列和主题使用 btsBizTalkServerNoVersion TIBCO EMS 由管理。</span><span class="sxs-lookup"><span data-stu-id="05bf1-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service enables you to publish and subscribe to queues and topics managed by TIBCO EMS using btsBizTalkServerNoVersion.</span></span>  <span data-ttu-id="05bf1-105">以下各节讨论入门、 创建应用程序，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="05bf1-105">The following sections discuss getting started, creating applications, and more.</span></span>  
   
## <a name="get-started"></a><span data-ttu-id="05bf1-106">要开始</span><span class="sxs-lookup"><span data-stu-id="05bf1-106">Get started</span></span>
<span data-ttu-id="05bf1-107">[要开始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)描述适配器功能，安装适配器，并包含一些教程。</span><span class="sxs-lookup"><span data-stu-id="05bf1-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md) describes adapter features, installing the adapter, and includes some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="05bf1-108">体系结构</span><span class="sxs-lookup"><span data-stu-id="05bf1-108">Architecture</span></span>
<span data-ttu-id="05bf1-109">[体系结构](../core/planning-and-architecture16.md)描述适配器工作原理，提供一些其他的要求，以及列出的任何限制。</span><span class="sxs-lookup"><span data-stu-id="05bf1-109">[Architecture](../core/planning-and-architecture16.md) describes how the adapter works, provides some additional requirements, and lists any limitations.</span></span>

## <a name="security"></a><span data-ttu-id="05bf1-110">安全性</span><span class="sxs-lookup"><span data-stu-id="05bf1-110">Security</span></span>
<span data-ttu-id="05bf1-111">[安全](../core/security-in-biztalk-adapter-for-tibco-ems.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="05bf1-111">[Security](../core/security-in-biztalk-adapter-for-tibco-ems.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="05bf1-112">创建项目</span><span class="sxs-lookup"><span data-stu-id="05bf1-112">Create the artifacts</span></span>
<span data-ttu-id="05bf1-113">[创建应用程序项目](../core/developing-applications5.md)列出的步骤生成架构、 创建发送和接收使用此适配器，以及如何使用消息上下文属性中业务流程的项目。</span><span class="sxs-lookup"><span data-stu-id="05bf1-113">[Create the application artifacts](../core/developing-applications5.md) lists the steps to generate schemas, create the send and receive artifacts used by this adapter, and how to use the message context properties within an orchestration.</span></span>

## <a name="import-apps"></a><span data-ttu-id="05bf1-114">导入应用</span><span class="sxs-lookup"><span data-stu-id="05bf1-114">Import apps</span></span>
<span data-ttu-id="05bf1-115">[导入的绑定](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md)讨论如何将应用程序绑定文件导入 BizTalk 管理，并都要通过任何限制。</span><span class="sxs-lookup"><span data-stu-id="05bf1-115">[Import bindings](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="handle-exceptions"></a><span data-ttu-id="05bf1-116">处理异常</span><span class="sxs-lookup"><span data-stu-id="05bf1-116">Handle exceptions</span></span>
<span data-ttu-id="05bf1-117">[使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling5.md)提供有关将不同的形状添加到您的业务流程来处理异常的指导。</span><span class="sxs-lookup"><span data-stu-id="05bf1-117">[Use BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling5.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="05bf1-118">故障排除</span><span class="sxs-lookup"><span data-stu-id="05bf1-118">Troubleshooting</span></span>
 <span data-ttu-id="05bf1-119">[故障排除](../core/troubleshooting-tibco-enterprise-message-service.md)介绍一些常见的错误和情况下，并讨论了 Windows 事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="05bf1-119">[Troubleshooting](../core/troubleshooting-tibco-enterprise-message-service.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>