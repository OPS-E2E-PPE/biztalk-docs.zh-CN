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
ms.openlocfilehash: f0dc316f039e56271f4d5540e3853aa82287b20d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283994"
---
# <a name="defending-against-denial-of-service-attacks"></a>抵御拒绝服务攻击
有人可能会启动拒绝服务攻击的 Microsoft® 安装[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]通过压力过大 RNIFReceive.aspx 接收页。 它们可以通过将大量的空消息发送到该页面这样做。 如果左侧未选中状态，此类攻击可能充满事件日志事件发布的 ASPX 接收页。  
  
## <a name="defending-against-an-attack"></a>抵御攻击  
 若要使服务器抵御拒绝服务攻击，建议你保留在合理的大小的事件日志并采取措施处理过多的事件。 您可以完成此操作的最大日志大小，设置选择覆盖事件，或使用一种[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) 来管理日志的大小。 有关详细信息，请参阅 microsoft 帮助[!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™。  
  
## <a name="see-also"></a>请参阅  
 [管理配置、证书、数据库和安全性](manage-configuration-certificates-databases-security.md)