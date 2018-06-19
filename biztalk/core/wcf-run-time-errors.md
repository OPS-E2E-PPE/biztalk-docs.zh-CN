---
title: WCF 运行时错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97f4107ddf791b8d9fd152f2258cd3185f23498f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288189"
---
# <a name="wcf-run-time-errors"></a>WCF 运行时错误
用于诊断和解决 WCF 运行时事件的信息。  
  
## <a name="wcf-service-host-restarted"></a>WCF 服务主机重新启动
  
||错误详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0x1FB0|  
|事件源|0|  
|组件|0|  
|符号名称|BTS_I_WCF_SERVICE_HOST_RESTARTED|  
|消息正文|0|  
  
## <a name="explanation"></a>解释  
 此消息提供了一种让 WCF 适配器写入“信息性”事件日志项的方法（为适配器提供的 API 允许创建警告或错误，而不是信息）。  
  
## <a name="user-action"></a>用户操作  
 如果您在事件日志中看到此信息性事件，则表示自动恢复已成功。 关于此消息，无需执行任何其他操作。