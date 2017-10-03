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
# <a name="known-issues-with-edi-migration"></a><span data-ttu-id="43567-102">EDI 迁移的已知问题</span><span class="sxs-lookup"><span data-stu-id="43567-102">Known Issues with EDI Migration</span></span>
<span data-ttu-id="43567-103">本主题介绍从 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 中的 EDI/HIPAA 适配器模型迁移到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="43567-103">This topic describes known issues with migration from the EDI/HIPAA adapter model in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a><span data-ttu-id="43567-104">不迁移 FILE 发送端口的凭据信息</span><span class="sxs-lookup"><span data-stu-id="43567-104">Credential Information Not Migrated for a FILE Send Port</span></span>  
 <span data-ttu-id="43567-105">使用 FILE 传输类型迁移发送端口时，如果主机没有访问网络共享位置的权限，则无法迁移用于访问文件夹的凭据。</span><span class="sxs-lookup"><span data-stu-id="43567-105">When migrating a send port using the FILE transport type, the credentials used to access the file folder when the host does not have access to the network share will not be migrated.</span></span> <span data-ttu-id="43567-106">迁移后，你将需要手动启用凭据，并输入用户名和密码，才能使用在**身份验证**页**文件传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="43567-106">After migration, you will need to manually enable credentials, and enter the user name and password to be used, on the **Authentication** page of the **FILE Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43567-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43567-107">See Also</span></span>  
 <span data-ttu-id="43567-108">[EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="43567-108">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 [<span data-ttu-id="43567-109">EDI 迁移实用工具</span><span class="sxs-lookup"><span data-stu-id="43567-109">EDI Migration Utilities</span></span>](../core/edi-migration-utilities.md)