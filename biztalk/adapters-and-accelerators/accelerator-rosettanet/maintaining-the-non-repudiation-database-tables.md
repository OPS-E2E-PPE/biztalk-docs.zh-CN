---
title: 维护不可否认性数据库表 |Microsoft Docs
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
ms.openlocfilehash: e6e3ca48850aa06bdcfd392f8411c28a921df77e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283308"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a>维护不可否认性数据库表
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储消息，以在 BTARNArchive 数据库的 MessageStorageIn 和 MessageStorageOut 表中的不可否认目的。 这些表中的许多消息可能会影响系统性能。 您可能想要通过定期进行清除和存档消息从表中，根据需要维护这些不可否认性数据库表。  
  
## <a name="routine-database-maintenance"></a>常规数据库维护  
 当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收消息时，它总是将消息保存在 MessageStorageIn 表中，并**ToBePurged**字段为"1"，表示该消息不需要的不可否认。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 然后进行解密和解码消息以确定协议。 解密和解码之后,[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]检查协议，请参阅是否必须保存消息的不可否认目的。 如果是，则设置**ToBePurged**字段为"0"和消息的其他字段中填充。 如果没有，则会使**ToBePurged**字段为"1"，并不填写消息的其他字段。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会自动删除的消息**ToBePurged**字段设置为"1"。 此外，不保存的不可否认与其他表的消息存档。 这两个消息集可以建立在 MessageStorageIn 表中，并会影响性能。 在数据库上的日常维护的一部分，你可能想要执行以下操作：  
  
-   运行存储的过程包含以下 SQL 语句，以删除所有消息在 MessageStorageIn 表中其**ToBePurged**字段不等于"0":  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   适当的时间段 （公司策略可能规定） 之后, 运行的脱机数据库不会影响性能的不可否认性消息存档的存储的过程。 您可以使用来确定此时间段**TimeCreated** MessageStorageIn 表中的字段。 一条消息的不可否认期已过之后，可以使用以下 SQL 语句 （这将删除早于七天的消息） 从存档数据库删除该消息：  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  **TimeCreated** MessageStorageIn 表中的字段是 utc 格式。  
  
> [!NOTE]
>  不应删除不超过一小时的传入消息。  
  
 当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发送传出消息时，它有权访问不可否认性协议。 如果协议要求不可否认，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息保存在 MessageStorageOut 表中。 如果没有，它不会保存在表中的消息。 这意味着没有无需**ToBePurged**此表中的字段。 仅维护所需的 MessageStorageOut 表是到脱机的数据库的不可否认性消息存档后适当的时间段，并可在其不可否认期后删除每条消息已过期。 可以使用以下 SQL 语句 （这将删除早于七天的消息） 执行操作：  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a>请参阅  
 [RNIF 消息处理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)   
 [管理配置、证书、数据库和安全性](manage-configuration-certificates-databases-security.md)