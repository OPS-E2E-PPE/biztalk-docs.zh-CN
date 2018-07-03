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
ms.openlocfilehash: d6c5e9b2ffe7e74fc7bf14c3d14a22a93e288b30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997040"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a>非 WCF 行业适配器疑难解答
## <a name="failed-to-retrieve-error"></a>“无法检索”错误  
 使用非 WCF 行业 (LOB) 适配器时，可能会发生以下错误：  
  
-   无法检索系统  
  
-   浏览代理： 构造函数中捕获的错误。 目标计算机主动拒绝连接。  
  
-   运行时代理： 构造函数中捕获的错误。 目标计算机主动拒绝连接。  
  
### <a name="cause"></a>原因  
 LOB 适配器使用 .Net 远程处理。 如果 .Net 远程处理激活花费的时间长于预期，适配器可能会返回这些错误。  
  
### <a name="resolution"></a>解决方法  
 创建**StartAgentSleep**注册表项并增大超时值：  
  
1. 打开注册表并转到*HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*。  
  
2. 使用以下属性创建新的 DWORD 值：  
  
    名称： StartAgentSleep  
  
    基本： 十进制  
  
    值数据： 1000年  
  
   值数据以毫秒 (ms) 为单位。 1000 毫秒等于 1 秒。  
  
   在某些系统中，一秒钟可能并不够。 请增大该值并进行测试，以便确定所需的适当超时值。  
  
> [!IMPORTANT]
>  添加**StartAgentSleep**注册表项会影响**所有**非 WCF LOB 适配器。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 适配器疑难解答](../core/troubleshooting-biztalk-server-adapters.md)