---
title: EncryptionCert （发送端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 83dff67e-1b3c-4c3d-91a2-d826a498635f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd51f4b339c5bdd228c692fffd7e6c487bb8c0ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-sendport-node"></a><span data-ttu-id="0ffb5-102">EncryptionCert（“发送端口”节点）</span><span class="sxs-lookup"><span data-stu-id="0ffb5-102">EncryptionCert (SendPort Node)</span></span>
<span data-ttu-id="0ffb5-103">绑定文件的 SendPort 节点的 EncryptionCert 节点包含有关随绑定文件导出的发送端口所用的加密证书的信息。</span><span class="sxs-lookup"><span data-stu-id="0ffb5-103">The EncryptionCert node of the SendPort node of a binding file contains information about the encryption certificate used with a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="0ffb5-104">EncryptionCert 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="0ffb5-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="0ffb5-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="0ffb5-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="0ffb5-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-106">**Name**</span></span>|<span data-ttu-id="0ffb5-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-107">**Node Type**</span></span>|<span data-ttu-id="0ffb5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-108">**Data Type**</span></span>|<span data-ttu-id="0ffb5-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-109">**Description**</span></span>|<span data-ttu-id="0ffb5-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-110">**Restrictions**</span></span>|<span data-ttu-id="0ffb5-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="0ffb5-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="0ffb5-112">长名称</span><span class="sxs-lookup"><span data-stu-id="0ffb5-112">LongName</span></span>|<span data-ttu-id="0ffb5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ffb5-113">Attribute</span></span>|<span data-ttu-id="0ffb5-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ffb5-114">xs:string</span></span>|<span data-ttu-id="0ffb5-115">指定证书的长名称。</span><span class="sxs-lookup"><span data-stu-id="0ffb5-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="0ffb5-116">可选</span><span class="sxs-lookup"><span data-stu-id="0ffb5-116">Not required</span></span>|<span data-ttu-id="0ffb5-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="0ffb5-117">Default value: empty</span></span>|  
|<span data-ttu-id="0ffb5-118">短名称</span><span class="sxs-lookup"><span data-stu-id="0ffb5-118">ShortName</span></span>|<span data-ttu-id="0ffb5-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ffb5-119">Attribute</span></span>|<span data-ttu-id="0ffb5-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ffb5-120">xs:string</span></span>|<span data-ttu-id="0ffb5-121">指定证书的短名称。</span><span class="sxs-lookup"><span data-stu-id="0ffb5-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="0ffb5-122">可选</span><span class="sxs-lookup"><span data-stu-id="0ffb5-122">Not required</span></span>|<span data-ttu-id="0ffb5-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="0ffb5-123">Default value: empty</span></span>|  
|<span data-ttu-id="0ffb5-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="0ffb5-124">UsageType</span></span>|<span data-ttu-id="0ffb5-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ffb5-125">Attribute</span></span>|<span data-ttu-id="0ffb5-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="0ffb5-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="0ffb5-127">指定此证书的预期的用法</span><span class="sxs-lookup"><span data-stu-id="0ffb5-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="0ffb5-128">必需</span><span class="sxs-lookup"><span data-stu-id="0ffb5-128">Required</span></span>|<span data-ttu-id="0ffb5-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="0ffb5-129">Default value: none</span></span><br /><br /> <span data-ttu-id="0ffb5-130">可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。</span><span class="sxs-lookup"><span data-stu-id="0ffb5-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="0ffb5-131">指纹</span><span class="sxs-lookup"><span data-stu-id="0ffb5-131">ThumbPrint</span></span>|<span data-ttu-id="0ffb5-132">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ffb5-132">Attribute</span></span>|<span data-ttu-id="0ffb5-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ffb5-133">xs:string</span></span>|<span data-ttu-id="0ffb5-134">指定证书的指纹或唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0ffb5-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="0ffb5-135">可选</span><span class="sxs-lookup"><span data-stu-id="0ffb5-135">Not required</span></span>|<span data-ttu-id="0ffb5-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="0ffb5-136">Default value: empty</span></span>|