---
title: PeopleSoft Enterprise 适配器 |Microsoft Docs
description: 安装、 单步执行教程，了解体系结构、 使用 SSO 安全、 创建您的应用程序、 导入绑定文件中，和使用适用于 BizTalk Server 中的 PeopleSoft Enterprise 的 BizTalk 适配器时添加异常处理
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c3dd7fd-3566-4063-a2fd-2acbe64d2885
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6963b6f5a291ee9086fdfb6f857dfcf93edf30fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291863"
---
# <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="1fd00-103">PeopleSoft Enterprise Adapter</span><span class="sxs-lookup"><span data-stu-id="1fd00-103">PeopleSoft Enterprise Adapter</span></span>
<span data-ttu-id="1fd00-104">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使您可以使用 BizTalk Server 应用程序中的 PeopleSoft 对象。</span><span class="sxs-lookup"><span data-stu-id="1fd00-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise enables you to use PeopleSoft objects within your BizTalk Server application.</span></span> <span data-ttu-id="1fd00-105">以下部分讨论设置适配器以访问特定于 PeopleSoft 的信息。</span><span class="sxs-lookup"><span data-stu-id="1fd00-105">The following sections discuss setting up the adapter to access PeopleSoft-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="1fd00-106">入门</span><span class="sxs-lookup"><span data-stu-id="1fd00-106">Get started</span></span>
<span data-ttu-id="1fd00-107">[开始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)列出了安装适配器，并单步执行一些教程的步骤。</span><span class="sxs-lookup"><span data-stu-id="1fd00-107">[Get started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="1fd00-108">体系结构</span><span class="sxs-lookup"><span data-stu-id="1fd00-108">Architecture</span></span>
<span data-ttu-id="1fd00-109">[体系结构](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md)描述的接口方法和验证与此适配器。</span><span class="sxs-lookup"><span data-stu-id="1fd00-109">[Architecture](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md) describes the interface methods, and validation with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="1fd00-110">安全性</span><span class="sxs-lookup"><span data-stu-id="1fd00-110">Security</span></span>
<span data-ttu-id="1fd00-111">[安全](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)中 BizTalk 服务器以保护应用程序使用此适配器，需使用企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="1fd00-111">[Security](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="1fd00-112">创建的项目</span><span class="sxs-lookup"><span data-stu-id="1fd00-112">Create the artifacts</span></span>
<span data-ttu-id="1fd00-113">[创建应用程序项目](../core/developing-applications4.md)演示如何将项目添加在 BizTalk 管理，并将架构添加到 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1fd00-113">[Create the application artifacts](../core/developing-applications4.md) shows you how to add the artifacts in BizTalk Administration, and add the schemas to Visual Studio.</span></span>

## <a name="import-apps"></a><span data-ttu-id="1fd00-114">导入应用</span><span class="sxs-lookup"><span data-stu-id="1fd00-114">Import apps</span></span>
<span data-ttu-id="1fd00-115">[导入绑定文件](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)讨论如何将应用程序的绑定文件导入到 BizTalk 管理和超过任何限制。</span><span class="sxs-lookup"><span data-stu-id="1fd00-115">[Importing binding file](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="1fd00-116">异常处理</span><span class="sxs-lookup"><span data-stu-id="1fd00-116">Exception handling</span></span>
<span data-ttu-id="1fd00-117">[使用异常处理](../core/using-biztalk-server-exception-handling2.md)将不同的形状添加到您的业务流程来处理异常提供指导。</span><span class="sxs-lookup"><span data-stu-id="1fd00-117">[Use Exception Handling](../core/using-biztalk-server-exception-handling2.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1fd00-118">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1fd00-118">Troubleshooting</span></span>
<span data-ttu-id="1fd00-119">[故障排除](../core/troubleshooting-peoplesoft.md)介绍一些常见的错误和情况下，并讨论了 Windows 的事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="1fd00-119">[Troubleshooting](../core/troubleshooting-peoplesoft.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="component-interfaces"></a><span data-ttu-id="1fd00-120">组件接口</span><span class="sxs-lookup"><span data-stu-id="1fd00-120">Component interfaces</span></span>
<span data-ttu-id="1fd00-121">[引用](../core/technical-reference-for-peoplesoft-enterprise.md)方法，提供详细信息，并生成 XML 来测试您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1fd00-121">[Reference](../core/technical-reference-for-peoplesoft-enterprise.md) provides details on the methods, and generating XML to test your orchestrations.</span></span>

## <a name="ui-guidance"></a><span data-ttu-id="1fd00-122">UI 指南</span><span class="sxs-lookup"><span data-stu-id="1fd00-122">UI guidance</span></span>
<span data-ttu-id="1fd00-123">[用户界面参考](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)提供对话框和向导使用此适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1fd00-123">[UI Reference](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 