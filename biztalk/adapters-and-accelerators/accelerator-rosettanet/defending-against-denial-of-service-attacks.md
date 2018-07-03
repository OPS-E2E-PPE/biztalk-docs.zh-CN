---
title: 抵御拒绝服务攻击 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2aa48e126aafc7b2202547fd72806b5d471ef4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976918"
---
# <a name="defending-against-denial-of-service-attacks"></a>抵御拒绝服务攻击
有人可能会启动拒绝服务攻击的 Microsoft® 安装[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]通过压力过大 RNIFReceive.aspx 接收页。 这些人可以通过向该页发送大量的空消息来达到此目的。 如果状态为不选中，则这种攻击可以使用 ASPX 接收页发布的事件填满事件日志。  
  
## <a name="defending-against-an-attack"></a>抵御攻击  
 要使服务器抵御拒绝服务攻击，建议您将事件日志保持在一个合理的大小，并采取措施处理过多的事件。 可以通过设置最大日志大小、选择覆盖事件的方法或使用 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® 管理规范 (WMI) 管理日志的大小来达到此目的。 有关详细信息，请参阅 microsoft 帮助[!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™。  
  
## <a name="see-also"></a>请参阅  
 [管理配置、证书、数据库和安全性](manage-configuration-certificates-databases-security.md)