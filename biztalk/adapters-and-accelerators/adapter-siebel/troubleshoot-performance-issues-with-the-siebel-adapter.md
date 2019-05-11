---
title: 使用 Siebel 适配器进行性能问题故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c5ecd89cfe3ea284bdc3264e8db597f29fdde7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370406"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a>使用 Siebel 适配器进行故障排除性能问题：
本部分讨论如何使用故障排除技术来解决使用时可能遇到的性能问题[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
## <a name="known-issues"></a>已知问题  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a>缓慢或停滞在使用适配器与 BizTalk Server 时的吞吐量  
 **问题**  
  
 使用时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，消息发送或接收的适配器数速度变慢或进入停滞。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性中未设置 WCF 自定义发送或接收端口在 BizTalk Server 管理控制台。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[配置的绑定属性用于 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)。  
  
## <a name="see-also"></a>请参阅  
[Siebel 适配器疑难解答](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)