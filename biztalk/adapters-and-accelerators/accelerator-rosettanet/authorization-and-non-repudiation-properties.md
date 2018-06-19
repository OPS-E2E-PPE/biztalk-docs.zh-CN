---
title: 授权和不可否认性属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authorization properties
- non-repudiation, properties
ms.assetid: e752b95b-9dae-4403-8f3e-3a0a50acd519
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7018ac2d66455359215db78b17e80414d176f99f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22208173"
---
# <a name="authorization-and-non-repudiation-properties"></a><span data-ttu-id="7c280-102">授权和不可否认性属性</span><span class="sxs-lookup"><span data-stu-id="7c280-102">Authorization and Non-Repudiation Properties</span></span>
<span data-ttu-id="7c280-103">本主题介绍了合作伙伴界面进程 (PIP) 的 `Is Authorization Required` 属性、`Non-Repudiation of Origin and Content` 属性，以及 `Non-Repudiation Required (Acknowledgement of Receipt)` 属性的行为。</span><span class="sxs-lookup"><span data-stu-id="7c280-103">This topic describes the behavior of the `Is Authorization Required`, `Non-Repudiation of Origin and Content`, and `Non-Repudiation Required (Acknowledgement of Receipt)` properties of Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="7c280-104">它还介绍了这些属性的组合， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="7c280-104">It also describes the combinations of these properties that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] supports.</span></span>  
  
 <span data-ttu-id="7c280-105">在设置这些属性**活动**选项卡的过程配置设置部分中的过程配置属性[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7c280-105">You set these properties on the **Activity** tab of the Process Configuration properties in the Process Configuration Settings section of the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console.</span></span> <span data-ttu-id="7c280-106">有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="7c280-106">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
## <a name="property-behavior"></a><span data-ttu-id="7c280-107">属性行为</span><span class="sxs-lookup"><span data-stu-id="7c280-107">Property Behavior</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7c280-108"> 根据“是否要求授权”`Is Authorization Required`、“	原始消息和内容的不可否认性”`Non-Repudiation of Origin and Content`以及“要求不可否认性（确认收到）”`Non-Repudiation Required (Acknowledgement of Receipt)`属性的设置表现为以下行为。</span><span class="sxs-lookup"><span data-stu-id="7c280-108"> exhibits the following behavior according to the settings of the `Is Authorization Required`, `Non-Repudiation of Origin and Content`, and `Non-Repudiation Required (Acknowledgement of Receipt)` properties.</span></span>  
  
|<span data-ttu-id="7c280-109">属性</span><span class="sxs-lookup"><span data-stu-id="7c280-109">Property</span></span>|<span data-ttu-id="7c280-110">为 True 时的行为</span><span class="sxs-lookup"><span data-stu-id="7c280-110">Behavior when True</span></span>|<span data-ttu-id="7c280-111">为 False 时的行为</span><span class="sxs-lookup"><span data-stu-id="7c280-111">Behavior when False</span></span>|  
|--------------|------------------------|-------------------------|  
|`Is Authorization Required`|<span data-ttu-id="7c280-112">传入的操作或信号消息必须进行签名;否则为[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="7c280-112">Incoming action or signal messages must be signed; otherwise, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will reject the message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7c280-113"> 如果未授权的个人/角色执行活动，不接受的业务文档。</span><span class="sxs-lookup"><span data-stu-id="7c280-113"> does not accept the business document if the individual/role is not authorized to perform the activity.</span></span>|<span data-ttu-id="7c280-114">传入操作或信号消息无需必须经过签名。</span><span class="sxs-lookup"><span data-stu-id="7c280-114">Incoming action or signal messages do not have to be signed.</span></span> <span data-ttu-id="7c280-115">但仍将使用该消息的 RNIF 头部分的合作伙伴邓氏 (DUNS) 编码来进行简单的验证。</span><span class="sxs-lookup"><span data-stu-id="7c280-115">Simple authorization will still be applied with the partner DUNS number from the RNIF header parts of the message.</span></span>|  
|`Non-Repudiation of Origin and Content`|<span data-ttu-id="7c280-116">将对传出操作或信号消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="7c280-116">Outgoing action or signal messages will be signed.</span></span> <span data-ttu-id="7c280-117">操作消息将以其原始接收格式存储在 BTARNDATA 数据库的 MessageStorageOut 表中。</span><span class="sxs-lookup"><span data-stu-id="7c280-117">Action messages will be stored in their original received form in the MessageStorageOut table of the BTARNDATA database.</span></span>|<span data-ttu-id="7c280-118">不存储传出操作或信号消息。</span><span class="sxs-lookup"><span data-stu-id="7c280-118">Outgoing action or signal messages will not be stored.</span></span>|  
|`Non-Repudiation Required (Acknowledgement of Receipt)`|<span data-ttu-id="7c280-119">传入操作或信号消息必须经过签名。</span><span class="sxs-lookup"><span data-stu-id="7c280-119">Incoming action or signal messages must be signed.</span></span> <span data-ttu-id="7c280-120">传入消息将存储在 BTARNDATA 数据库的 MessageStorageIn 表中。</span><span class="sxs-lookup"><span data-stu-id="7c280-120">The incoming message will be stored in the MessageStorageIn table in the BTARNDATA database.</span></span> <span data-ttu-id="7c280-121">在确认中必须包括消息摘要。</span><span class="sxs-lookup"><span data-stu-id="7c280-121">A message digest must be included in the acknowledgement.</span></span>|<span data-ttu-id="7c280-122">不存储传入操作或信号消息。</span><span class="sxs-lookup"><span data-stu-id="7c280-122">Incoming action or signal messages will not be stored.</span></span>|  
  
## <a name="property-support"></a><span data-ttu-id="7c280-123">属性支持</span><span class="sxs-lookup"><span data-stu-id="7c280-123">Property Support</span></span>  
 <span data-ttu-id="7c280-124">下表介绍 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 支持的“是否要求授权”`Is Authorization Required`、“原始消息和内容的不可否认性”`Non-Repudiation of Origin and Content`以及“要求不可否认性（确认收到）”`Non-Repudiation Required (Acknowledgement of Receipt)`属性的组合。</span><span class="sxs-lookup"><span data-stu-id="7c280-124">The following table shows [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] support for combinations of the `Is Authorization Required`, `Non-Repudiation of Origin and Content`, and `Non-Repudiation Required (Acknowledgement of Receipt)` properties.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7c280-125"> 必须是对签名同时的操作的消息和信号消息或既不操作的消息也不单个消息。</span><span class="sxs-lookup"><span data-stu-id="7c280-125"> must either sign both action messages and signal messages, or neither action messages nor single messages.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7c280-126"> 执行不支持签名操作，但不是签名发出信号，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="7c280-126"> does not support signing actions, but not signing signals, or vice versa.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7c280-127">如果 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 对出站消息进行签名，它必须将该消息保存到 BTARNArchive 数据库的 MessageStorageOut 表中。</span><span class="sxs-lookup"><span data-stu-id="7c280-127">If [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] signs an outbound message, it must save the message in the MessageStorageOut table of the BTARNArchive database.</span></span>  
  
|<span data-ttu-id="7c280-128">是否要求授权</span><span class="sxs-lookup"><span data-stu-id="7c280-128">Is Authorization Required</span></span>|<span data-ttu-id="7c280-129">不可否认性的源和内容</span><span class="sxs-lookup"><span data-stu-id="7c280-129">Non-Repudiation of Origin and Content</span></span>|<span data-ttu-id="7c280-130">要求不可否认性（确认收到）</span><span class="sxs-lookup"><span data-stu-id="7c280-130">Non-Repudiation Required (Acknowledgement of Receipt)</span></span>|<span data-ttu-id="7c280-131">BTARN 是否支持？</span><span class="sxs-lookup"><span data-stu-id="7c280-131">Supported by BTARN?</span></span>|  
|-------------------------------|--------------------------------------------|--------------------------------------------------------------|-------------------------|  
|`False`|`False`|`False`|<span data-ttu-id="7c280-132">是</span><span class="sxs-lookup"><span data-stu-id="7c280-132">Yes</span></span>|  
|`False`|`False`|`True`|<span data-ttu-id="7c280-133">否\*</span><span class="sxs-lookup"><span data-stu-id="7c280-133">No\*</span></span>|  
|`False`|`True`|`False`|<span data-ttu-id="7c280-134">否**</span><span class="sxs-lookup"><span data-stu-id="7c280-134">No**</span></span>|  
|`False`|`True`|`True`|<span data-ttu-id="7c280-135">否\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7c280-135">No\*\*\*</span></span>|  
|`True`|`False`|`False`|<span data-ttu-id="7c280-136">是****</span><span class="sxs-lookup"><span data-stu-id="7c280-136">Yes****</span></span>|  
|`True`|`False`|`True`|<span data-ttu-id="7c280-137">是****</span><span class="sxs-lookup"><span data-stu-id="7c280-137">Yes****</span></span>|  
|`True`|`True`|`False`|<span data-ttu-id="7c280-138">是</span><span class="sxs-lookup"><span data-stu-id="7c280-138">Yes</span></span>|  
|`True`|`True`|`True`|<span data-ttu-id="7c280-139">是</span><span class="sxs-lookup"><span data-stu-id="7c280-139">Yes</span></span>|  
  
 <span data-ttu-id="7c280-140">\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为它需要信号进行签名和未签名操作。</span><span class="sxs-lookup"><span data-stu-id="7c280-140">\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support this combination because it requires that signals be signed and actions not be signed.</span></span>  
  
 <span data-ttu-id="7c280-141">** [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为它需要操作进行签名和未签名的信号。</span><span class="sxs-lookup"><span data-stu-id="7c280-141">** [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support this combination because it requires that actions be signed and signals not be signed.</span></span>  
  
 <span data-ttu-id="7c280-142">\*\*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为将不可否认性设置为`True`对于由操作和信号意味着[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]正在执行授权。</span><span class="sxs-lookup"><span data-stu-id="7c280-142">\*\*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support this combination because setting non-repudiation to `True` for both actions and signals means that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] is performing authorization.</span></span> <span data-ttu-id="7c280-143">因此，此组合无效。</span><span class="sxs-lookup"><span data-stu-id="7c280-143">Therefore, this combination is not valid.</span></span>  
  
 <span data-ttu-id="7c280-144">**** 在将“要求不可否认性”`Is Authorization Required`设置为 `True`，将“原始消息和内容的不可否认性”`Non-Repudiation of Origin and Content`设置为 `False` 时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息存储在不可否认性表中。</span><span class="sxs-lookup"><span data-stu-id="7c280-144">**** When you set `Is Authorization Required` to `True` and `Non-Repudiation of Origin and Content` to `False`, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] stores the message in the non-repudiation table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c280-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c280-145">See Also</span></span>  
 [<span data-ttu-id="7c280-146">如何创建或编辑流程配置</span><span class="sxs-lookup"><span data-stu-id="7c280-146">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)