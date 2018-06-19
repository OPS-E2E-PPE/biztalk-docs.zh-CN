---
title: 博士 Edwards OneWorld 适配器 |Microsoft 文档
description: 安装、 逐步调试教程，了解体系结构、 使用 SSO 安全、 创建你的应用程序、 导入绑定文件中，并为 J.D.使用 BizTalk 适配器时添加异常处理 BizTalk Server 中的 Edwards OneWorld
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5df8cd89-d9df-41ca-9a2c-b9d7fbcd06f2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bde93503bff679faf2717edefb386aa2f43fc3e
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015926"
---
# <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="703c7-104">JD Edwards OneWorld 适配器</span><span class="sxs-lookup"><span data-stu-id="703c7-104">JD Edwards OneWorld Adapter</span></span>
<span data-ttu-id="703c7-105">通过用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，可以在 BizTalk Server 中使用 JD Edwards OneWorld 业务功能。</span><span class="sxs-lookup"><span data-stu-id="703c7-105">Microsoft BizTalk Adapter for JD Edwards OneWorld enables you to use JD Edwards OneWorld business functions within BizTalk Server.</span></span> <span data-ttu-id="703c7-106">以下部分讨论设置用于 JD Edwards OneWorld 的 BizTalk 适配器，以访问特定于 JD Edwards OneWorld 的信息。</span><span class="sxs-lookup"><span data-stu-id="703c7-106">The following sections discuss setting up BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="703c7-107">要开始</span><span class="sxs-lookup"><span data-stu-id="703c7-107">Get started</span></span> 
<span data-ttu-id="703c7-108">[要开始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)列出要安装适配器，并单步教程的步骤。</span><span class="sxs-lookup"><span data-stu-id="703c7-108">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md) lists the steps to install the adapter, and step through a tutorial.</span></span>

## <a name="architecture"></a><span data-ttu-id="703c7-109">体系结构</span><span class="sxs-lookup"><span data-stu-id="703c7-109">Architecture</span></span>
<span data-ttu-id="703c7-110">[体系结构](../core/planning-and-architecture17.md)详细说明了适配器的工作原理，如何实例和函数建立池连接在设计时和运行的时，限制时查询和检索列出，并且使用了此适配器的多订单项。</span><span class="sxs-lookup"><span data-stu-id="703c7-110">[Architecture](../core/planning-and-architecture17.md) details how the adapter works, how instances and functions are pooled at design time and run time, limitations when  querying and retrieving lists, and using multi-order items with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="703c7-111">安全性</span><span class="sxs-lookup"><span data-stu-id="703c7-111">Security</span></span>
<span data-ttu-id="703c7-112">[用于博士 Edwards OneWorld 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="703c7-112">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="703c7-113">创建项目</span><span class="sxs-lookup"><span data-stu-id="703c7-113">Create the artifacts</span></span>
<span data-ttu-id="703c7-114">[创建应用程序项目](../core/developing-applications3.md)演示如何在 BizTalk 管理，和 Visual Studio 中添加项目。</span><span class="sxs-lookup"><span data-stu-id="703c7-114">[Create the application artifacts](../core/developing-applications3.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="703c7-115">它还演示如何在业务流程中使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="703c7-115">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="703c7-116">导入你的应用程序</span><span class="sxs-lookup"><span data-stu-id="703c7-116">Import your app</span></span>
<span data-ttu-id="703c7-117">[为博士 Edwards OneWorld 部署的 BizTalk Adapter](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)讨论如何将应用程序绑定文件导入 BizTalk 管理并超过限制。</span><span class="sxs-lookup"><span data-stu-id="703c7-117">[Deploying BizTalk Adapter for JD Edwards OneWorld](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md) discusses how to import your application binding file into BizTalk Administration, and goes over the limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="703c7-118">异常处理</span><span class="sxs-lookup"><span data-stu-id="703c7-118">Exception handling</span></span> 
<span data-ttu-id="703c7-119">[BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)提供有关更新 jdearglist.txt 文件，并将不同的形状添加到您的业务流程来处理异常的指导。</span><span class="sxs-lookup"><span data-stu-id="703c7-119">[BizTalk Server exception handling](../core/using-biztalk-server-exception-handling1.md) provides guidance on updating the jdearglist.txt file, and adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="703c7-120">故障排除</span><span class="sxs-lookup"><span data-stu-id="703c7-120">Troubleshooting</span></span>
<span data-ttu-id="703c7-121">[故障排除](../core/troubleshooting-jd-edwards-oneworld.md)介绍一些常见的错误和情况下，并讨论了 Windows 事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="703c7-121">[Troubleshooting](../core/troubleshooting-jd-edwards-oneworld.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="data-types"></a><span data-ttu-id="703c7-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="703c7-122">Data Types</span></span>
<span data-ttu-id="703c7-123">[附录： 数据类型](../core/appendix-a-data-types.md)列出此适配器使用的示例数据类型。</span><span class="sxs-lookup"><span data-stu-id="703c7-123">[Appendix: Data Types](../core/appendix-a-data-types.md) lists the sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="703c7-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="703c7-124">UI reference</span></span>
<span data-ttu-id="703c7-125">[用于 JDE OneWorld 的 BizTalk Adapter 的用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)提供有关显示的对话框和向导使用此适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="703c7-125">[UI Reference for BizTalk Adapter for JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 