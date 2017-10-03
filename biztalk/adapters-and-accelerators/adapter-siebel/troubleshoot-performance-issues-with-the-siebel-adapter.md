---
title: "解决性能问题与 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6443dd8b96b19b3cf42f6444ba1ae6c16f2b4ee6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a>与 Siebel 适配器解决性能问题
本部分讨论如何使用故障排除方法来解决在使用时可能遇到的性能问题[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
## <a name="known-issues"></a>已知问题  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a>缓慢或吞吐量与 BizTalk Server 使用适配器时停止  
 **问题**  
  
 使用时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，由适配器发送或接收的消息数变慢或进入停止。  
  
 **可能的原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性未设置在 WCF 自定义上发送或接收 BizTalk Server 管理控制台中的端口。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[为 Siebel 配置的绑定属性](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)。  
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)