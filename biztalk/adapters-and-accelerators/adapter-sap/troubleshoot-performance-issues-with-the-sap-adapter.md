---
title: 解决性能问题与 SAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217117"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a>与 SAP 适配器解决性能问题
本部分讨论如何使用故障排除方法来解决在使用时可能遇到的性能问题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
##  <a name="BKMK_SAPSlowdown"></a>缓慢或吞吐量与 BizTalk Server 使用适配器时停止  
 **问题**  
  
 使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，由适配器发送或接收的消息数变慢或进入停止。  
  
 **可能的原因**  
  
 **EnableBizTalkCompatibilityMode**绑定属性未设置在 WCF 自定义上发送或接收 BizTalk Server 管理控制台中的端口。  
  
 **解决方法**  
  
 设置**EnableBizTalkCompatibilityMode**绑定属性为 True。 有关此属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
##  <a name="BKMK_SAPMemLeak"></a>可能的内存泄漏时参数的使用 NULL 值  
 **问题**  
  
 你可能会观察内存泄漏如果 SAP 系统中调用项目时未指定输入或表参数的值。  
  
 **解决方法**  
  
 请确保在调用 SAP 系统中的项目时指定的输入和表的所有参数的值。  
  
## <a name="see-also"></a>另请参阅  
[故障排除 SAP 适配器](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)