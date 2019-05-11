---
title: 使用 EDI 迁移的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480a448691072ec46a2cff1dad8f114ef3e35691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380758"
---
# <a name="known-issues-with-edi-migration"></a>EDI 迁移的已知的问题
本主题介绍从中的 EDI/HIPAA 适配器模型迁移的已知的问题[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]到 BizTalk Server。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>凭据信息不会迁移 FILE 发送端口  
 当迁移使用 FILE 传输类型的发送端口时，将不迁移用于访问文件夹，如果主机不具有访问网络共享位置的凭据。 迁移后，你将需要手动启用凭据，然后输入用户名和密码以进行使用，在**身份验证**页**FILE 传输属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 迁移实用工具](../core/edi-migration-utilities.md)