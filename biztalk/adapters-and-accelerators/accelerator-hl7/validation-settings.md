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
# <a name="validation-settings"></a>验证设置
使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，可以验证你对 HL7 标准的消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 可确保发送或接收的消息具有符合 HL7 标准的消息结构和正文段。 此外可以验证 HL7 支持自定义数据类型，并允许尾部分隔符。 您使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡可配置验证。  

## <a name="configuring-validation-settings"></a>配置验证设置  
 您使用**验证**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 配置验证设置。 可以选择以下类型的验证：  

- 语法、 结构和示意图正文段，根据消息架构验证  

- HL7 标准验证的自定义数据类型 （DT、 TS、 TM 和 TN）  

- 字段分隔符 （允许使用尾部分隔符） 的验证  

  使用此选项卡，还可以设置用于为此参与方的消息上验证的架构命名空间。  

  下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**验证**选项卡。  

  ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
  BTAHL7 配置资源管理器验证选项卡  

  使用以下过程配置验证设置。  

#### <a name="to-open-btahl7-configuration-explorer"></a>若要打开 BTAHL7 配置资源管理器  

-   单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  

#### <a name="to-configure-validation-settings"></a>配置验证设置  

1. 在 BTAHL7 配置资源管理器上**验证**选项卡上，执行以下操作：  


   |                  使用此选项                  |                                            执行的操作                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         **验证主体段**         |             选择此选项以执行语法、 结构和架构验证。              |
   |       **验证自定义数据类型**        |  选择此选项可对 DT、 TS、 TM，和 TN 自定义数据类型执行 HL7 标准验证。  |
   | **允许尾部分隔符 （分隔符）** |           选择此选项以启用消息实例中的尾部字段分隔符。           |
   |            **架构 Namespace**            | 键入架构命名空间位置。 默认值是 http://microsoft.com/HealthCare/HL7/2X。 |


2. 单击 **“保存”**。  

## <a name="see-also"></a>请参阅  
 [日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [确认设置](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)   
[运行日志记录、消息批处理、验证和确认设置](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)