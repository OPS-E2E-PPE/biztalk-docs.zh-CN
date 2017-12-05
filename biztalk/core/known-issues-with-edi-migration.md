---
title: "EDI 迁移的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd62c1c965e814929537a62dc5d49be7e017ae3b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-edi-migration"></a>EDI 迁移的已知问题
本主题介绍中的 EDI/HIPAA 适配器模型从迁移的已知的问题[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]给 BizTalk Server。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>不迁移 FILE 发送端口的凭据信息  
 使用 FILE 传输类型迁移发送端口时，如果主机没有访问网络共享位置的权限，则无法迁移用于访问文件夹的凭据。 迁移后，你将需要手动启用凭据，并输入用户名和密码，才能使用在**身份验证**页**文件传输属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 迁移实用工具](../core/edi-migration-utilities.md)