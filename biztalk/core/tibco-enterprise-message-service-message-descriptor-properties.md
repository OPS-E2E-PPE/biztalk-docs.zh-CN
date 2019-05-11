---
title: TIBCO EMS 消息描述符属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3684b21f7e37757a9d6ab3bf66e352d4518d33bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379902"
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="98119-102">TIBCO Enterprise Message Service 消息描述符属性</span><span class="sxs-lookup"><span data-stu-id="98119-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>

## <a name="descriptor-properties-and-values"></a><span data-ttu-id="98119-103">描述符属性和值</span><span class="sxs-lookup"><span data-stu-id="98119-103">Descriptor properties, and values</span></span>
<span data-ttu-id="98119-104">下表显示了可用的消息描述符 （TibcoEMSMD 结构） 属性及其相应的类型和值的完整集。</span><span class="sxs-lookup"><span data-stu-id="98119-104">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="98119-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="98119-105">Name</span></span>|<span data-ttu-id="98119-106">类型</span><span class="sxs-lookup"><span data-stu-id="98119-106">Type</span></span>|<span data-ttu-id="98119-107">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="98119-107">Value</span></span>|<span data-ttu-id="98119-108">说明</span><span class="sxs-lookup"><span data-stu-id="98119-108">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="98119-109">TibcoEMS。相关 Id</span><span class="sxs-lookup"><span data-stu-id="98119-109">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="98119-110">string</span><span class="sxs-lookup"><span data-stu-id="98119-110">string</span></span>|||  
|<span data-ttu-id="98119-111">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="98119-111">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="98119-112">string</span><span class="sxs-lookup"><span data-stu-id="98119-112">string</span></span>|<span data-ttu-id="98119-113">一个 PERSISENT 或 NON-PERSISTENT</span><span class="sxs-lookup"><span data-stu-id="98119-113">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="98119-114">TibcoEMS。目标</span><span class="sxs-lookup"><span data-stu-id="98119-114">TibcoEMS .Destination</span></span>|<span data-ttu-id="98119-115">string</span><span class="sxs-lookup"><span data-stu-id="98119-115">string</span></span>||<span data-ttu-id="98119-116">只读</span><span class="sxs-lookup"><span data-stu-id="98119-116">Read-only</span></span>|  
|<span data-ttu-id="98119-117">TibcoEMS。过期</span><span class="sxs-lookup"><span data-stu-id="98119-117">TibcoEMS .Expiration</span></span>|<span data-ttu-id="98119-118">long</span><span class="sxs-lookup"><span data-stu-id="98119-118">long</span></span>|||  
|<span data-ttu-id="98119-119">TibcoEMS。消息 Id</span><span class="sxs-lookup"><span data-stu-id="98119-119">TibcoEMS .MessageID</span></span>|<span data-ttu-id="98119-120">string</span><span class="sxs-lookup"><span data-stu-id="98119-120">string</span></span>||<span data-ttu-id="98119-121">只读</span><span class="sxs-lookup"><span data-stu-id="98119-121">Read-only</span></span>|  
|<span data-ttu-id="98119-122">TibcoEMS。优先级</span><span class="sxs-lookup"><span data-stu-id="98119-122">TibcoEMS .Priority</span></span>|<span data-ttu-id="98119-123">integer</span><span class="sxs-lookup"><span data-stu-id="98119-123">integer</span></span>|<span data-ttu-id="98119-124">从 0 到 9</span><span class="sxs-lookup"><span data-stu-id="98119-124">From 0 to 9</span></span>||  
|<span data-ttu-id="98119-125">TibcoEMS。被重新传送</span><span class="sxs-lookup"><span data-stu-id="98119-125">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="98119-126">boolean</span><span class="sxs-lookup"><span data-stu-id="98119-126">boolean</span></span>||<span data-ttu-id="98119-127">只读</span><span class="sxs-lookup"><span data-stu-id="98119-127">Read-only</span></span>|  
|<span data-ttu-id="98119-128">TibcoEMS。ReplyTo</span><span class="sxs-lookup"><span data-stu-id="98119-128">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="98119-129">string</span><span class="sxs-lookup"><span data-stu-id="98119-129">string</span></span>|<span data-ttu-id="98119-130">类似于目标</span><span class="sxs-lookup"><span data-stu-id="98119-130">Similar to Destination</span></span>||  
|<span data-ttu-id="98119-131">TibcoEMS。时间戳</span><span class="sxs-lookup"><span data-stu-id="98119-131">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="98119-132">long</span><span class="sxs-lookup"><span data-stu-id="98119-132">long</span></span>||<span data-ttu-id="98119-133">只读</span><span class="sxs-lookup"><span data-stu-id="98119-133">Read-only</span></span>|  
  
 <span data-ttu-id="98119-134">只读属性是在用于 TIBCO EMS 的 Microsoft BizTalk 适配器传递消息时由 TIBCO Enterprise Message Service 设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="98119-134">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="98119-135">更改此值，但也可以在消息赋值形状中，表达式中不会影响该消息。</span><span class="sxs-lookup"><span data-stu-id="98119-135">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="98119-136">有关必须从 EMS 消息移动到 BizTalk Server 消息的其他属性，必须创建一个属性 DLL 并在项目中使用。</span><span class="sxs-lookup"><span data-stu-id="98119-136">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="98119-137">以下示例属性架构使业务流程，以使用`JMSXDeliveryCount`消息属性。</span><span class="sxs-lookup"><span data-stu-id="98119-137">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
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
  
 <span data-ttu-id="98119-138">请确保使用目标命名空间;仅使用此命名空间的属性复制到 BizTalk Server 消息或 EMS 消息。</span><span class="sxs-lookup"><span data-stu-id="98119-138">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="98119-139">请参阅有关消息上下文属性的详细信息的 BizTalk Server 文档。</span><span class="sxs-lookup"><span data-stu-id="98119-139">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98119-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="98119-140">See Also</span></span>  
[<span data-ttu-id="98119-141">TIBCO EMS 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="98119-141">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)