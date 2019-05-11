---
title: JD Edwards OneWorld 适配器 |Microsoft Docs
description: 安装、 单步执行教程，了解体系结构、 使用 SSO 安全性、 创建您的应用程序、 导入绑定文件中，和使用用于 J.D.的 BizTalk 适配器时添加异常处理 在 BizTalk Server 中的 Edwards OneWorld
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
ms.openlocfilehash: 1ef563da19f04c940aa7f02f700f3b38fa79b1ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380787"
---
# <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="e9560-104">JD Edwards OneWorld Adapter</span><span class="sxs-lookup"><span data-stu-id="e9560-104">JD Edwards OneWorld Adapter</span></span>
<span data-ttu-id="e9560-105">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，可使用 BizTalk Server 中的 JD Edwards OneWorld 业务功能。</span><span class="sxs-lookup"><span data-stu-id="e9560-105">Microsoft BizTalk Adapter for JD Edwards OneWorld enables you to use JD Edwards OneWorld business functions within BizTalk Server.</span></span> <span data-ttu-id="e9560-106">以下部分介绍访问特定于 JD Edwards OneWorld 的信息适用于 JD Edwards OneWorld 设置 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="e9560-106">The following sections discuss setting up BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="e9560-107">入门</span><span class="sxs-lookup"><span data-stu-id="e9560-107">Get started</span></span> 
<span data-ttu-id="e9560-108">[开始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)列出了安装适配器，并单步执行本教程的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9560-108">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md) lists the steps to install the adapter, and step through a tutorial.</span></span>

## <a name="architecture"></a><span data-ttu-id="e9560-109">体系结构</span><span class="sxs-lookup"><span data-stu-id="e9560-109">Architecture</span></span>
<span data-ttu-id="e9560-110">[体系结构](../core/planning-and-architecture17.md)详细介绍该适配器的工作原理，如何实例和函数共用在设计时和运行的时，限制时查询和检索列表，并使用此适配器使用 multi-order 项。</span><span class="sxs-lookup"><span data-stu-id="e9560-110">[Architecture](../core/planning-and-architecture17.md) details how the adapter works, how instances and functions are pooled at design time and run time, limitations when  querying and retrieving lists, and using multi-order items with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="e9560-111">安全性</span><span class="sxs-lookup"><span data-stu-id="e9560-111">Security</span></span>
<span data-ttu-id="e9560-112">[用于 JD Edwards OneWorld 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)中 BizTalk 服务器以保护应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="e9560-112">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="e9560-113">创建的项目</span><span class="sxs-lookup"><span data-stu-id="e9560-113">Create the artifacts</span></span>
<span data-ttu-id="e9560-114">[创建应用程序项目](../core/developing-applications3.md)演示如何在 BizTalk 管理，并在 Visual Studio 中添加项目。</span><span class="sxs-lookup"><span data-stu-id="e9560-114">[Create the application artifacts](../core/developing-applications3.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="e9560-115">它还演示如何在业务流程中使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e9560-115">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="e9560-116">导入您的应用程序</span><span class="sxs-lookup"><span data-stu-id="e9560-116">Import your app</span></span>
<span data-ttu-id="e9560-117">[部署用于 JD Edwards OneWorld 的 BizTalk 适配器](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)讨论了如何将应用程序的绑定文件导入到 BizTalk 管理并超过限制。</span><span class="sxs-lookup"><span data-stu-id="e9560-117">[Deploying BizTalk Adapter for JD Edwards OneWorld](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md) discusses how to import your application binding file into BizTalk Administration, and goes over the limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="e9560-118">异常处理</span><span class="sxs-lookup"><span data-stu-id="e9560-118">Exception handling</span></span> 
<span data-ttu-id="e9560-119">[BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)指导更新 jdearglist.txt 文件中，并将不同的形状添加到您的业务流程来处理异常。</span><span class="sxs-lookup"><span data-stu-id="e9560-119">[BizTalk Server exception handling](../core/using-biztalk-server-exception-handling1.md) provides guidance on updating the jdearglist.txt file, and adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e9560-120">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e9560-120">Troubleshooting</span></span>
<span data-ttu-id="e9560-121">[故障排除](../core/troubleshooting-jd-edwards-oneworld.md)介绍一些常见的错误和情况下，并讨论了 Windows 的事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="e9560-121">[Troubleshooting](../core/troubleshooting-jd-edwards-oneworld.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="data-types"></a><span data-ttu-id="e9560-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="e9560-122">Data Types</span></span>
<span data-ttu-id="e9560-123">[附录：数据类型](../core/appendix-a-data-types.md)列出了使用此适配器的示例数据类型。</span><span class="sxs-lookup"><span data-stu-id="e9560-123">[Appendix: Data Types](../core/appendix-a-data-types.md) lists the sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e9560-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="e9560-124">UI reference</span></span>
<span data-ttu-id="e9560-125">[用于 JDE OneWorld 的 BizTalk 适配器用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)提供对话框和向导使用此适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9560-125">[UI Reference for BizTalk Adapter for JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 