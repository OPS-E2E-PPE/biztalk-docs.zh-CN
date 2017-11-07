---
title: "TIBCO 集合适配器 |Microsoft 文档"
description: "安装、 逐步调试教程，了解体系结构、 使用 SSO 安全、 创建你的应用程序、 导入绑定文件中，并为 TIBCO 会合 BizTalk Server 中使用 BizTalk 适配器时添加异常处理"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0528954d-11b4-449b-8057-30d463104fef
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b12b4c8382019372efca91b11eda4efa8e3f4b4a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="d128a-103">TIBCO 会合适配器</span><span class="sxs-lookup"><span data-stu-id="d128a-103">TIBCO Rendezvous Adapter</span></span>
<span data-ttu-id="d128a-104">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使您能够使用 BizTalk Server 内的 TIBCO Rendezvous 企业功能。</span><span class="sxs-lookup"><span data-stu-id="d128a-104">Microsoft BizTalk Adapter for TIBCO Rendezvous enables you to use TIBCO Rendezvous business functions within BizTalk Server.</span></span> <span data-ttu-id="d128a-105">以下部分介绍设置适配器以访问 TIBCO Rendezvous 特定信息。</span><span class="sxs-lookup"><span data-stu-id="d128a-105">The following sections discuss setting up the adapter to access TIBCO Rendezvous-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="d128a-106">要开始</span><span class="sxs-lookup"><span data-stu-id="d128a-106">Get started</span></span>
<span data-ttu-id="d128a-107">[要开始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)描述不同的消息和概念，并还提供在安装、 架构和限制的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d128a-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) describes the different messages and concepts, and also provides details on installation, schemas, and limitations.</span></span> <span data-ttu-id="d128a-108">单步执行一些教程，以接收和发送数据使用此适配器。</span><span class="sxs-lookup"><span data-stu-id="d128a-108">ALso step through some tutorials to receive and send data using this adapter.</span></span>

## <a name="architecture"></a><span data-ttu-id="d128a-109">体系结构</span><span class="sxs-lookup"><span data-stu-id="d128a-109">Architecture</span></span>
<span data-ttu-id="d128a-110">[体系结构](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)描述连接，以及将消息的传递方式。</span><span class="sxs-lookup"><span data-stu-id="d128a-110">[Architecture](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md) describes the connectivity, and how messages are passed.</span></span>

## <a name="security"></a><span data-ttu-id="d128a-111">安全性</span><span class="sxs-lookup"><span data-stu-id="d128a-111">Security</span></span>
<span data-ttu-id="d128a-112">[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="d128a-112">[Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-applications"></a><span data-ttu-id="d128a-113">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="d128a-113">Create applications</span></span>
<span data-ttu-id="d128a-114">[创建应用程序项目](../core/developing-applications1.md)说明如何添加接收和发送项目在 BizTalk 管理中，提供有关消息和数据类型映射和消息上下文属性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d128a-114">[Create application artifacts](../core/developing-applications1.md) shows you how to add the receive and send artifacts in BizTalk Administration, provides details on message and data type mapping, and message context properties.</span></span>

## <a name="importing-assemblies"></a><span data-ttu-id="d128a-115">导入程序集</span><span class="sxs-lookup"><span data-stu-id="d128a-115">Importing assemblies</span></span>
<span data-ttu-id="d128a-116">[端口和程序集导入](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md)讨论如何将应用程序绑定文件导入 BizTalk 管理。</span><span class="sxs-lookup"><span data-stu-id="d128a-116">[Import ports and assemblies](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md) discusses how to import your application binding file into BizTalk Administration.</span></span>

## <a name="handle-exceptions"></a><span data-ttu-id="d128a-117">处理异常</span><span class="sxs-lookup"><span data-stu-id="d128a-117">Handle exceptions</span></span>
<span data-ttu-id="d128a-118">[异常处理](../core/using-biztalk-server-exception-handling4.md)提供有关将不同的形状添加到您的业务流程来处理异常的指导。</span><span class="sxs-lookup"><span data-stu-id="d128a-118">[Exception handling](../core/using-biztalk-server-exception-handling4.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="d128a-119">故障排除</span><span class="sxs-lookup"><span data-stu-id="d128a-119">Troubleshoot</span></span>
<span data-ttu-id="d128a-120">[故障排除 TIBCO 会合](../core/troubleshooting-tibco-rendezvous.md)包含有关使用 Windows 事件跟踪详细信息。</span><span class="sxs-lookup"><span data-stu-id="d128a-120">[Troubleshooting TIBCO Rendezvous](../core/troubleshooting-tibco-rendezvous.md) includes details on using Event Tracing for Windows.</span></span>