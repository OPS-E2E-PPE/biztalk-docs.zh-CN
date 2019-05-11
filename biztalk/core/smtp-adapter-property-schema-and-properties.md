---
title: SMTP 适配器属性架构和属性 |Microsoft Docs
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
ms.openlocfilehash: 1dcc5e9b1ab3ac9ef5d898c21e0c70638425443a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270994"
---
# <a name="smtp-adapter-property-schema-and-properties"></a><span data-ttu-id="11d79-102">SMTP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="11d79-102">SMTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="11d79-103">下表列出了 SMTP 适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="11d79-103">The following table lists the properties in the SMTP adapter property schema.</span></span>  
  
 <span data-ttu-id="11d79-104">**Namespace**： http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span><span class="sxs-lookup"><span data-stu-id="11d79-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span></span>  
  
|<span data-ttu-id="11d79-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="11d79-105">Name</span></span>|<span data-ttu-id="11d79-106">类型</span><span class="sxs-lookup"><span data-stu-id="11d79-106">Type</span></span>|<span data-ttu-id="11d79-107">Description</span><span class="sxs-lookup"><span data-stu-id="11d79-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="11d79-108">**用户名**</span><span class="sxs-lookup"><span data-stu-id="11d79-108">**Username**</span></span>|<span data-ttu-id="11d79-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-109">xs:string</span></span>|<span data-ttu-id="11d79-110">指定要用于 SMTP 服务器的身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="11d79-110">Specify the user name to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="11d79-111">**密码**</span><span class="sxs-lookup"><span data-stu-id="11d79-111">**Password**</span></span>|<span data-ttu-id="11d79-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-112">xs:string</span></span>|<span data-ttu-id="11d79-113">指定要使用的 SMTP 服务器的身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="11d79-113">Specify the password to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="11d79-114">**SMTPHost**</span><span class="sxs-lookup"><span data-stu-id="11d79-114">**SMTPHost**</span></span>|<span data-ttu-id="11d79-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-115">xs:string</span></span>|<span data-ttu-id="11d79-116">指定要发送消息时使用的 SMTP 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="11d79-116">Specify the name of the SMTP server to use when sending messages.</span></span>|  
|<span data-ttu-id="11d79-117">**From**</span><span class="sxs-lookup"><span data-stu-id="11d79-117">**From**</span></span>|<span data-ttu-id="11d79-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-118">xs:string</span></span>|<span data-ttu-id="11d79-119">指定要放置在 SMTP 的电子邮件地址**从**标头。</span><span class="sxs-lookup"><span data-stu-id="11d79-119">Specify the e-mail address to place on the SMTP **From** header.</span></span>|  
|<span data-ttu-id="11d79-120">**CC**</span><span class="sxs-lookup"><span data-stu-id="11d79-120">**CC**</span></span>|<span data-ttu-id="11d79-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-121">xs:string</span></span>|<span data-ttu-id="11d79-122">指定要将消息的副本发送的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="11d79-122">Specify the e-mail address to send a copy of the message.</span></span>|  
|<span data-ttu-id="11d79-123">**主题**</span><span class="sxs-lookup"><span data-stu-id="11d79-123">**Subject**</span></span>|<span data-ttu-id="11d79-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-124">xs:string</span></span>|<span data-ttu-id="11d79-125">指定消息的使用者标头。</span><span class="sxs-lookup"><span data-stu-id="11d79-125">Specify the subject header for the message.</span></span>|  
|<span data-ttu-id="11d79-126">**SMTPAuthenticate**</span><span class="sxs-lookup"><span data-stu-id="11d79-126">**SMTPAuthenticate**</span></span>|<span data-ttu-id="11d79-127">xs:int</span><span class="sxs-lookup"><span data-stu-id="11d79-127">xs:int</span></span>|<span data-ttu-id="11d79-128">指定要对 SMTP 服务器使用身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="11d79-128">Specify the type of authentication to use with the SMTP server.</span></span>|  
|<span data-ttu-id="11d79-129">**ReadReceipt**</span><span class="sxs-lookup"><span data-stu-id="11d79-129">**ReadReceipt**</span></span>|<span data-ttu-id="11d79-130">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="11d79-130">xs:boolean</span></span>|<span data-ttu-id="11d79-131">指定是否在读取消息时发送一封确认电子邮件。</span><span class="sxs-lookup"><span data-stu-id="11d79-131">Specify whether to send a confirmation e-mail message when the message is read.</span></span>|  
|<span data-ttu-id="11d79-132">**DeliveryReceipt**</span><span class="sxs-lookup"><span data-stu-id="11d79-132">**DeliveryReceipt**</span></span>|<span data-ttu-id="11d79-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="11d79-133">xs:boolean</span></span>|<span data-ttu-id="11d79-134">指定是否在消息传递后发送确认电子邮件。</span><span class="sxs-lookup"><span data-stu-id="11d79-134">Specify whether to send a confirmation e-mail message after delivery of the message.</span></span>|  
|<span data-ttu-id="11d79-135">**EmailBodyText**</span><span class="sxs-lookup"><span data-stu-id="11d79-135">**EmailBodyText**</span></span>|<span data-ttu-id="11d79-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-136">xs:string</span></span>|<span data-ttu-id="11d79-137">指定要用于发送的电子邮件的正文文本。</span><span class="sxs-lookup"><span data-stu-id="11d79-137">Specify text to be used for the body of the e-mail being sent.</span></span>|  
|<span data-ttu-id="11d79-138">**EmailBodyTextCharset**</span><span class="sxs-lookup"><span data-stu-id="11d79-138">**EmailBodyTextCharset**</span></span>|<span data-ttu-id="11d79-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-139">xs:string</span></span>|<span data-ttu-id="11d79-140">指定要使用时要发送的电子邮件的正文进行编码的字符集**EmailBodyText**使用选项。</span><span class="sxs-lookup"><span data-stu-id="11d79-140">Specify the character set to use for encoding the body of the e-mail being sent when the **EmailBodyText** option is used.</span></span> <span data-ttu-id="11d79-141">SMTP 适配器会将转换**EmailBodyText**到由指定的字符集**EmailBodyTextCharset**。</span><span class="sxs-lookup"><span data-stu-id="11d79-141">The SMTP adapter will convert the **EmailBodyText** to the character set specified by **EmailBodyTextCharset**.</span></span>|  
|<span data-ttu-id="11d79-142">**EmailBodyFile**</span><span class="sxs-lookup"><span data-stu-id="11d79-142">**EmailBodyFile**</span></span>|<span data-ttu-id="11d79-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-143">xs:string</span></span>|<span data-ttu-id="11d79-144">指定文件的内容将用于要发送电子邮件和文件的完整路径的正文。</span><span class="sxs-lookup"><span data-stu-id="11d79-144">Specifies that the contents of a file will be used for the body of the e-mail being sent and the full path to the file.</span></span> <span data-ttu-id="11d79-145">在运行时，此路径必须是 SMTP 适配器的主机可访问。</span><span class="sxs-lookup"><span data-stu-id="11d79-145">This path must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="11d79-146">**EmailBodyFileCharset**</span><span class="sxs-lookup"><span data-stu-id="11d79-146">**EmailBodyFileCharset**</span></span>|<span data-ttu-id="11d79-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-147">xs:string</span></span>|<span data-ttu-id="11d79-148">指定要使用要发送的电子邮件的正文进行编码的字符集**EmailBodyFile**属性设置。</span><span class="sxs-lookup"><span data-stu-id="11d79-148">Specify the character set to use for encoding the body of the e-mail being sent if the **EmailBodyFile** property is set.</span></span> <span data-ttu-id="11d79-149">SMTP 适配器将该文件; 不执行任何转换该文件已必须用此字符集进行编码。</span><span class="sxs-lookup"><span data-stu-id="11d79-149">The SMTP adapter will not perform any conversion on the file; the file must already be encoded in this character set.</span></span> <span data-ttu-id="11d79-150">如果该文件具有字节顺序标记 (BOM)，SMTP 适配器将其删除。</span><span class="sxs-lookup"><span data-stu-id="11d79-150">If the file has a Byte-Order-Mark (BOM), the SMTP adapter will remove it.</span></span>|  
|<span data-ttu-id="11d79-151">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="11d79-151">**Attachments**</span></span>|<span data-ttu-id="11d79-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="11d79-152">xs:string</span></span>|<span data-ttu-id="11d79-153">指定的文件将附加到电子邮件和文件的文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="11d79-153">Specifies that a file or files will be attached to the e-mail message and the full path to the file or files.</span></span> <span data-ttu-id="11d79-154">指定的路径必须是 SMTP 适配器的主机可以访问在运行时。</span><span class="sxs-lookup"><span data-stu-id="11d79-154">The specified path or paths must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="11d79-155">**MessagePartsAttachments**</span><span class="sxs-lookup"><span data-stu-id="11d79-155">**MessagePartsAttachments**</span></span>|<span data-ttu-id="11d79-156">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="11d79-156">xs:unsignedInt</span></span>|<span data-ttu-id="11d79-157">指定 BizTalk 消息部分如何附加到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="11d79-157">Specify how BizTalk message parts are attached to the e-mail message.</span></span>|  
|<span data-ttu-id="11d79-158">**ReplyBy**</span><span class="sxs-lookup"><span data-stu-id="11d79-158">**ReplyBy**</span></span>|<span data-ttu-id="11d79-159">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="11d79-159">xs:dateTime</span></span>|<span data-ttu-id="11d79-160">指定一个日期时间值**答复**传出的电子邮件消息中的标头。</span><span class="sxs-lookup"><span data-stu-id="11d79-160">Specify a dateTime value for the **Reply-To** header in the outgoing e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11d79-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="11d79-161">See Also</span></span>  
 [<span data-ttu-id="11d79-162">配置 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="11d79-162">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)