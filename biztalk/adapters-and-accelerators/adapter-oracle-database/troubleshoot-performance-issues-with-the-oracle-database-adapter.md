---
title: "解决性能问题与 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba487bcd5d6d245c979dec903613465ae54f8d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a>解决与 Oracle 数据库适配器的性能问题
本部分讨论如何使用故障排除方法来解决在使用时可能遇到的性能问题[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
## <a name="known-issue"></a>已知的问题  
 以下是使用时可能遇到的最常见性能问题[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，以及其可能的原因和解决方法。  
  
##  <a name="BKMK_Slowdown"></a>缓慢或吞吐量与 BizTalk Server 使用适配器时停止  
 **问题**  
  
 使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，由适配器发送或接收的消息数变慢或进入停止。  
  
 **可能的原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性未设置在 WCF 自定义上发送或接收 BizTalk Server 管理控制台中的端口。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a>当使用 Oracle 数据库适配器执行涉及 FLOAT 数据类型的操作的 64 位计算机上可能的内存泄漏  
 **问题**  
  
 使用时，你可能会遇到内存泄漏[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行涉及 FLOAT 数据类型的操作的 64 位计算机上。  
  
 **解决方法**  
  
 安装.NET \<*版本*\> (x64) 64 位计算机上的。  
  
## <a name="see-also"></a>另请参阅  
[解决 Oracle 数据库 adapter.md](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)