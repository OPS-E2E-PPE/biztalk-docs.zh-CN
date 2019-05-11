---
title: 确认疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a66eba1221b30ec142cc44400c60cff6f66e62e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286522"
---
# <a name="troubleshooting-acknowledgments"></a>确认疑难解答
解决了与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认。  
  
## <a name="acknowledgments-are-not-generated"></a>不生成确认  
 有多个确认 (Ack) 不生成或接收的潜在原因。 查看以下潜在问题的列表。  
  
### <a name="symptom"></a>故障现象  
 当更新中的参与方信息时，不会生成确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器生成确认。  
  
**可能的原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]缓存并刷新参与方配置信息每隔 15 分钟。  
  
**解析**:等待至少 15 分钟的缓存刷新，或重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的更改立即生效。  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does 不会生成用于确认和事件日志中出现事件错误。  
  
**可能的原因**:无法生成确认时中的批处理, / 出消息的批包含空 FHS11 字段。  
  
**解析**:请确保消息具有正确格式化和填充 FHS11 字段。  
  
### <a name="symptom"></a>故障现象  
 你的应用程序将无法生成或接收确认。  
  
**可能的原因**:MSH3 字段中的消息的不正确信息可以防止[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从发送消息的确认。  
  
**解析**:请确保消息具有正确格式化和填充 MSH3 字段。  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a>挂起或不会路由至发送方确认  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将消息发送到双向适配器，而不会生成确认。  
  
**可能的原因**:消息订阅的配置不正确。  
  
**解析**:确保消息订阅已存在并且配置正确。  
  
## <a name="suspended-acknowledgments"></a>挂起的确认  
  
### <a name="symptom"></a>故障现象  
 确认挂起并显示错误消息"字段中找到的分隔符"配置该参与方如包含分隔符字符的字符进行编码时@-！ $。  
  
**可能的原因**:该消息包含一个句点 （.） 或连字符 （-） 等字符。 生成 Ack 时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括"。"和"-"时间戳值。  
  
**解析**:禁用在发送管道中要避免这些错误的验证。  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a>BizTalk Server 生成关于缺少确认使用双向处的 MLLP 适配器时的错误  
  
### <a name="symptom"></a>故障现象  
 事件日志中收到以下或类似错误：  
  
 "无法从网络由于错误接收 ACK"异常来自 HRESULT:0xC0C01662""  
  
**可能的原因**:使用单向接收和双向发送端口，因此，BizTalk 没有相应的接收端口以返回来自双向发送端口接收的消息。  
  
**解析**:这是设计使然，并且可以忽略的错误消息。  
  
## <a name="see-also"></a>请参阅  
[HL7 的疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)