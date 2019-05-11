---
title: 异常和错误处理与 SAP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d609e456e835cc14288f239bb53b252eb58f7e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373455"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a><span data-ttu-id="ebf6c-102">异常和错误处理与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="ebf6c-102">Exceptions and Error Handling with the SAP adapter</span></span>
<span data-ttu-id="ebf6c-103">列出了异常的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]引发。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-103">Lists the exceptions that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] throws.</span></span> <span data-ttu-id="ebf6c-104">这些可以包含：</span><span class="sxs-lookup"><span data-stu-id="ebf6c-104">These can contain:</span></span>  

- <span data-ttu-id="ebf6c-105">内部异常，这是.NET Framework 将引发系统异常</span><span class="sxs-lookup"><span data-stu-id="ebf6c-105">An inner exception, which is a system exception that the .NET Framework throws</span></span>  

- <span data-ttu-id="ebf6c-106">LOB 客户端库将引发一个 LOB 异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-106">An LOB exception that the LOB client library throws.</span></span>  

  <span data-ttu-id="ebf6c-107">有关内部异常的详细信息，请参阅.NET Framework 或 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-107">For more information about the inner exception, see the .NET Framework or SAP documentation.</span></span> <span data-ttu-id="ebf6c-108">异常还包含可能帮助解决此问题的详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-108">Exceptions also contain a detailed error message that may help resolve the problem.</span></span>  

## <a name="exception-descriptions"></a><span data-ttu-id="ebf6c-109">异常说明</span><span class="sxs-lookup"><span data-stu-id="ebf6c-109">Exception descriptions</span></span>  

|<span data-ttu-id="ebf6c-110">异常</span><span class="sxs-lookup"><span data-stu-id="ebf6c-110">Exception</span></span>|<span data-ttu-id="ebf6c-111">可能的原因说明</span><span class="sxs-lookup"><span data-stu-id="ebf6c-111">Possible Cause/Description</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="ebf6c-112">ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-112">ObjectDisposedException</span></span>|<span data-ttu-id="ebf6c-113">适配器客户端尝试访问响应 XMLReader 后已被释放时，适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-113">The adapter throws this exception when the adapter client is trying to access the response XMLReader after it has been disposed.</span></span>|  
|<span data-ttu-id="ebf6c-114">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-114">XmlReaderGenerationException</span></span>|<span data-ttu-id="ebf6c-115">当无法从输出消息生成 XmlReader 时，适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-115">The adapter throws this exception when it is unable to generate an XmlReader from the output message.</span></span> <span data-ttu-id="ebf6c-116">这也可能是由于 SAP 系统从接收的数据的存在一些问题。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-116">This could also be due to some problems with the data received from the SAP system.</span></span> <span data-ttu-id="ebf6c-117">查找内部异常和错误消息以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-117">Look for the inner exception and the error message for more information.</span></span>|  
|<span data-ttu-id="ebf6c-118">InvalidUriException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-118">InvalidUriException</span></span>|<span data-ttu-id="ebf6c-119">当连接 URI 没有连接字符串所需的组件时，引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-119">This exception is thrown when the connection URI does not have the required components for the connection string.</span></span>|  
|<span data-ttu-id="ebf6c-120">ConnectionException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-120">ConnectionException</span></span>|<span data-ttu-id="ebf6c-121">连接到 SAP 系统时出现问题时，或者基础连接将变为无效，因为 SAP 系统上出现错误或由于网络问题，则会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-121">This exception is thrown when there is a problem connecting to the SAP system or if an underlying connection becomes invalid, either due to an error on the SAP system or due to a network problem.</span></span>|  
|<span data-ttu-id="ebf6c-122">TimeoutException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-122">TimeoutException</span></span>|<span data-ttu-id="ebf6c-123">如果指定的操作的超时期满，引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-123">This exception is thrown when the timeout specified for an operation is lapsed.</span></span> <span data-ttu-id="ebf6c-124">内部异常包含指定的超时的原因不足够的细节。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-124">The inner exception contains the specifics of why the specified timeout was not sufficient.</span></span>|  
|<span data-ttu-id="ebf6c-125">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-125">XmlReaderParsingException</span></span>|<span data-ttu-id="ebf6c-126">如果它不支持指定的类型，或不正确的值指定的类型，则适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-126">The adapter throws this exception if it does not support the specified type, or if an incorrect value is specified for the type.</span></span> <span data-ttu-id="ebf6c-127">此外，输入的 XML 可能不正确。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-127">Also, the input XML could be incorrect.</span></span> <span data-ttu-id="ebf6c-128">不正确的值包括其中超出了文本或最大数字的最长的情况。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-128">An incorrect value includes cases where the maximum amount of text or maximum digits is exceeded.</span></span> <span data-ttu-id="ebf6c-129">输入的 XML 可能不正确的操作名称或命名空间是否不正确。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-129">The input XML might be incorrect if the operation name or namespace is incorrect.</span></span>|  
|<span data-ttu-id="ebf6c-130">RFCException （派生自 AdapterException）</span><span class="sxs-lookup"><span data-stu-id="ebf6c-130">RFCException (derived from AdapterException)</span></span>|<span data-ttu-id="ebf6c-131">如果错误来自 SAP 系统，该适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-131">The adapter throws this exception if there is an error received from the SAP system.</span></span> <span data-ttu-id="ebf6c-132">内部异常是从 SAP 系统收到的实际异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-132">The inner exception is the actual exception received from the SAP system.</span></span>|  
|<span data-ttu-id="ebf6c-133">UnsupportedOperationException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-133">UnsupportedOperationException</span></span>|<span data-ttu-id="ebf6c-134">当适配器客户端指定操作无效时，适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-134">The adapter throws this exception when the adapter client specifies an invalid action.</span></span>|  
|<span data-ttu-id="ebf6c-135">MetadataException</span><span class="sxs-lookup"><span data-stu-id="ebf6c-135">MetadataException</span></span>|<span data-ttu-id="ebf6c-136">如果元数据检索、 浏览或搜索过程中出错，则适配器会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="ebf6c-136">The adapter throws this exception if there is an error during metadata retrieval, browse, or search.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="ebf6c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf6c-137">See Also</span></span>  
[<span data-ttu-id="ebf6c-138">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="ebf6c-138">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)