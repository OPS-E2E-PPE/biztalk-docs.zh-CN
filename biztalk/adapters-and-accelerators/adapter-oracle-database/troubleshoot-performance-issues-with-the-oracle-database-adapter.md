---
title: 对 Oracle 数据库适配器的性能问题进行故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23c36e2df514f6caf5e654a99c4d57a5c4b41e65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375905"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a>对 Oracle 数据库适配器的性能问题进行故障排除
本部分讨论如何使用故障排除技术来解决使用时可能遇到的性能问题[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
## <a name="known-issue"></a>已知的问题  
 以下是使用时可能遇到的最常见性能问题[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，以及其可能的原因和解决方法。  
  
##  <a name="BKMK_Slowdown"></a> 缓慢或停滞在使用适配器与 BizTalk Server 时的吞吐量  
 **问题**  
  
 使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，消息发送或接收的适配器数速度变慢或进入停滞。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性中未设置 WCF 自定义发送或接收端口在 BizTalk Server 管理控制台。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a>使用 Oracle 数据库适配器执行涉及 FLOAT 数据类型的操作时在 64 位计算机上可能出现的内存泄漏  
 **问题**  
  
 使用时，可能会遇到内存泄漏[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行涉及 FLOAT 数据类型的操作的 64 位计算机上。  
  
 **解决方法**  
  
 安装.NET \<*版本*\> (x64) 64 位计算机上的。  
  
## <a name="see-also"></a>请参阅  
[排查在 Oracle 数据库 adapter.md](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)