---
title: "博士 Edwards EnterpriseOne 适配器 |Microsoft 文档"
description: "安装、 逐步调试教程，了解体系结构、 使用 SSO 安全、 创建你的应用程序、 导入绑定文件中，并为 J.D.使用 BizTalk 适配器时添加异常处理 BizTalk Server 中的 Edwards EnterpriseOne"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97f0f87a-59c3-4503-8da6-d6967dab820a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1d82cafd20e8c86fbbf7daa42304ecb95c9aee
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-enterpriseone-adapter"></a><span data-ttu-id="b01cc-104">博士 Edwards EnterpriseOne 适配器</span><span class="sxs-lookup"><span data-stu-id="b01cc-104">JD Edwards EnterpriseOne Adapter</span></span>
<span data-ttu-id="b01cc-105">Microsoft BizTalk Adapter for J.D.</span><span class="sxs-lookup"><span data-stu-id="b01cc-105">Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="b01cc-106">Edwards EnterpriseOne，可使用内 BizTalk Server 博士 Edwards EnterpriseOne 业务功能。</span><span class="sxs-lookup"><span data-stu-id="b01cc-106">Edwards EnterpriseOne enables you to use JD Edwards EnterpriseOne business functions within BizTalk Server.</span></span> <span data-ttu-id="b01cc-107">以下各节讨论设置该适配器访问博士 Edwards EnterpriseOne 特定信息。</span><span class="sxs-lookup"><span data-stu-id="b01cc-107">The following sections discuss setting up the adapter to access JD Edwards EnterpriseOne-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="b01cc-108">要开始</span><span class="sxs-lookup"><span data-stu-id="b01cc-108">Get started</span></span>
<span data-ttu-id="b01cc-109">[要开始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md)列出要安装适配器，并单步某些教程的步骤。</span><span class="sxs-lookup"><span data-stu-id="b01cc-109">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="b01cc-110">体系结构</span><span class="sxs-lookup"><span data-stu-id="b01cc-110">Architecture</span></span>
<span data-ttu-id="b01cc-111">[体系结构](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md)介绍设计时和运行时间元素的适配器。</span><span class="sxs-lookup"><span data-stu-id="b01cc-111">[Architecture](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md) describes the design time and run time elements of the adapter.</span></span>

## <a name="security"></a><span data-ttu-id="b01cc-112">安全性</span><span class="sxs-lookup"><span data-stu-id="b01cc-112">Security</span></span>
<span data-ttu-id="b01cc-113">[安全](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="b01cc-113">[Security](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="b01cc-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="b01cc-114">Create the artifacts</span></span>
<span data-ttu-id="b01cc-115">[创建应用程序项目](../core/developing-applications2.md)演示如何在 BizTalk 管理，和 Visual Studio 中添加项目。</span><span class="sxs-lookup"><span data-stu-id="b01cc-115">[Create the application artifacts](../core/developing-applications2.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="b01cc-116">它还演示如何在业务流程中使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b01cc-116">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="b01cc-117">导入你的应用程序</span><span class="sxs-lookup"><span data-stu-id="b01cc-117">Import your app</span></span>
<span data-ttu-id="b01cc-118">[部署应用程序](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)讨论如何将应用程序绑定文件导入 BizTalk 管理，并都要通过任何限制。</span><span class="sxs-lookup"><span data-stu-id="b01cc-118">[Deploying your application](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="b01cc-119">异常处理</span><span class="sxs-lookup"><span data-stu-id="b01cc-119">Exception handling</span></span>
<span data-ttu-id="b01cc-120">[BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)提供有关将不同的形状添加到您的业务流程来处理异常的指导。</span><span class="sxs-lookup"><span data-stu-id="b01cc-120">[BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling3.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b01cc-121">故障排除</span><span class="sxs-lookup"><span data-stu-id="b01cc-121">Troubleshooting</span></span>
<span data-ttu-id="b01cc-122">[解决适配器](../core/troubleshooting-jd-edwards-enterpriseone.md)介绍一些常见的错误和情况下，并讨论了 Windows 事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="b01cc-122">[Troubleshoot the adapter](../core/troubleshooting-jd-edwards-enterpriseone.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="reference"></a><span data-ttu-id="b01cc-123">参考</span><span class="sxs-lookup"><span data-stu-id="b01cc-123">Reference</span></span>
<span data-ttu-id="b01cc-124">[技术参考](../core/technical-reference6.md)包括示例文件和使用的此适配器的示例数据类型。</span><span class="sxs-lookup"><span data-stu-id="b01cc-124">[Technical reference](../core/technical-reference6.md) includes sample files and sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b01cc-125">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="b01cc-125">UI reference</span></span>
<span data-ttu-id="b01cc-126">[用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md)提供有关显示的对话框和向导使用此适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b01cc-126">[UI reference](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 