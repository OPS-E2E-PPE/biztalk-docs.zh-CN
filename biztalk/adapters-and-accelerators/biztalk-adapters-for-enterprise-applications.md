---
title: 企业应用程序适配器 |Microsoft 文档
description: Microsoft 企业应用程序的 BizTalk 适配器包括博士 Edwards EnterpriseOne，博士 Edwards OneWorld PeopleSoft 企业、 TIBCO 企业消息服务和 TIBCO 会合若要在 BizTalk Server 中使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1960a5a-d627-42ce-8898-5df444846fea
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c13bb1aecaadb3a943cf59ad6dcba06d6ed03f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24016132"
---
# <a name="enterprise-applications-adapters-in-biztalk-server"></a><span data-ttu-id="b7114-103">BizTalk Server 中的企业应用程序适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-103">Enterprise Applications adapters in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="b7114-104">概述</span><span class="sxs-lookup"><span data-stu-id="b7114-104">Overview</span></span>

<span data-ttu-id="b7114-105">Microsoft BizTalk Server 包括使企业应用程序能够与每个其他接口的适配器。</span><span class="sxs-lookup"><span data-stu-id="b7114-105">Microsoft BizTalk Server includes adapters that enable enterprise applications to interface with each other.</span></span> <span data-ttu-id="b7114-106">企业应用程序包括以下适配器：</span><span class="sxs-lookup"><span data-stu-id="b7114-106">The Enterprise Applications includes the following adapters:</span></span>  

* <span data-ttu-id="b7114-107">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="b7114-107">JD Edwards EnterpriseOne</span></span>
* <span data-ttu-id="b7114-108">博士 Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="b7114-108">JD Edwards OneWorld</span></span>
* <span data-ttu-id="b7114-109">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7114-109">PeopleSoft Enterprise</span></span>
* <span data-ttu-id="b7114-110">TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="b7114-110">TIBCO Enterprise Message Service</span></span>
* <span data-ttu-id="b7114-111">TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="b7114-111">TIBCO Rendezvous</span></span> 

<span data-ttu-id="b7114-112">使用这些适配器，可以连接到本地业务线 (LOB) 系统，以获取数据，然后将数据放。</span><span class="sxs-lookup"><span data-stu-id="b7114-112">Using these adapters, you can connect to these on-premises line-of-business (LOB) systems to get data, and put data.</span></span> 

## <a name="install"></a><span data-ttu-id="b7114-113">Install</span><span class="sxs-lookup"><span data-stu-id="b7114-113">Install</span></span>
<span data-ttu-id="b7114-114">BizTalk Server 中附带了企业应用程序适配器。</span><span class="sxs-lookup"><span data-stu-id="b7114-114">The Enterprise Applications adapters are included with BizTalk Server.</span></span> <span data-ttu-id="b7114-115">有关特定的安装步骤中，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b7114-115">For the specific installation steps, see:</span></span>

[<span data-ttu-id="b7114-116">安装和配置 Microsoft BizTalk 适配器为企业应用程序</span><span class="sxs-lookup"><span data-stu-id="b7114-116">Install and configure the Microsoft BizTalk Adapters for Enterprise Applications</span></span>](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)

## <a name="jd-edwards-enterpriseone-adapter"></a><span data-ttu-id="b7114-117">博士 Edwards EnterpriseOne 适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-117">JD Edwards EnterpriseOne adapter</span></span>

<span data-ttu-id="b7114-118">[Microsoft BizTalk Adapter for 博士 Edwards EnterpriseOne](../core/jd-edwards-enterpriseone-adapter.md)包括的教程，若要开始，在运行的时和设计时，使用 SSO 保护你的应用程序，并使用一个业务流程中的消息上下文属性中描述的体系结构.</span><span class="sxs-lookup"><span data-stu-id="b7114-118">[Microsoft BizTalk Adapter for JD Edwards EnterpriseOne](../core/jd-edwards-enterpriseone-adapter.md) includes a tutorial to get started, describes the architecture at run time and design time, using SSO to secure your applications, and using message context properties within an orchestration.</span></span> <span data-ttu-id="b7114-119">使用绑定文件，异常处理和故障排除适配器还会涉及。</span><span class="sxs-lookup"><span data-stu-id="b7114-119">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="b7114-120">博士 Edwards OneWorld 适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-120">JD Edwards OneWorld adapter</span></span>

<span data-ttu-id="b7114-121">[Microsoft BizTalk Adapter for 博士 Edwards OneWorld](../core/jd-edwards-oneworld-adapter.md)包括入门的教程，介绍体系结构和限制，使用 SSO 保护你的应用程序，并使用一个业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b7114-121">[Microsoft BizTalk Adapter for JD Edwards OneWorld](../core/jd-edwards-oneworld-adapter.md) includes a tutorial to get started, describes the architecture and limitations, using SSO to secure your applications, and using message context properties within an orchestration.</span></span> <span data-ttu-id="b7114-122">使用绑定文件，异常处理和故障排除适配器还会涉及。</span><span class="sxs-lookup"><span data-stu-id="b7114-122">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="b7114-123">PeopleSoft Enterprise 适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-123">PeopleSoft Enterprise adapter</span></span>

<span data-ttu-id="b7114-124">[Microsoft BizTalk Adapter for PeopleSoft 企业](../core/peoplesoft-enterprise-adapter.md)包括几个教程，若要开始数据、 介绍体系结构和限制，使用 SSO 来保护你的应用程序，并将发送和接收 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="b7114-124">[Microsoft BizTalk Adapter for PeopleSoft Enterprise](../core/peoplesoft-enterprise-adapter.md) includes several tutorials to get started, describes the architecture and limitations, using SSO to secure your applications, and sending and receive with PeopleSoft.</span></span> <span data-ttu-id="b7114-125">使用绑定文件，异常处理和故障排除适配器还会涉及。</span><span class="sxs-lookup"><span data-stu-id="b7114-125">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="b7114-126">TIBCO 企业消息服务适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-126">TIBCO Enterprise Message Service adapter</span></span>

<span data-ttu-id="b7114-127">[Microsoft BizTalk Adapter for TIBCO 企业消息服务](../core/tibco-enterprise-message-service-adapter.md)包括几个教程，若要开始，描述体系结构和限制，并使用 SSO 来保护你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7114-127">[Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-adapter.md) includes several tutorials to get started, describes the architecture and limitations, and using SSO to secure your applications.</span></span> <span data-ttu-id="b7114-128">此外介绍异常处理和故障排除适配器。</span><span class="sxs-lookup"><span data-stu-id="b7114-128">Exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="b7114-129">TIBCO 会合适配器</span><span class="sxs-lookup"><span data-stu-id="b7114-129">TIBCO Rendezvous adapter</span></span>
<span data-ttu-id="b7114-130">[Microsoft BizTalk Adapter for TIBCO 会合](../core/tibco-rendezvous-adapter.md)包括几个教程，若要开始数据、 介绍体系结构和限制，使用 SSO 来保护你的应用程序，并将发送和接收 TIBCO。</span><span class="sxs-lookup"><span data-stu-id="b7114-130">[Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tibco-rendezvous-adapter.md) includes several tutorials to get started, describes the architecture and limitations, using SSO to secure your applications, and sending and receive with TIBCO.</span></span> <span data-ttu-id="b7114-131">此外介绍异常处理和故障排除适配器。</span><span class="sxs-lookup"><span data-stu-id="b7114-131">Exception handling, and troubleshooting the adapter are also covered.</span></span> 

