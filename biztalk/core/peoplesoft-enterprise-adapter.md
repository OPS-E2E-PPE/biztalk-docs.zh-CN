---
title: "PeopleSoft Enterprise 适配器 |Microsoft 文档"
description: "安装、 单步执行教程，了解体系结构、 使用 SSO 安全性，创建你的应用程序、 导入绑定文件中，和 PeopleSoft 企业 BizTalk Server 中使用 BizTalk 适配器时添加异常处理"
ms.custom: 
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c3dd7fd-3566-4063-a2fd-2acbe64d2885
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a3bedda77a7bc45153cda79bd8c011b8628c26b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="e7957-103">PeopleSoft Enterprise 适配器</span><span class="sxs-lookup"><span data-stu-id="e7957-103">PeopleSoft Enterprise Adapter</span></span>
<span data-ttu-id="e7957-104">Microsoft BizTalk Adapter for PeopleSoft 企业可以使用 PeopleSoft BizTalk Server 应用程序中的对象。</span><span class="sxs-lookup"><span data-stu-id="e7957-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise enables you to use PeopleSoft objects within your BizTalk Server application.</span></span> <span data-ttu-id="e7957-105">以下各节讨论设置该适配器访问 PeopleSoft 特定信息。</span><span class="sxs-lookup"><span data-stu-id="e7957-105">The following sections discuss setting up the adapter to access PeopleSoft-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="e7957-106">要开始</span><span class="sxs-lookup"><span data-stu-id="e7957-106">Get started</span></span>
<span data-ttu-id="e7957-107">[要开始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)列出要安装适配器，并单步某些教程的步骤。</span><span class="sxs-lookup"><span data-stu-id="e7957-107">[Get started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="e7957-108">体系结构</span><span class="sxs-lookup"><span data-stu-id="e7957-108">Architecture</span></span>
<span data-ttu-id="e7957-109">[体系结构](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md)描述的接口方法和验证与此适配器。</span><span class="sxs-lookup"><span data-stu-id="e7957-109">[Architecture](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md) describes the interface methods, and validation with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="e7957-110">安全性</span><span class="sxs-lookup"><span data-stu-id="e7957-110">Security</span></span>
<span data-ttu-id="e7957-111">[安全](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="e7957-111">[Security](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="e7957-112">创建项目</span><span class="sxs-lookup"><span data-stu-id="e7957-112">Create the artifacts</span></span>
<span data-ttu-id="e7957-113">[创建应用程序项目](../core/developing-applications4.md)演示如何将项目添加在 BizTalk 管理，并将架构添加到 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e7957-113">[Create the application artifacts](../core/developing-applications4.md) shows you how to add the artifacts in BizTalk Administration, and add the schemas to Visual Studio.</span></span>

## <a name="import-apps"></a><span data-ttu-id="e7957-114">导入应用</span><span class="sxs-lookup"><span data-stu-id="e7957-114">Import apps</span></span>
<span data-ttu-id="e7957-115">[导入绑定文件](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)讨论如何将应用程序绑定文件导入 BizTalk 管理，并都要通过任何限制。</span><span class="sxs-lookup"><span data-stu-id="e7957-115">[Importing binding file](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="e7957-116">异常处理</span><span class="sxs-lookup"><span data-stu-id="e7957-116">Exception handling</span></span>
<span data-ttu-id="e7957-117">[使用异常处理，](../core/using-biztalk-server-exception-handling2.md)提供有关将不同的形状添加到您的业务流程来处理异常的指导。</span><span class="sxs-lookup"><span data-stu-id="e7957-117">[Use Exception Handling](../core/using-biztalk-server-exception-handling2.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e7957-118">故障排除</span><span class="sxs-lookup"><span data-stu-id="e7957-118">Troubleshooting</span></span>
<span data-ttu-id="e7957-119">[故障排除](../core/troubleshooting-peoplesoft.md)介绍一些常见的错误和情况下，并讨论了 Windows 事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="e7957-119">[Troubleshooting](../core/troubleshooting-peoplesoft.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="component-interfaces"></a><span data-ttu-id="e7957-120">组件接口</span><span class="sxs-lookup"><span data-stu-id="e7957-120">Component interfaces</span></span>
<span data-ttu-id="e7957-121">[引用](../core/technical-reference-for-peoplesoft-enterprise.md)的方法，提供详细信息和生成的 XML，以测试你的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e7957-121">[Reference](../core/technical-reference-for-peoplesoft-enterprise.md) provides details on the methods, and generating XML to test your orchestrations.</span></span>

## <a name="ui-guidance"></a><span data-ttu-id="e7957-122">用户界面指南</span><span class="sxs-lookup"><span data-stu-id="e7957-122">UI guidance</span></span>
<span data-ttu-id="e7957-123">[用户界面参考](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)提供有关显示的对话框和向导使用此适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e7957-123">[UI Reference](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 