---
title: POP3 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bfd98117254686f69a590430f46fbd07a4d0b03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394907"
---
# <a name="pop3-adapter-property-schema-and-properties"></a><span data-ttu-id="4cc89-102">POP3 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="4cc89-102">POP3 Adapter Property Schema and Properties</span></span>
<span data-ttu-id="4cc89-103">下表列出了 POP3 适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="4cc89-103">The following table lists the properties in the POP3 adapter property schema.</span></span>  
  
 <span data-ttu-id="4cc89-104">**Namespace**： http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span><span class="sxs-lookup"><span data-stu-id="4cc89-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span></span>  
  
|<span data-ttu-id="4cc89-105">**名称**</span><span class="sxs-lookup"><span data-stu-id="4cc89-105">**Name**</span></span>|<span data-ttu-id="4cc89-106">**类型**</span><span class="sxs-lookup"><span data-stu-id="4cc89-106">**Type**</span></span>|<span data-ttu-id="4cc89-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="4cc89-107">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="4cc89-108">**主题**</span><span class="sxs-lookup"><span data-stu-id="4cc89-108">**Subject**</span></span>|<span data-ttu-id="4cc89-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-109">xs:string</span></span>|<span data-ttu-id="4cc89-110">指定上放置的内容**使用者**消息标头</span><span class="sxs-lookup"><span data-stu-id="4cc89-110">Specifies the content placed on the **Subject** header for the message</span></span>|  
|<span data-ttu-id="4cc89-111">**From**</span><span class="sxs-lookup"><span data-stu-id="4cc89-111">**From**</span></span>|<span data-ttu-id="4cc89-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-112">xs:string</span></span>|<span data-ttu-id="4cc89-113">指定上放置的电子邮件地址**从**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-113">Specifies the e-mail address placed on the **From** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-114">**若要**</span><span class="sxs-lookup"><span data-stu-id="4cc89-114">**To**</span></span>|<span data-ttu-id="4cc89-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-115">xs:string</span></span>|<span data-ttu-id="4cc89-116">指定的电子邮件地址或地址上放置**到**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-116">Specifies the e-mail address or addresses placed on the **To** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-117">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="4cc89-117">**ReplyTo**</span></span>|<span data-ttu-id="4cc89-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-118">xs:string</span></span>|<span data-ttu-id="4cc89-119">指定上放置的电子邮件地址**ReplyTo**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-119">Specifies the e-mail address placed on the **ReplyTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-120">**CC**</span><span class="sxs-lookup"><span data-stu-id="4cc89-120">**CC**</span></span>|<span data-ttu-id="4cc89-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-121">xs:string</span></span>|<span data-ttu-id="4cc89-122">指定的电子邮件地址或地址上放置**CC**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-122">Specifies the e-mail address or addresses placed on the **CC** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-123">**Date**</span><span class="sxs-lookup"><span data-stu-id="4cc89-123">**Date**</span></span>|<span data-ttu-id="4cc89-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-124">xs:string</span></span>|<span data-ttu-id="4cc89-125">指定上放置的内容**日期**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-125">Specifies the content placed on the **Date** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-126">**DispositionNotificationTo**</span><span class="sxs-lookup"><span data-stu-id="4cc89-126">**DispositionNotificationTo**</span></span>|<span data-ttu-id="4cc89-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-127">xs:string</span></span>|<span data-ttu-id="4cc89-128">指定上放置的内容**DispositionNotificationTo**电子邮件消息的标头字段。</span><span class="sxs-lookup"><span data-stu-id="4cc89-128">Specifies the content placed on the **DispositionNotificationTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="4cc89-129">**标头**</span><span class="sxs-lookup"><span data-stu-id="4cc89-129">**Headers**</span></span>|<span data-ttu-id="4cc89-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4cc89-130">xs:string</span></span>|<span data-ttu-id="4cc89-131">指定的所有电子邮件消息的标头字段的内容。</span><span class="sxs-lookup"><span data-stu-id="4cc89-131">Specifies the content of all of the header fields of the e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4cc89-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cc89-132">See Also</span></span>  
 [<span data-ttu-id="4cc89-133">配置 POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="4cc89-133">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)