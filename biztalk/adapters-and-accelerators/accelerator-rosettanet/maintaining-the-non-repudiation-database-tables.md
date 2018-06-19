---
title: 维护不可否认性数据库表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, purging
- databases, non-repudiation database
- maintaining databases, purging
- purging databases
- databases, maintaining
- non-repudiation, database
ms.assetid: 29222510-325b-4cd7-854b-6f548a63fd08
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182172eccddcaad684f35335708dce6027fb111f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210605"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a>维护不可否认性数据库表
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储消息，以便不可否认性 BTARNArchive 数据库的 MessageStorageIn 和 MessageStorageOut 表中。 这些表中的许多消息都可能影响系统的性能。 可以根据需要对不可否认性数据库表中的消息定期进行清除和存档，以便维护这些数据库表。  
  
## <a name="routine-database-maintenance"></a>日常数据库维护  
 当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收消息时，它始终将消息保存在 MessageStorageIn 表以及最初设置**ToBePurged**字段为"1"，该值指示消息不需要不可否认性。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]然后解密，并对要确定哪种协议的消息进行解码。 在解密和解码后，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将检查协议，确定是否必须保存消息以确保不可否认性。 如果是，则设置**ToBePurged**为"0"和消息的其他字段中填充字段。 如果没有，则会使**ToBePurged**字段为"1"和不填写消息的其他字段。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会自动删除与消息**ToBePurged**字段设置为"1"。 而且，BTARN 不会将那些为确保不可否认性而保存的消息存档到其他表中。 这两个消息集可以在 MessageStorageIn 表中建立，但影响性能。 您可能要执行以下数据库的日常维护：  
  
-   运行存储的过程包含以下 SQL 语句可删除所有文件中的邮件 MessageStorageIn 表其**ToBePurged**字段是否不等于"0":  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   在适当的时间段（公司策略中可能有此规定）后，运行存储过程，将不可否认性消息存档到不会影响性能的脱机数据库中。 你可以使用来确定此期间**TimeCreated** MessageStorageIn 表中的字段。 在消息的不可否认性时间段到期后，可以使用以下 SQL 语句（该语句删除七天前的消息）从存档数据库中删除消息：  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  **TimeCreated** MessageStorageIn 表中的字段是 utc 格式。  
  
> [!NOTE]
>  在传入消息刚传入的一个小时内，不应该将其删除。  
  
 当 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送传出消息时，它可以访问不可否认性协议。 如果协议要求具有不可否认性，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息保存在 MessageStorageOut 表中。 如果不要求不可否认性，它不会将消息保存在该表中。 这意味着没有无需**ToBePurged**此表中的字段。 对 MessageStorageOut 表需要进行的全部维护是：在适当的时间段后，将不可否认性消息存档到脱机数据库中，并在每条消息的不可否认性时间段到期后，将其删除。 可以使用以下 SQL 语句（该语句删除七天前的消息）执行这些操作：  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a>另请参阅  
 [RNIF 消息处理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)   
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)