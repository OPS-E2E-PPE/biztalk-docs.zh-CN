---
title: 相关类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eea1801632fbeea4eb598f3973923d2436e1d813
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390218"
---
# <a name="correlation-types"></a><span data-ttu-id="1bf72-102">相关类型</span><span class="sxs-lookup"><span data-stu-id="1bf72-102">Correlation Types</span></span>
<span data-ttu-id="1bf72-103">每个相关集基于**相关类型**，即只需的属性列表。</span><span class="sxs-lookup"><span data-stu-id="1bf72-103">Each correlation set is based on a **correlation type**, which is simply a list of properties.</span></span> <span data-ttu-id="1bf72-104">这些属性可能是数据属性，可在消息本身或上下文属性，描述系统或与消息中所传达的数据无关的消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf72-104">These properties might be data properties, which are found in the message itself, or context properties, which describe details of the system or messages that are unrelated to the data being conveyed in the message.</span></span>  
  
 <span data-ttu-id="1bf72-105">在多个相关集，可以使用相关类型。</span><span class="sxs-lookup"><span data-stu-id="1bf72-105">You can use a correlation type in more than one correlation set.</span></span> <span data-ttu-id="1bf72-106">如果你需要对相关类型中的属性的不同值相关联，则必须创建新的相关集，可以一次初始化每个相关集。</span><span class="sxs-lookup"><span data-stu-id="1bf72-106">If you need to correlate on different values for the properties in a correlation type, you must create a new correlation set—each correlation set can be initialized only once.</span></span>  
  
 <span data-ttu-id="1bf72-107">你可以升级属性架构声明一条消息中的某些属性是可以访问您的业务流程中的属性。</span><span class="sxs-lookup"><span data-stu-id="1bf72-107">You can promote properties in a property schema to declare that certain properties in a message are accessible to your orchestration.</span></span> <span data-ttu-id="1bf72-108">有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf72-108">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1bf72-109">未设置系统定义的属性**BTS。CorrelationToken**每条消息与该键相关联。</span><span class="sxs-lookup"><span data-stu-id="1bf72-109">Do not set the system-defined property **BTS.CorrelationToken** that is associated with each message.</span></span> <span data-ttu-id="1bf72-110">这由关联消息，该引擎使用，并将其设置可能会导致您丢失消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1bf72-110">This is used by the engine in correlating messages, and setting it could result in your orchestration losing messages.</span></span>  
  
## <a name="validating-message-correlation-on-send-actions"></a><span data-ttu-id="1bf72-111">验证对发送操作消息相关性</span><span class="sxs-lookup"><span data-stu-id="1bf72-111">Validating Message Correlation on Send Actions</span></span>  
 <span data-ttu-id="1bf72-112">你可以验证将从您的业务流程发送消息的属性以确保它反映了其相关集中的属性。</span><span class="sxs-lookup"><span data-stu-id="1bf72-112">You can validate the properties of a message that you send from your orchestration to ensure that it reflects the properties in its correlation set.</span></span> <span data-ttu-id="1bf72-113">默认情况下，此验证已禁用。</span><span class="sxs-lookup"><span data-stu-id="1bf72-113">By default, this validation is disabled.</span></span> <span data-ttu-id="1bf72-114">有关如何启用它的信息，请参阅[业务流程引擎的运行时验证](../core/runtime-validation-for-the-orchestration-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf72-114">For information on how to enable it, see [Runtime Validation for the Orchestration Engine](../core/runtime-validation-for-the-orchestration-engine.md).</span></span>