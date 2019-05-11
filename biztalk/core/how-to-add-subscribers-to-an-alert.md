---
title: 如何向警报添加订户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034415c8252a8e8adde51136b11185803d39af40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387224"
---
# <a name="how-to-add-subscribers-to-an-alert"></a>如何向警报添加订户
管理员使用**添加订阅**命令将订阅服务器添加到指定的警报。  
  
### <a name="to-add-subscribers-to-an-alert"></a>向警报添加订户  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。 按 **Enter**。  
  
3. 键入 `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`。  
  
   > [!NOTE]
   >  *类型*指定 BAM 用来传送警报的传递方法。 如果指定的电子邮件传递类型必须提供向其传递该警报的电子邮件地址。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何从警报删除订户](../core/how-to-remove-subscribers-from-an-alert.md)