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
ms.openlocfilehash: 6ceea893a49512167242eb6552e6a23c5a84cd18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966222"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="5f7db-102">维护不可否认性数据库表</span><span class="sxs-lookup"><span data-stu-id="5f7db-102">Maintaining the Non-Repudiation Database Tables</span></span>
<span data-ttu-id="5f7db-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储消息，以在 BTARNArchive 数据库的 MessageStorageIn 和 MessageStorageOut 表中的不可否认目的。</span><span class="sxs-lookup"><span data-stu-id="5f7db-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="5f7db-104">这些表中的许多消息都可能影响系统的性能。</span><span class="sxs-lookup"><span data-stu-id="5f7db-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="5f7db-105">可以根据需要对不可否认性数据库表中的消息定期进行清除和存档，以便维护这些数据库表。</span><span class="sxs-lookup"><span data-stu-id="5f7db-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="5f7db-106">日常数据库维护</span><span class="sxs-lookup"><span data-stu-id="5f7db-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="5f7db-107">当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收消息时，它总是将消息保存在 MessageStorageIn 表中，并**ToBePurged**字段为"1"，表示该消息不需要的不可否认。</span><span class="sxs-lookup"><span data-stu-id="5f7db-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5f7db-108"> 然后进行解密和解码消息以确定协议。</span><span class="sxs-lookup"><span data-stu-id="5f7db-108"> then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="5f7db-109">在解密和解码后，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将检查协议，确定是否必须保存消息以确保不可否认性。</span><span class="sxs-lookup"><span data-stu-id="5f7db-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="5f7db-110">如果是，则设置**ToBePurged**字段为"0"和消息的其他字段中填充。</span><span class="sxs-lookup"><span data-stu-id="5f7db-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="5f7db-111">如果没有，则会使**ToBePurged**字段为"1"，并不填写消息的其他字段。</span><span class="sxs-lookup"><span data-stu-id="5f7db-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="5f7db-112"> 不会自动删除的消息**ToBePurged**字段设置为"1"。</span><span class="sxs-lookup"><span data-stu-id="5f7db-112"> does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="5f7db-113">而且，BTARN 不会将那些为确保不可否认性而保存的消息存档到其他表中。</span><span class="sxs-lookup"><span data-stu-id="5f7db-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="5f7db-114">这两个消息集可以在 MessageStorageIn 表中建立，但影响性能。</span><span class="sxs-lookup"><span data-stu-id="5f7db-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="5f7db-115">您可能要执行以下数据库的日常维护：</span><span class="sxs-lookup"><span data-stu-id="5f7db-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="5f7db-116">运行存储的过程包含以下 SQL 语句，以删除所有消息在 MessageStorageIn 表中其**ToBePurged**字段不等于"0":</span><span class="sxs-lookup"><span data-stu-id="5f7db-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="5f7db-117">在适当的时间段（公司策略中可能有此规定）后，运行存储过程，将不可否认性消息存档到不会影响性能的脱机数据库中。</span><span class="sxs-lookup"><span data-stu-id="5f7db-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="5f7db-118">您可以使用来确定此时间段**TimeCreated** MessageStorageIn 表中的字段。</span><span class="sxs-lookup"><span data-stu-id="5f7db-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="5f7db-119">在消息的不可否认性时间段到期后，可以使用以下 SQL 语句（该语句删除七天前的消息）从存档数据库中删除消息：</span><span class="sxs-lookup"><span data-stu-id="5f7db-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="5f7db-120">**TimeCreated** MessageStorageIn 表中的字段是 utc 格式。</span><span class="sxs-lookup"><span data-stu-id="5f7db-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f7db-121">在传入消息刚传入的一个小时内，不应该将其删除。</span><span class="sxs-lookup"><span data-stu-id="5f7db-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="5f7db-122">当 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送传出消息时，它可以访问不可否认性协议。</span><span class="sxs-lookup"><span data-stu-id="5f7db-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="5f7db-123">如果协议要求具有不可否认性，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息保存在 MessageStorageOut 表中。</span><span class="sxs-lookup"><span data-stu-id="5f7db-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="5f7db-124">如果不要求不可否认性，它不会将消息保存在该表中。</span><span class="sxs-lookup"><span data-stu-id="5f7db-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="5f7db-125">这意味着没有无需**ToBePurged**此表中的字段。</span><span class="sxs-lookup"><span data-stu-id="5f7db-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="5f7db-126">对 MessageStorageOut 表需要进行的全部维护是：在适当的时间段后，将不可否认性消息存档到脱机数据库中，并在每条消息的不可否认性时间段到期后，将其删除。</span><span class="sxs-lookup"><span data-stu-id="5f7db-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="5f7db-127">可以使用以下 SQL 语句（该语句删除七天前的消息）执行这些操作：</span><span class="sxs-lookup"><span data-stu-id="5f7db-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f7db-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f7db-128">See Also</span></span>  
 <span data-ttu-id="5f7db-129">[RNIF 消息处理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5f7db-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="5f7db-130">管理配置、证书、数据库和安全性</span><span class="sxs-lookup"><span data-stu-id="5f7db-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)