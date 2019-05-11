---
title: 使用 SAP 适配器进行性能问题故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c44bf56f73cd23de36e53ae6f0720d863e4f694e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372386"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a>使用 SAP 适配器进行故障排除性能问题：
本部分讨论如何使用故障排除技术来解决使用时可能遇到的性能问题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
##  <a name="BKMK_SAPSlowdown"></a> 缓慢或停滞在使用适配器与 BizTalk Server 时的吞吐量  
 **问题**  
  
 使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，消息发送或接收的适配器数速度变慢或进入停滞。  
  
 **原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性中未设置 WCF 自定义发送或接收端口在 BizTalk Server 管理控制台。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
##  <a name="BKMK_SAPMemLeak"></a> 使用参数的 NULL 值时可能出现的内存泄漏  
 **问题**  
  
 您可能会观察到内存泄漏如果调用 SAP 系统中的项目时未指定输入或表参数的值。  
  
 **解决方法**  
  
 请确保在 SAP 系统中调用项目时指定的输入和表的所有参数的值。  
  
## <a name="see-also"></a>请参阅  
[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)