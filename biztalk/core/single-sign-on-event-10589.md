---
title: 单一登录： 事件 10589 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56bb848711a627ceaea70085d770db7b0c759e9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271573"
---
# <a name="single-sign-on-event-10589"></a>单一登录： 事件 10589
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10589|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_BACKUP_SECRET_REQUIRED|  
|消息正文|尚未备份主密钥。 如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。 请使用 SSO 管理工具来备份主密钥。|  
  
## <a name="explanation"></a>解释  
 尚未备份主密钥。 如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。  
  
## <a name="user-action"></a>用户操作  
 有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。