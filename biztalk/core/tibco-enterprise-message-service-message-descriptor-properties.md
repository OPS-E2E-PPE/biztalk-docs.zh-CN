---
title: "TIBCO 企业消息服务消息描述符属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message descriptor properties
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c75875c44c4d082089fc9394fef390a0f91571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="d2332-102">TIBCO Enterprise Message Service 消息描述符属性</span><span class="sxs-lookup"><span data-stu-id="d2332-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>
<span data-ttu-id="d2332-103">下表显示了可用的消息描述符（TibcoEMSMD 结构）属性的完整集以及其对应的类型和值：</span><span class="sxs-lookup"><span data-stu-id="d2332-103">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="d2332-104">Name</span><span class="sxs-lookup"><span data-stu-id="d2332-104">Name</span></span>|<span data-ttu-id="d2332-105">类型</span><span class="sxs-lookup"><span data-stu-id="d2332-105">Type</span></span>|<span data-ttu-id="d2332-106">值</span><span class="sxs-lookup"><span data-stu-id="d2332-106">Value</span></span>|<span data-ttu-id="d2332-107">说明</span><span class="sxs-lookup"><span data-stu-id="d2332-107">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="d2332-108">TibcoEMS .CorrelationID</span><span class="sxs-lookup"><span data-stu-id="d2332-108">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="d2332-109">string</span><span class="sxs-lookup"><span data-stu-id="d2332-109">string</span></span>|||  
|<span data-ttu-id="d2332-110">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="d2332-110">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="d2332-111">string</span><span class="sxs-lookup"><span data-stu-id="d2332-111">string</span></span>|<span data-ttu-id="d2332-112">一个 PERSISENT 或 NON-PERSISTENT</span><span class="sxs-lookup"><span data-stu-id="d2332-112">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="d2332-113">TibcoEMS .Destination</span><span class="sxs-lookup"><span data-stu-id="d2332-113">TibcoEMS .Destination</span></span>|<span data-ttu-id="d2332-114">string</span><span class="sxs-lookup"><span data-stu-id="d2332-114">string</span></span>||<span data-ttu-id="d2332-115">只读</span><span class="sxs-lookup"><span data-stu-id="d2332-115">Read-only</span></span>|  
|<span data-ttu-id="d2332-116">TibcoEMS .Expiration</span><span class="sxs-lookup"><span data-stu-id="d2332-116">TibcoEMS .Expiration</span></span>|<span data-ttu-id="d2332-117">long</span><span class="sxs-lookup"><span data-stu-id="d2332-117">long</span></span>|||  
|<span data-ttu-id="d2332-118">TibcoEMS .MessageID</span><span class="sxs-lookup"><span data-stu-id="d2332-118">TibcoEMS .MessageID</span></span>|<span data-ttu-id="d2332-119">string</span><span class="sxs-lookup"><span data-stu-id="d2332-119">string</span></span>||<span data-ttu-id="d2332-120">只读</span><span class="sxs-lookup"><span data-stu-id="d2332-120">Read-only</span></span>|  
|<span data-ttu-id="d2332-121">TibcoEMS .Priority</span><span class="sxs-lookup"><span data-stu-id="d2332-121">TibcoEMS .Priority</span></span>|<span data-ttu-id="d2332-122">integer</span><span class="sxs-lookup"><span data-stu-id="d2332-122">integer</span></span>|<span data-ttu-id="d2332-123">从 0 到 9</span><span class="sxs-lookup"><span data-stu-id="d2332-123">From 0 to 9</span></span>||  
|<span data-ttu-id="d2332-124">TibcoEMS .Redelivered</span><span class="sxs-lookup"><span data-stu-id="d2332-124">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="d2332-125">boolean</span><span class="sxs-lookup"><span data-stu-id="d2332-125">boolean</span></span>||<span data-ttu-id="d2332-126">只读</span><span class="sxs-lookup"><span data-stu-id="d2332-126">Read-only</span></span>|  
|<span data-ttu-id="d2332-127">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="d2332-127">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="d2332-128">string</span><span class="sxs-lookup"><span data-stu-id="d2332-128">string</span></span>|<span data-ttu-id="d2332-129">类似于目标</span><span class="sxs-lookup"><span data-stu-id="d2332-129">Similar to Destination</span></span>||  
|<span data-ttu-id="d2332-130">TibcoEMS .Timestamp</span><span class="sxs-lookup"><span data-stu-id="d2332-130">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="d2332-131">long</span><span class="sxs-lookup"><span data-stu-id="d2332-131">long</span></span>||<span data-ttu-id="d2332-132">只读</span><span class="sxs-lookup"><span data-stu-id="d2332-132">Read-only</span></span>|  
  
 <span data-ttu-id="d2332-133">只读属性是在向用于 TIBCO EMS 的 Microsoft BizTalk 适配器发送消息时由 TIBCO Enterprise 消息服务设置的属性。</span><span class="sxs-lookup"><span data-stu-id="d2332-133">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="d2332-134">更改此值，尽管可能在消息分配形状的表达式中，但不影响消息。</span><span class="sxs-lookup"><span data-stu-id="d2332-134">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="d2332-135">对于必须从 EMS 消息移动到 BizTalk Server 消息的其他属性，必须创建一个属性 DLL 并在该项目中使用它。</span><span class="sxs-lookup"><span data-stu-id="d2332-135">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="d2332-136">以下示例属性架构使业务流程能够使用 `JMSXDeliveryCount` 消息属性。</span><span class="sxs-lookup"><span data-stu-id="d2332-136">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="d2332-137">确保使用目标命名空间；仅将使用该命名空间的属性复制到 BizTalk Server 消息或复制到 EMS 消息。</span><span class="sxs-lookup"><span data-stu-id="d2332-137">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="d2332-138">有关消息上下文属性的详细信息，请参阅 BizTalk Server 文档。</span><span class="sxs-lookup"><span data-stu-id="d2332-138">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2332-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2332-139">See Also</span></span>  
 [<span data-ttu-id="d2332-140">消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="d2332-140">Message Context Properties</span></span>](../core/message-context-properties2.md)