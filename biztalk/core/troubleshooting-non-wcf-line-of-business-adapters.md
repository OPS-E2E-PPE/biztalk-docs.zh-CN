---
title: 故障排除非-WCF 业务线适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6cf91a9219f385be1269420ef2965a643bbc29a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296646"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a>故障排除非-WCF 业务线适配器
## <a name="failed-to-retrieve-error"></a>"无法检索"错误  
 使用非-WCF 业务线 LOB 适配器时，可能会出现以下错误：  
  
-   无法检索系统  
  
-   浏览代理：在构造函数中捕获的错误。 目标计算机主动拒绝连接。  
  
-   运行时代理：在构造函数中捕获的错误。 目标计算机主动拒绝连接。  
  
### <a name="cause"></a>原因  
 LOB 适配器使用.Net 远程处理。 如果.Net 远程处理激活花费的时间超过预期，适配器可能会返回这些错误。  
  
### <a name="resolution"></a>解决方法  
 创建**StartAgentSleep**注册表项并增大超时值：  
  
1. 打开注册表并转到*HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*。  
  
2. 创建新的 DWORD 值具有以下属性：  
  
    名称：StartAgentSleep  
  
    基址：Decimal  
  
    值数据：1000  
  
   值数据以毫秒 (ms) 为单位。 1000 毫秒等于 1 秒。  
  
   在某些系统中，一秒可能不够。 增大该值并进行测试，以帮助确定所需的适当超时值。  
  
> [!IMPORTANT]
>  添加**StartAgentSleep**注册表项会影响**所有**非 WCF LOB 适配器。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 适配器疑难解答](../core/troubleshooting-biztalk-server-adapters.md)