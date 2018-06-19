---
title: SMTP 适配器属性架构和属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UserName property, SMTP adapters
- EmailBodyTextCharset property [SMTP adapters]
- configuring [SMTP adapters], properties
- Subject property [SMTP adapters]
- EmailBodyFileCharset property [SMTP adapters]
- Attachments property [SMTP adapters]
- SMTP adapters, schemas
- EmailBodyText property [SMTP adapters]
- configuring [SMTP adapters], schemas
- CC property [SMTP adapters]
- ReadReceipt property [SMTP adapters]
- Password property [SMTP adapters]
- ReplyBy property [SMTP adapters]
- DeliveryReceipt property [SMTP adapters]
- SMTP adapters, properties
- SMTPAuthenticate property [SMTP adapters]
- EmailBodyFile property [SMTP adapters]
- schemas, SMTP adapters
- SMTPHost property [SMTP adapters]
- From property [SMTP adapters]
- MessagePartsAttachments property [SMTP adapters]
ms.assetid: 6d062fb6-d728-4525-8f0d-bd3f0f8ff7ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09f7dfa67bfad53e43a4a6678ff6ad67705e0e27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278669"
---
# <a name="smtp-adapter-property-schema-and-properties"></a><span data-ttu-id="39c0a-102">SMTP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="39c0a-102">SMTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="39c0a-103">下表列出了 SMTP 适配器属性架构中的属性：</span><span class="sxs-lookup"><span data-stu-id="39c0a-103">The following table lists the properties in the SMTP adapter property schema.</span></span>  
  
 <span data-ttu-id="39c0a-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span><span class="sxs-lookup"><span data-stu-id="39c0a-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span></span>  
  
|<span data-ttu-id="39c0a-105">Name</span><span class="sxs-lookup"><span data-stu-id="39c0a-105">Name</span></span>|<span data-ttu-id="39c0a-106">类型</span><span class="sxs-lookup"><span data-stu-id="39c0a-106">Type</span></span>|<span data-ttu-id="39c0a-107">Description</span><span class="sxs-lookup"><span data-stu-id="39c0a-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="39c0a-108">**用户名**</span><span class="sxs-lookup"><span data-stu-id="39c0a-108">**Username**</span></span>|<span data-ttu-id="39c0a-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-109">xs:string</span></span>|<span data-ttu-id="39c0a-110">指定对 SMTP 服务器进行验证所使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="39c0a-110">Specify the user name to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="39c0a-111">**密码**</span><span class="sxs-lookup"><span data-stu-id="39c0a-111">**Password**</span></span>|<span data-ttu-id="39c0a-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-112">xs:string</span></span>|<span data-ttu-id="39c0a-113">指定对 SMTP 服务器进行验证所使用的密码。</span><span class="sxs-lookup"><span data-stu-id="39c0a-113">Specify the password to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="39c0a-114">**SMTPHost**</span><span class="sxs-lookup"><span data-stu-id="39c0a-114">**SMTPHost**</span></span>|<span data-ttu-id="39c0a-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-115">xs:string</span></span>|<span data-ttu-id="39c0a-116">指定发送邮件时要使用的 SMTP 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="39c0a-116">Specify the name of the SMTP server to use when sending messages.</span></span>|  
|<span data-ttu-id="39c0a-117">**From**</span><span class="sxs-lookup"><span data-stu-id="39c0a-117">**From**</span></span>|<span data-ttu-id="39c0a-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-118">xs:string</span></span>|<span data-ttu-id="39c0a-119">指定要放入 SMTP 的电子邮件地址**从**标头。</span><span class="sxs-lookup"><span data-stu-id="39c0a-119">Specify the e-mail address to place on the SMTP **From** header.</span></span>|  
|<span data-ttu-id="39c0a-120">**抄送**</span><span class="sxs-lookup"><span data-stu-id="39c0a-120">**CC**</span></span>|<span data-ttu-id="39c0a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-121">xs:string</span></span>|<span data-ttu-id="39c0a-122">指定要将邮件的副本发送到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="39c0a-122">Specify the e-mail address to send a copy of the message.</span></span>|  
|<span data-ttu-id="39c0a-123">**主题**</span><span class="sxs-lookup"><span data-stu-id="39c0a-123">**Subject**</span></span>|<span data-ttu-id="39c0a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-124">xs:string</span></span>|<span data-ttu-id="39c0a-125">指定邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="39c0a-125">Specify the subject header for the message.</span></span>|  
|<span data-ttu-id="39c0a-126">**SMTPAuthenticate**</span><span class="sxs-lookup"><span data-stu-id="39c0a-126">**SMTPAuthenticate**</span></span>|<span data-ttu-id="39c0a-127">xs:int</span><span class="sxs-lookup"><span data-stu-id="39c0a-127">xs:int</span></span>|<span data-ttu-id="39c0a-128">指定对 SMTP 服务器使用的验证类型。</span><span class="sxs-lookup"><span data-stu-id="39c0a-128">Specify the type of authentication to use with the SMTP server.</span></span>|  
|<span data-ttu-id="39c0a-129">**ReadReceipt**</span><span class="sxs-lookup"><span data-stu-id="39c0a-129">**ReadReceipt**</span></span>|<span data-ttu-id="39c0a-130">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="39c0a-130">xs:boolean</span></span>|<span data-ttu-id="39c0a-131">指定在阅读邮件后是否发送确认电子邮件。</span><span class="sxs-lookup"><span data-stu-id="39c0a-131">Specify whether to send a confirmation e-mail message when the message is read.</span></span>|  
|<span data-ttu-id="39c0a-132">**DeliveryReceipt**</span><span class="sxs-lookup"><span data-stu-id="39c0a-132">**DeliveryReceipt**</span></span>|<span data-ttu-id="39c0a-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="39c0a-133">xs:boolean</span></span>|<span data-ttu-id="39c0a-134">指定在送达邮件后是否发送确认电子邮件。</span><span class="sxs-lookup"><span data-stu-id="39c0a-134">Specify whether to send a confirmation e-mail message after delivery of the message.</span></span>|  
|<span data-ttu-id="39c0a-135">**EmailBodyText**</span><span class="sxs-lookup"><span data-stu-id="39c0a-135">**EmailBodyText**</span></span>|<span data-ttu-id="39c0a-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-136">xs:string</span></span>|<span data-ttu-id="39c0a-137">指定将用于要发送的电子邮件正文的文本。</span><span class="sxs-lookup"><span data-stu-id="39c0a-137">Specify text to be used for the body of the e-mail being sent.</span></span>|  
|<span data-ttu-id="39c0a-138">**EmailBodyTextCharset**</span><span class="sxs-lookup"><span data-stu-id="39c0a-138">**EmailBodyTextCharset**</span></span>|<span data-ttu-id="39c0a-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-139">xs:string</span></span>|<span data-ttu-id="39c0a-140">指定要用于编码时要发送电子邮件的正文的字符集**EmailBodyText**使用选项。</span><span class="sxs-lookup"><span data-stu-id="39c0a-140">Specify the character set to use for encoding the body of the e-mail being sent when the **EmailBodyText** option is used.</span></span> <span data-ttu-id="39c0a-141">SMTP 适配器会将转换**EmailBodyText**为设置指定的字符**EmailBodyTextCharset**。</span><span class="sxs-lookup"><span data-stu-id="39c0a-141">The SMTP adapter will convert the **EmailBodyText** to the character set specified by **EmailBodyTextCharset**.</span></span>|  
|<span data-ttu-id="39c0a-142">**EmailBodyFile**</span><span class="sxs-lookup"><span data-stu-id="39c0a-142">**EmailBodyFile**</span></span>|<span data-ttu-id="39c0a-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-143">xs:string</span></span>|<span data-ttu-id="39c0a-144">指定将使用一个文件的内容作为要发送的电子邮件的正文，并指定该文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="39c0a-144">Specifies that the contents of a file will be used for the body of the e-mail being sent and the full path to the file.</span></span> <span data-ttu-id="39c0a-145">在运行时，SMTP 适配器所在的主机必须能够访问此路径。</span><span class="sxs-lookup"><span data-stu-id="39c0a-145">This path must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="39c0a-146">**EmailBodyFileCharset**</span><span class="sxs-lookup"><span data-stu-id="39c0a-146">**EmailBodyFileCharset**</span></span>|<span data-ttu-id="39c0a-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-147">xs:string</span></span>|<span data-ttu-id="39c0a-148">指定要用于编码如果正在发送的电子邮件正文的字符集**EmailBodyFile**属性设置。</span><span class="sxs-lookup"><span data-stu-id="39c0a-148">Specify the character set to use for encoding the body of the e-mail being sent if the **EmailBodyFile** property is set.</span></span> <span data-ttu-id="39c0a-149">SMTP 适配器将不对该文件执行任何转换；该文件必须已用此字符集进行编码。</span><span class="sxs-lookup"><span data-stu-id="39c0a-149">The SMTP adapter will not perform any conversion on the file; the file must already be encoded in this character set.</span></span> <span data-ttu-id="39c0a-150">如果该文件具有字节顺序标记 (BOM)，则 SMTP 适配器将删除该标记。</span><span class="sxs-lookup"><span data-stu-id="39c0a-150">If the file has a Byte-Order-Mark (BOM), the SMTP adapter will remove it.</span></span>|  
|<span data-ttu-id="39c0a-151">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="39c0a-151">**Attachments**</span></span>|<span data-ttu-id="39c0a-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="39c0a-152">xs:string</span></span>|<span data-ttu-id="39c0a-153">指定将向电子邮件附加一个或多个文件，并指定所附加的文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="39c0a-153">Specifies that a file or files will be attached to the e-mail message and the full path to the file or files.</span></span> <span data-ttu-id="39c0a-154">在运行时，SMTP 适配器所在的主机必须能够访问所指定的路径。</span><span class="sxs-lookup"><span data-stu-id="39c0a-154">The specified path or paths must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="39c0a-155">**MessagePartsAttachments**</span><span class="sxs-lookup"><span data-stu-id="39c0a-155">**MessagePartsAttachments**</span></span>|<span data-ttu-id="39c0a-156">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="39c0a-156">xs:unsignedInt</span></span>|<span data-ttu-id="39c0a-157">指定 BizTalk 消息部分如何附加到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="39c0a-157">Specify how BizTalk message parts are attached to the e-mail message.</span></span>|  
|<span data-ttu-id="39c0a-158">**ReplyBy**</span><span class="sxs-lookup"><span data-stu-id="39c0a-158">**ReplyBy**</span></span>|<span data-ttu-id="39c0a-159">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="39c0a-159">xs:dateTime</span></span>|<span data-ttu-id="39c0a-160">指定的日期时间值**答复到**传出的电子邮件消息中的标头。</span><span class="sxs-lookup"><span data-stu-id="39c0a-160">Specify a dateTime value for the **Reply-To** header in the outgoing e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39c0a-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39c0a-161">See Also</span></span>  
 [<span data-ttu-id="39c0a-162">配置 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="39c0a-162">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)