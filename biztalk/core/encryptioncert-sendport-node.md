---
title: EncryptionCert （SendPort 节点） |Microsoft Docs
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
ms.openlocfilehash: a314490ecb9b92babab690e892ee7ce11ebfdec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349497"
---
# <a name="encryptioncert-sendport-node"></a><span data-ttu-id="290f0-102">EncryptionCert （SendPort 节点）</span><span class="sxs-lookup"><span data-stu-id="290f0-102">EncryptionCert (SendPort Node)</span></span>
<span data-ttu-id="290f0-103">绑定文件的发送端口节点的 EncryptionCert 节点包含有关与绑定文件一起导出的发送端口一起使用的加密证书的信息。</span><span class="sxs-lookup"><span data-stu-id="290f0-103">The EncryptionCert node of the SendPort node of a binding file contains information about the encryption certificate used with a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-encryptioncert-node"></a><span data-ttu-id="290f0-104">EncryptionCert 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="290f0-104">Nodes in the EncryptionCert node</span></span>  
 <span data-ttu-id="290f0-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="290f0-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="290f0-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="290f0-106">**Name**</span></span>|<span data-ttu-id="290f0-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="290f0-107">**Node Type**</span></span>|<span data-ttu-id="290f0-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="290f0-108">**Data Type**</span></span>|<span data-ttu-id="290f0-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="290f0-109">**Description**</span></span>|<span data-ttu-id="290f0-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="290f0-110">**Restrictions**</span></span>|<span data-ttu-id="290f0-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="290f0-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="290f0-112">LongName</span><span class="sxs-lookup"><span data-stu-id="290f0-112">LongName</span></span>|<span data-ttu-id="290f0-113">特性</span><span class="sxs-lookup"><span data-stu-id="290f0-113">Attribute</span></span>|<span data-ttu-id="290f0-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="290f0-114">xs:string</span></span>|<span data-ttu-id="290f0-115">指定证书的长名称。</span><span class="sxs-lookup"><span data-stu-id="290f0-115">Specifies the long name of the certificate.</span></span>|<span data-ttu-id="290f0-116">可选</span><span class="sxs-lookup"><span data-stu-id="290f0-116">Not required</span></span>|<span data-ttu-id="290f0-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="290f0-117">Default value: empty</span></span>|  
|<span data-ttu-id="290f0-118">ShortName</span><span class="sxs-lookup"><span data-stu-id="290f0-118">ShortName</span></span>|<span data-ttu-id="290f0-119">特性</span><span class="sxs-lookup"><span data-stu-id="290f0-119">Attribute</span></span>|<span data-ttu-id="290f0-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="290f0-120">xs:string</span></span>|<span data-ttu-id="290f0-121">指定证书的短名称。</span><span class="sxs-lookup"><span data-stu-id="290f0-121">Specifies the short name of the certificate.</span></span>|<span data-ttu-id="290f0-122">可选</span><span class="sxs-lookup"><span data-stu-id="290f0-122">Not required</span></span>|<span data-ttu-id="290f0-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="290f0-123">Default value: empty</span></span>|  
|<span data-ttu-id="290f0-124">UsageType</span><span class="sxs-lookup"><span data-stu-id="290f0-124">UsageType</span></span>|<span data-ttu-id="290f0-125">特性</span><span class="sxs-lookup"><span data-stu-id="290f0-125">Attribute</span></span>|<span data-ttu-id="290f0-126">CertUsageType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="290f0-126">CertUsageType (SimpleType)</span></span>|<span data-ttu-id="290f0-127">指定此证书的预期的用法</span><span class="sxs-lookup"><span data-stu-id="290f0-127">Specifies the intended usage of this certificate</span></span>|<span data-ttu-id="290f0-128">Required</span><span class="sxs-lookup"><span data-stu-id="290f0-128">Required</span></span>|<span data-ttu-id="290f0-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="290f0-129">Default value: none</span></span><br /><br /> <span data-ttu-id="290f0-130">可能的值包括可[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。</span><span class="sxs-lookup"><span data-stu-id="290f0-130">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="290f0-131">ThumbPrint</span><span class="sxs-lookup"><span data-stu-id="290f0-131">ThumbPrint</span></span>|<span data-ttu-id="290f0-132">特性</span><span class="sxs-lookup"><span data-stu-id="290f0-132">Attribute</span></span>|<span data-ttu-id="290f0-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="290f0-133">xs:string</span></span>|<span data-ttu-id="290f0-134">指定的指纹或证书的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="290f0-134">Specifies the thumbprint, or unique ID, of the certificate.</span></span>|<span data-ttu-id="290f0-135">可选</span><span class="sxs-lookup"><span data-stu-id="290f0-135">Not required</span></span>|<span data-ttu-id="290f0-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="290f0-136">Default value: empty</span></span>|