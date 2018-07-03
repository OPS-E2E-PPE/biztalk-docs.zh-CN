---
title: 验证设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01f85c02434f8b20124258d95fd484c79809b509
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966318"
---
# <a name="validation-settings"></a><span data-ttu-id="6bfc4-102">验证设置</span><span class="sxs-lookup"><span data-stu-id="6bfc4-102">Validation Settings</span></span>
<span data-ttu-id="6bfc4-103">使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，可以验证你对 HL7 标准的消息。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6bfc4-104"> 可确保发送或接收的消息具有符合 HL7 标准的消息结构和正文段。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="6bfc4-105">此外可以验证 HL7 支持自定义数据类型，并允许尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="6bfc4-106">您使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡可配置验证。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  

## <a name="configuring-validation-settings"></a><span data-ttu-id="6bfc4-107">配置验证设置</span><span class="sxs-lookup"><span data-stu-id="6bfc4-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="6bfc4-108">您使用**验证**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 配置验证设置。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="6bfc4-109">可以选择以下类型的验证：</span><span class="sxs-lookup"><span data-stu-id="6bfc4-109">You can select the following types of validation:</span></span>  

- <span data-ttu-id="6bfc4-110">语法、 结构和示意图正文段，根据消息架构验证</span><span class="sxs-lookup"><span data-stu-id="6bfc4-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  

- <span data-ttu-id="6bfc4-111">HL7 标准验证的自定义数据类型 （DT、 TS、 TM 和 TN）</span><span class="sxs-lookup"><span data-stu-id="6bfc4-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  

- <span data-ttu-id="6bfc4-112">字段分隔符 （允许使用尾部分隔符） 的验证</span><span class="sxs-lookup"><span data-stu-id="6bfc4-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  

  <span data-ttu-id="6bfc4-113">使用此选项卡，还可以设置用于为此参与方的消息上验证的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  

  <span data-ttu-id="6bfc4-114">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  

  <span data-ttu-id="6bfc4-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span><span class="sxs-lookup"><span data-stu-id="6bfc4-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span></span>  
  <span data-ttu-id="6bfc4-116">BTAHL7 配置资源管理器验证选项卡</span><span class="sxs-lookup"><span data-stu-id="6bfc4-116">BTAHL7 Configuration Explorer Validation tab</span></span>  

  <span data-ttu-id="6bfc4-117">使用以下过程配置验证设置。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-117">Use the following procedures to configure validation settings.</span></span>  

#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="6bfc4-118">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="6bfc4-118">To open BTAHL7 Configuration Explorer</span></span>  

-   <span data-ttu-id="6bfc4-119">单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-119">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

#### <a name="to-configure-validation-settings"></a><span data-ttu-id="6bfc4-120">配置验证设置</span><span class="sxs-lookup"><span data-stu-id="6bfc4-120">To configure validation settings</span></span>  

1. <span data-ttu-id="6bfc4-121">在 BTAHL7 配置资源管理器上**验证**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6bfc4-121">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  


   |                  <span data-ttu-id="6bfc4-122">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6bfc4-122">Use this</span></span>                  |                                            <span data-ttu-id="6bfc4-123">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6bfc4-123">To do this</span></span>                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         <span data-ttu-id="6bfc4-124">**验证主体段**</span><span class="sxs-lookup"><span data-stu-id="6bfc4-124">**Validate body segments**</span></span>         |             <span data-ttu-id="6bfc4-125">选择此选项以执行语法、 结构和架构验证。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-125">Select this option to perform syntax, structure, and schema validation.</span></span>              |
   |       <span data-ttu-id="6bfc4-126">**验证自定义数据类型**</span><span class="sxs-lookup"><span data-stu-id="6bfc4-126">**Validate custom data type**</span></span>        |  <span data-ttu-id="6bfc4-127">选择此选项可对 DT、 TS、 TM，和 TN 自定义数据类型执行 HL7 标准验证。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-127">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>  |
   | <span data-ttu-id="6bfc4-128">**允许尾部分隔符 （分隔符）**</span><span class="sxs-lookup"><span data-stu-id="6bfc4-128">**Allow trailing delimiters (separators)**</span></span> |           <span data-ttu-id="6bfc4-129">选择此选项以启用消息实例中的尾部字段分隔符。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-129">Select this option to enable trailing field delimiters in message instances.</span></span>           |
   |            <span data-ttu-id="6bfc4-130">**架构 Namespace**</span><span class="sxs-lookup"><span data-stu-id="6bfc4-130">**Schema Namespace**</span></span>            | <span data-ttu-id="6bfc4-131">键入架构命名空间位置。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-131">Type the schema namespace location.</span></span> <span data-ttu-id="6bfc4-132">默认值是 http://microsoft.com/HealthCare/HL7/2X。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-132">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span> |


2. <span data-ttu-id="6bfc4-133">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="6bfc4-133">Click **Save**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6bfc4-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bfc4-134">See Also</span></span>  
 <span data-ttu-id="6bfc4-135">[日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6bfc4-135">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="6bfc4-136">[确认设置](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="6bfc4-136">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="6bfc4-137">运行日志记录、消息批处理、验证和确认设置</span><span class="sxs-lookup"><span data-stu-id="6bfc4-137">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)