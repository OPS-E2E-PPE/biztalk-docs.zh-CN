---
title: EncryptionCert （接收位置节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 04dc4021-8cd9-45e7-8339-8f22e29f4be6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4d0ff769c7a8ca297800f427c4ebbae48a8640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240509"
---
# <a name="encryptioncert-receivelocation-node"></a><span data-ttu-id="9ded8-102">EncryptionCert（ReceiveLocation 节点）</span><span class="sxs-lookup"><span data-stu-id="9ded8-102">EncryptionCert (ReceiveLocation Node)</span></span>
<span data-ttu-id="9ded8-103">绑定文件的 ReceiveLocation 节点的 EncryptionCert 节点包含与用于从该绑定文件导出的接收位置的加密证书有关的信息。</span><span class="sxs-lookup"><span data-stu-id="9ded8-103">The EncryptionCert node of the ReceiveLocation node of a binding file contains information about the encryption certificate used with a receive location that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="9ded8-104">EncryptionCert 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="9ded8-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="9ded8-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="9ded8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="9ded8-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="9ded8-106">**Name**</span></span>|<span data-ttu-id="9ded8-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="9ded8-107">**Node Type**</span></span>|<span data-ttu-id="9ded8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9ded8-108">**Data Type**</span></span>|<span data-ttu-id="9ded8-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="9ded8-109">**Description**</span></span>|<span data-ttu-id="9ded8-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="9ded8-110">**Restrictions**</span></span>|<span data-ttu-id="9ded8-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="9ded8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="9ded8-112">长名称</span><span class="sxs-lookup"><span data-stu-id="9ded8-112">LongName</span></span>|<span data-ttu-id="9ded8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ded8-113">Attribute</span></span>|<span data-ttu-id="9ded8-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ded8-114">xs:string</span></span>|<span data-ttu-id="9ded8-115">指定证书的长名称。</span><span class="sxs-lookup"><span data-stu-id="9ded8-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="9ded8-116">可选</span><span class="sxs-lookup"><span data-stu-id="9ded8-116">Not required</span></span>|<span data-ttu-id="9ded8-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="9ded8-117">Default value: empty</span></span>|  
|<span data-ttu-id="9ded8-118">短名称</span><span class="sxs-lookup"><span data-stu-id="9ded8-118">ShortName</span></span>|<span data-ttu-id="9ded8-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ded8-119">Attribute</span></span>|<span data-ttu-id="9ded8-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ded8-120">xs:string</span></span>|<span data-ttu-id="9ded8-121">指定证书的短名称。</span><span class="sxs-lookup"><span data-stu-id="9ded8-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="9ded8-122">可选</span><span class="sxs-lookup"><span data-stu-id="9ded8-122">Not required</span></span>|<span data-ttu-id="9ded8-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="9ded8-123">Default value: empty</span></span>|  
|<span data-ttu-id="9ded8-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="9ded8-124">UsageType</span></span>|<span data-ttu-id="9ded8-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ded8-125">Attribute</span></span>|<span data-ttu-id="9ded8-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="9ded8-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="9ded8-127">指定此证书的预期的用法</span><span class="sxs-lookup"><span data-stu-id="9ded8-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="9ded8-128">必需</span><span class="sxs-lookup"><span data-stu-id="9ded8-128">Required</span></span>|<span data-ttu-id="9ded8-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="9ded8-129">Default value: none</span></span><br /><br /> <span data-ttu-id="9ded8-130">可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。</span><span class="sxs-lookup"><span data-stu-id="9ded8-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="9ded8-131">指纹</span><span class="sxs-lookup"><span data-stu-id="9ded8-131">ThumbPrint</span></span>|<span data-ttu-id="9ded8-132">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ded8-132">Attribute</span></span>|<span data-ttu-id="9ded8-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ded8-133">xs:string</span></span>|<span data-ttu-id="9ded8-134">指定证书的指纹或唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9ded8-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="9ded8-135">可选</span><span class="sxs-lookup"><span data-stu-id="9ded8-135">Not required</span></span>|<span data-ttu-id="9ded8-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="9ded8-136">Default value: empty</span></span>|