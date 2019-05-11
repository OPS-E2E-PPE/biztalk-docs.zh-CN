---
title: TIBCO Rendezvous 适配器 |Microsoft Docs
description: 安装、 单步执行教程，了解体系结构、 使用 SSO 安全性、 创建您的应用程序、 导入绑定文件中，和使用 BizTalk Server 中的 TIBCO Rendezvous 的 BizTalk 适配器时添加异常处理
ms.custom: ''
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0528954d-11b4-449b-8057-30d463104fef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 437d0ba281a724b47b8ccfb7c15846d4cfaa8bb8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379811"
---
# <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="942c0-103">TIBCO Rendezvous Adapter</span><span class="sxs-lookup"><span data-stu-id="942c0-103">TIBCO Rendezvous Adapter</span></span>
<span data-ttu-id="942c0-104">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器，可使用 BizTalk Server 内的 TIBCO Rendezvous 企业功能。</span><span class="sxs-lookup"><span data-stu-id="942c0-104">Microsoft BizTalk Adapter for TIBCO Rendezvous enables you to use TIBCO Rendezvous business functions within BizTalk Server.</span></span> <span data-ttu-id="942c0-105">以下部分讨论设置适配器以访问 TIBCO Rendezvous 特定信息。</span><span class="sxs-lookup"><span data-stu-id="942c0-105">The following sections discuss setting up the adapter to access TIBCO Rendezvous-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="942c0-106">入门</span><span class="sxs-lookup"><span data-stu-id="942c0-106">Get started</span></span>
<span data-ttu-id="942c0-107">[开始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)介绍不同的消息和概念，并还详细介绍安装、 架构和限制。</span><span class="sxs-lookup"><span data-stu-id="942c0-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) describes the different messages and concepts, and also provides details on installation, schemas, and limitations.</span></span> <span data-ttu-id="942c0-108">单步执行一些教程来接收和发送数据使用此适配器。</span><span class="sxs-lookup"><span data-stu-id="942c0-108">ALso step through some tutorials to receive and send data using this adapter.</span></span>

## <a name="architecture"></a><span data-ttu-id="942c0-109">体系结构</span><span class="sxs-lookup"><span data-stu-id="942c0-109">Architecture</span></span>
<span data-ttu-id="942c0-110">[体系结构](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)介绍连接，以及如何传递消息。</span><span class="sxs-lookup"><span data-stu-id="942c0-110">[Architecture](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md) describes the connectivity, and how messages are passed.</span></span>

## <a name="security"></a><span data-ttu-id="942c0-111">安全性</span><span class="sxs-lookup"><span data-stu-id="942c0-111">Security</span></span>
<span data-ttu-id="942c0-112">[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)中 BizTalk 服务器以保护应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="942c0-112">[Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-applications"></a><span data-ttu-id="942c0-113">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="942c0-113">Create applications</span></span>
<span data-ttu-id="942c0-114">[创建应用程序项目](../core/developing-applications1.md)说明如何添加接收和发送 BizTalk 管理在项目中，提供有关消息和数据类型映射和消息上下文属性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="942c0-114">[Create application artifacts](../core/developing-applications1.md) shows you how to add the receive and send artifacts in BizTalk Administration, provides details on message and data type mapping, and message context properties.</span></span>

## <a name="importing-assemblies"></a><span data-ttu-id="942c0-115">导入程序集</span><span class="sxs-lookup"><span data-stu-id="942c0-115">Importing assemblies</span></span>
<span data-ttu-id="942c0-116">[导入端口和程序集](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md)讨论如何将应用程序的绑定文件导入到 BizTalk 管理。</span><span class="sxs-lookup"><span data-stu-id="942c0-116">[Import ports and assemblies](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md) discusses how to import your application binding file into BizTalk Administration.</span></span>

## <a name="handle-exceptions"></a><span data-ttu-id="942c0-117">处理异常</span><span class="sxs-lookup"><span data-stu-id="942c0-117">Handle exceptions</span></span>
<span data-ttu-id="942c0-118">[异常处理](../core/using-biztalk-server-exception-handling4.md)将不同的形状添加到您的业务流程来处理异常提供指导。</span><span class="sxs-lookup"><span data-stu-id="942c0-118">[Exception handling](../core/using-biztalk-server-exception-handling4.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="942c0-119">故障排除</span><span class="sxs-lookup"><span data-stu-id="942c0-119">Troubleshoot</span></span>
<span data-ttu-id="942c0-120">[TIBCO Rendezvous 疑难解答](../core/troubleshooting-tibco-rendezvous.md)包括使用 Windows 的事件跟踪的详细信息。</span><span class="sxs-lookup"><span data-stu-id="942c0-120">[Troubleshooting TIBCO Rendezvous](../core/troubleshooting-tibco-rendezvous.md) includes details on using Event Tracing for Windows.</span></span>