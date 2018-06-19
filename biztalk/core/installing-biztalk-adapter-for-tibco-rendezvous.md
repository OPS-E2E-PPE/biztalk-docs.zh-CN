---
title: 安装、 架构和限制 TIBCO 会合适配器 |Microsoft 文档
description: 安装架构生成的、 和限制的 BizTalk Adapter TIBCO 会合 BizTalk Server 中
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a158d4f627a553a87f0bc8fa08333a5864bb884
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013596"
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="0f81c-103">安装、 架构和 TIBCO 会合适配器的限制</span><span class="sxs-lookup"><span data-stu-id="0f81c-103">Install, schemas, and limitations of the TIBCO Rendezvous adapter</span></span>

## <a name="install-and-setup"></a><span data-ttu-id="0f81c-104">安装和设置</span><span class="sxs-lookup"><span data-stu-id="0f81c-104">Install and setup</span></span>

<span data-ttu-id="0f81c-105">[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)包括了步骤来安装企业适配器，并还包括密钥信息以了解安装适配器之前, 和之后安装适配器。</span><span class="sxs-lookup"><span data-stu-id="0f81c-105">[Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) includes the steps to install the enterprise adapters, and also includes key information to know before you install the adapter, and after you install the adapter.</span></span> 

## <a name="generate-schemas"></a><span data-ttu-id="0f81c-106">生成架构</span><span class="sxs-lookup"><span data-stu-id="0f81c-106">Generate schemas</span></span>
<span data-ttu-id="0f81c-107">TIBCO Rendezvous 系统中没有消息类型存储库。</span><span class="sxs-lookup"><span data-stu-id="0f81c-107">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="0f81c-108">所有消息构造和解析都在 Rendezvous 应用程序级别隐藏了。</span><span class="sxs-lookup"><span data-stu-id="0f81c-108">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="0f81c-109">鉴于此限制，适配器不能提供架构生成功能。</span><span class="sxs-lookup"><span data-stu-id="0f81c-109">Because of this limitation, adapter cannot provide schema-generation capabilities.</span></span>  
  
<span data-ttu-id="0f81c-110">你必须编写架构，并使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="0f81c-110">You must write a schema, and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="0f81c-111">架构对于 BizTalk Server 开发工具和 Visual Studio 中的集成都非常重要。</span><span class="sxs-lookup"><span data-stu-id="0f81c-111">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="0f81c-112">BizTalk Server 开发人员可以选择提供完整架构、最低限要求的架构，或介于二者之间的版本。</span><span class="sxs-lookup"><span data-stu-id="0f81c-112">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  

## <a name="limitations"></a><span data-ttu-id="0f81c-113">限制</span><span class="sxs-lookup"><span data-stu-id="0f81c-113">Limitations</span></span>

- <span data-ttu-id="0f81c-114">不保证字段名称的唯一性。</span><span class="sxs-lookup"><span data-stu-id="0f81c-114">Field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="0f81c-115">如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。</span><span class="sxs-lookup"><span data-stu-id="0f81c-115">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
-   <span data-ttu-id="0f81c-116">未提供字段排序功能。</span><span class="sxs-lookup"><span data-stu-id="0f81c-116">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="0f81c-117">根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。</span><span class="sxs-lookup"><span data-stu-id="0f81c-117">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="0f81c-118">用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="0f81c-118">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="0f81c-119">不支持与后台程序的安全连接。</span><span class="sxs-lookup"><span data-stu-id="0f81c-119">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="0f81c-120">不支持自定义数据类型。</span><span class="sxs-lookup"><span data-stu-id="0f81c-120">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="0f81c-121">传输端不支持经过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="0f81c-121">Certified Messaging is not supported on the transmit side.</span></span>  
-   
## <a name="next-step"></a><span data-ttu-id="0f81c-122">下一步</span><span class="sxs-lookup"><span data-stu-id="0f81c-122">Next step</span></span>

[<span data-ttu-id="0f81c-123">教程：使用适用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0f81c-123">Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  