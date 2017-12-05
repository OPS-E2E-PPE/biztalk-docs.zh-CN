---
title: "验证设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 574e4a27342680ef4a37f6b12059cbf97bd9584a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="validation-settings"></a><span data-ttu-id="fc1a1-102">验证设置</span><span class="sxs-lookup"><span data-stu-id="fc1a1-102">Validation Settings</span></span>
<span data-ttu-id="fc1a1-103">使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，你可以验证你对 HL7 标准的消息。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="fc1a1-104">确保将发送或接收的消息具有符合 HL7 标准消息结构和正文段。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="fc1a1-105">您还可以验证 HL7 支持自定义数据类型，并允许尾随分隔符。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="fc1a1-106">你使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡以配置验证。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  
  
## <a name="configuring-validation-settings"></a><span data-ttu-id="fc1a1-107">配置验证设置</span><span class="sxs-lookup"><span data-stu-id="fc1a1-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="fc1a1-108">你使用**验证**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 配置验证设置。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="fc1a1-109">你可以选择以下类型的验证：</span><span class="sxs-lookup"><span data-stu-id="fc1a1-109">You can select the following types of validation:</span></span>  
  
-   <span data-ttu-id="fc1a1-110">语法、 结构和示意图正文段，基于消息的架构验证</span><span class="sxs-lookup"><span data-stu-id="fc1a1-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  
  
-   <span data-ttu-id="fc1a1-111">HL7 标准验证自定义数据类型 （DT、 TS、 TM 和 TN）</span><span class="sxs-lookup"><span data-stu-id="fc1a1-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  
  
-   <span data-ttu-id="fc1a1-112">字段分隔符 （允许尾随分隔符） 的验证</span><span class="sxs-lookup"><span data-stu-id="fc1a1-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  
  
 <span data-ttu-id="fc1a1-113">使用此选项卡，还可以设置用于此参与方的消息验证的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  
  
 <span data-ttu-id="fc1a1-114">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  
  
 <span data-ttu-id="fc1a1-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span><span class="sxs-lookup"><span data-stu-id="fc1a1-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span></span>  
<span data-ttu-id="fc1a1-116">BTAHL7 配置资源管理器验证选项卡</span><span class="sxs-lookup"><span data-stu-id="fc1a1-116">BTAHL7 Configuration Explorer Validation tab</span></span>  
  
 <span data-ttu-id="fc1a1-117">使用以下过程配置验证设置。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-117">Use the following procedures to configure validation settings.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="fc1a1-118">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="fc1a1-118">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="fc1a1-119">单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-119">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-validation-settings"></a><span data-ttu-id="fc1a1-120">配置验证设置</span><span class="sxs-lookup"><span data-stu-id="fc1a1-120">To configure validation settings</span></span>  
  
1.  <span data-ttu-id="fc1a1-121">在 BTAHL7 资源上的配置管理器**验证**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc1a1-121">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  
  
    |<span data-ttu-id="fc1a1-122">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fc1a1-122">Use this</span></span>|<span data-ttu-id="fc1a1-123">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fc1a1-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fc1a1-124">**验证正文段**</span><span class="sxs-lookup"><span data-stu-id="fc1a1-124">**Validate body segments**</span></span>|<span data-ttu-id="fc1a1-125">选择此选项以执行语法、 结构和架构验证。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-125">Select this option to perform syntax, structure, and schema validation.</span></span>|  
    |<span data-ttu-id="fc1a1-126">**验证自定义数据类型**</span><span class="sxs-lookup"><span data-stu-id="fc1a1-126">**Validate custom data type**</span></span>|<span data-ttu-id="fc1a1-127">选择此选项以对 DT、 TS、 TM 和 TN 自定义数据类型执行 HL7 标准的验证。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-127">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>|  
    |<span data-ttu-id="fc1a1-128">**允许尾随分隔符 （逗号）**</span><span class="sxs-lookup"><span data-stu-id="fc1a1-128">**Allow trailing delimiters (separators)**</span></span>|<span data-ttu-id="fc1a1-129">选择此选项以启用消息实例中的尾随字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-129">Select this option to enable trailing field delimiters in message instances.</span></span>|  
    |<span data-ttu-id="fc1a1-130">**架构 Namespace**</span><span class="sxs-lookup"><span data-stu-id="fc1a1-130">**Schema Namespace**</span></span>|<span data-ttu-id="fc1a1-131">键入架构命名空间位置。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-131">Type the schema namespace location.</span></span> <span data-ttu-id="fc1a1-132">默认值为 http://microsoft.com/HealthCare/HL7/2X。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-132">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span>|  
  
2.  <span data-ttu-id="fc1a1-133">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="fc1a1-133">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1a1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc1a1-134">See Also</span></span>  
 <span data-ttu-id="fc1a1-135">[日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fc1a1-135">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="fc1a1-136">[确认设置](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="fc1a1-136">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="fc1a1-137">运行日志记录、消息批处理、验证和确认设置</span><span class="sxs-lookup"><span data-stu-id="fc1a1-137">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)