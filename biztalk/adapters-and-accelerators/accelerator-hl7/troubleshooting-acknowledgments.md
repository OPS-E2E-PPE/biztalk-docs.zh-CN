---
title: "故障排除确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-acknowledgments"></a>故障排除的确认
解决与相关的问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认。  
  
## <a name="acknowledgments-are-not-generated"></a>确认不会生成  
 有几个确认 (Ack) 不生成或接收的潜在原因。 查看以下列表的潜在问题。  
  
### <a name="symptom"></a>故障现象  
 当你更新方中的信息时，不会生成确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器以生成确认。  
  
**可能的原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]缓存并方配置信息每隔 15 分钟刷新一次。  
  
**解析**： 等待至少 15 分钟缓存刷新或重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的更改立即生效。  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不生成 Ack 且事件错误出现在事件日志。  
  
**可能的原因**： 时中的批，无法生成 ACK / 出消息的批处理包含空 FHS11 字段。  
  
**解析**： 确保你的消息具有正确格式化和填充 FHS11 字段。  
  
### <a name="symptom"></a>故障现象  
 你的应用程序无法生成或接收确认  
  
**可能的原因**: MSH3 字段中的消息的不正确信息会阻止[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从发送消息确认。  
  
**解析**： 确保你的消息具有正确格式化和填充 MSH3 字段。  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a>挂起或未路由到发送方确认  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息发送到双向适配器，而不生成确认。  
  
**可能的原因**： 消息订阅配置不正确。  
  
**解析**： 确保消息的订阅已存在并且配置正确。  
  
## <a name="suspended-acknowledgments"></a>挂起的确认  
  
### <a name="symptom"></a>故障现象  
 确认挂起并显示错误消息"字段中找到的分隔符"配置该参与方将具有如包含分隔符的字符进行编码时@-！ $。  
  
**可能的原因**： 消息包含如句点 （.） 或连字符 （-） 字符。 当生成 Ack，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括"。"和"-"时间戳值。  
  
**解析**： 在发送管道，以避免这些错误中禁用验证。  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a>BizTalk Server 生成有关缺少 ACK，使用双向 MLLP 适配器时出错  
  
### <a name="symptom"></a>故障现象  
 事件日志中获取以下或类似错误：  
  
 "无法从网络由于错误接收 ACK"异常来自 HRESULT: 0xC0C01662""  
  
**可能的原因**： 使用单向接收和双向发送端口，因此 BizTalk 没有相应的接收端口，以返回从双向发送端口收到的消息。  
  
**解析**： 这是设计使然，并且你可以忽略该错误消息。  
  
## <a name="see-also"></a>另请参阅  
[在 HL7 疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)