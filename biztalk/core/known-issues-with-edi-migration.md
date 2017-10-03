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
ms.openlocfilehash: b642c56151750232be3d17aa3f3cb3b8c858474c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-migration"></a>EDI 迁移的已知问题
本主题介绍从 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 中的 EDI/HIPAA 适配器模型迁移到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的已知问题。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>不迁移 FILE 发送端口的凭据信息  
 使用 FILE 传输类型迁移发送端口时，如果主机没有访问网络共享位置的权限，则无法迁移用于访问文件夹的凭据。 迁移后，你将需要手动启用凭据，并输入用户名和密码，才能使用在**身份验证**页**文件传输属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 迁移实用工具](../core/edi-migration-utilities.md)