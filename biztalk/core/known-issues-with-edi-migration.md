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
# <a name="known-issues-with-edi-migration"></a><span data-ttu-id="52144-102">EDI 迁移的已知问题</span><span class="sxs-lookup"><span data-stu-id="52144-102">Known Issues with EDI Migration</span></span>
<span data-ttu-id="52144-103">本主题介绍中的 EDI/HIPAA 适配器模型从迁移的已知的问题[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="52144-103">This topic describes known issues with migration from the EDI/HIPAA adapter model in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span>  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a><span data-ttu-id="52144-104">不迁移 FILE 发送端口的凭据信息</span><span class="sxs-lookup"><span data-stu-id="52144-104">Credential Information Not Migrated for a FILE Send Port</span></span>  
 <span data-ttu-id="52144-105">使用 FILE 传输类型迁移发送端口时，如果主机没有访问网络共享位置的权限，则无法迁移用于访问文件夹的凭据。</span><span class="sxs-lookup"><span data-stu-id="52144-105">When migrating a send port using the FILE transport type, the credentials used to access the file folder when the host does not have access to the network share will not be migrated.</span></span> <span data-ttu-id="52144-106">迁移后，你将需要手动启用凭据，并输入用户名和密码，才能使用在**身份验证**页**文件传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="52144-106">After migration, you will need to manually enable credentials, and enter the user name and password to be used, on the **Authentication** page of the **FILE Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52144-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52144-107">See Also</span></span>  
 <span data-ttu-id="52144-108">[EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="52144-108">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 [<span data-ttu-id="52144-109">EDI 迁移实用工具</span><span class="sxs-lookup"><span data-stu-id="52144-109">EDI Migration Utilities</span></span>](../core/edi-migration-utilities.md)