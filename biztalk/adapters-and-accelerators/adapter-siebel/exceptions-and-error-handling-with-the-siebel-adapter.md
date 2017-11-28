---
title: "异常和错误处理，并在 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 743e2a0f03e35282c24a506ff37e9d774f0b7505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a><span data-ttu-id="cb010-102">异常和错误处理，并在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="cb010-102">Exceptions and Error Handling with the Siebel adapter</span></span>
## <a name="exception-list"></a><span data-ttu-id="cb010-103">异常列表</span><span class="sxs-lookup"><span data-stu-id="cb010-103">Exception list</span></span>
<span data-ttu-id="cb010-104">引发的异常[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cb010-104">The exceptions thrown by the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="cb010-105">这些可以包含：</span><span class="sxs-lookup"><span data-stu-id="cb010-105">These can contain:</span></span>  
  
-   <span data-ttu-id="cb010-106">内部异常，这是.NET Framework 引发系统异常</span><span class="sxs-lookup"><span data-stu-id="cb010-106">An inner exception, which is a system exception that the .NET Framework throws</span></span>  
  
-   <span data-ttu-id="cb010-107">LOB 客户端库引发的 LOB 异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-107">An LOB exception that the LOB client library throws.</span></span>  
  
 <span data-ttu-id="cb010-108">有关内部异常的详细信息，请参阅相应的.NET Framework 或 Siebel 文档。</span><span class="sxs-lookup"><span data-stu-id="cb010-108">For more information about the inner exception, refer to the respective .NET Framework or Siebel documentation.</span></span> <span data-ttu-id="cb010-109">该异常还包含详细的错误消息，以解决此问题可帮助。</span><span class="sxs-lookup"><span data-stu-id="cb010-109">The exception also contains a detailed error message that helps in resolving the problem.</span></span> <span data-ttu-id="cb010-110">请注意，此处提及的例外列表中的不完整。</span><span class="sxs-lookup"><span data-stu-id="cb010-110">Note that the list of exceptions mentioned here is not comprehensive.</span></span>  
  
|<span data-ttu-id="cb010-111">异常</span><span class="sxs-lookup"><span data-stu-id="cb010-111">Exception</span></span>|<span data-ttu-id="cb010-112">可能的原因错误说明</span><span class="sxs-lookup"><span data-stu-id="cb010-112">Possible Cause/Error Description</span></span>|  
|---------------|---------------------------------------|  
|<span data-ttu-id="cb010-113">ConnectionException</span><span class="sxs-lookup"><span data-stu-id="cb010-113">ConnectionException</span></span>|<span data-ttu-id="cb010-114">如果无法建立的连接或关闭现有连接到 Siebel 系统，该适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-114">The adapter throws this exception if it is unable to establish a connection or close an existing connection to a Siebel system.</span></span>|  
|<span data-ttu-id="cb010-115">CredentialsException</span><span class="sxs-lookup"><span data-stu-id="cb010-115">CredentialsException</span></span>|<span data-ttu-id="cb010-116">如果适配器客户端未指定用户名或密码以连接到 Siebel 系统，该适配器将引发此异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-116">The adapter throws this exception if the adapter client does not specify a user name or password to connect to a Siebel system.</span></span>|  
|<span data-ttu-id="cb010-117">MetadataException</span><span class="sxs-lookup"><span data-stu-id="cb010-117">MetadataException</span></span>|<span data-ttu-id="cb010-118">如果它无法检索有关 Siebel 项目的元数据，该适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-118">The adapter throws this exception if it fails to retrieve metadata for Siebel artifacts.</span></span>|  
|<span data-ttu-id="cb010-119">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="cb010-119">XmlReaderParsingException</span></span>|<span data-ttu-id="cb010-120">如果要在 Siebel 系统中，调用操作的适配器客户端提供的输入的信息不完整或不正确，则适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-120">The adapter throws this exception if the input information provided by the adapter clients to invoke an operation in the Siebel system, is either incomplete or incorrect.</span></span>|  
|<span data-ttu-id="cb010-121">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="cb010-121">XmlReaderGenerationException</span></span>|<span data-ttu-id="cb010-122">如果无法生成 Siebel 系统中执行的操作的输出，该适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-122">The adapter throws this exception if it is unable to generate output for an operation executed in a Siebel system.</span></span>|  
|<span data-ttu-id="cb010-123">TargetSystemException</span><span class="sxs-lookup"><span data-stu-id="cb010-123">TargetSystemException</span></span>|<span data-ttu-id="cb010-124">适配器会引发此异常，如果 Siebel COM api，该适配器使用到 API 接口 Siebel 系统，则引发一个异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-124">The adapter throws this exception if the Siebel COM API, which the adapter uses to interface with the Siebel system, throws an exception.</span></span> <span data-ttu-id="cb010-125">内部异常包含 Siebel COM API 所引发的异常。</span><span class="sxs-lookup"><span data-stu-id="cb010-125">The inner exception contains the exception thrown by the Siebel COM API.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb010-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb010-126">See Also</span></span>  
 <span data-ttu-id="cb010-127">[为 Siebel eBusiness 应用程序了解的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cb010-127">[Understand BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span></span>  
[<span data-ttu-id="cb010-128">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="cb010-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)