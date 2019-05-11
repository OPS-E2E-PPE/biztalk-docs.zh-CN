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
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="0c76a-102">维护不可否认性数据库表</span><span class="sxs-lookup"><span data-stu-id="0c76a-102">Maintaining the Non-Repudiation Database Tables</span></span>
<span data-ttu-id="0c76a-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储消息，以在 BTARNArchive 数据库的 MessageStorageIn 和 MessageStorageOut 表中的不可否认目的。</span><span class="sxs-lookup"><span data-stu-id="0c76a-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="0c76a-104">这些表中的许多消息可能会影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="0c76a-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="0c76a-105">您可能想要通过定期进行清除和存档消息从表中，根据需要维护这些不可否认性数据库表。</span><span class="sxs-lookup"><span data-stu-id="0c76a-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="0c76a-106">常规数据库维护</span><span class="sxs-lookup"><span data-stu-id="0c76a-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="0c76a-107">当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收消息时，它总是将消息保存在 MessageStorageIn 表中，并**ToBePurged**字段为"1"，表示该消息不需要的不可否认。</span><span class="sxs-lookup"><span data-stu-id="0c76a-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0c76a-108">然后进行解密和解码消息以确定协议。</span><span class="sxs-lookup"><span data-stu-id="0c76a-108">then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="0c76a-109">解密和解码之后,[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]检查协议，请参阅是否必须保存消息的不可否认目的。</span><span class="sxs-lookup"><span data-stu-id="0c76a-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="0c76a-110">如果是，则设置**ToBePurged**字段为"0"和消息的其他字段中填充。</span><span class="sxs-lookup"><span data-stu-id="0c76a-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="0c76a-111">如果没有，则会使**ToBePurged**字段为"1"，并不填写消息的其他字段。</span><span class="sxs-lookup"><span data-stu-id="0c76a-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0c76a-112">不会自动删除的消息**ToBePurged**字段设置为"1"。</span><span class="sxs-lookup"><span data-stu-id="0c76a-112">does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="0c76a-113">此外，不保存的不可否认与其他表的消息存档。</span><span class="sxs-lookup"><span data-stu-id="0c76a-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="0c76a-114">这两个消息集可以建立在 MessageStorageIn 表中，并会影响性能。</span><span class="sxs-lookup"><span data-stu-id="0c76a-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="0c76a-115">在数据库上的日常维护的一部分，你可能想要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c76a-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="0c76a-116">运行存储的过程包含以下 SQL 语句，以删除所有消息在 MessageStorageIn 表中其**ToBePurged**字段不等于"0":</span><span class="sxs-lookup"><span data-stu-id="0c76a-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="0c76a-117">适当的时间段 （公司策略可能规定） 之后, 运行的脱机数据库不会影响性能的不可否认性消息存档的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="0c76a-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="0c76a-118">您可以使用来确定此时间段**TimeCreated** MessageStorageIn 表中的字段。</span><span class="sxs-lookup"><span data-stu-id="0c76a-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="0c76a-119">一条消息的不可否认期已过之后，可以使用以下 SQL 语句 （这将删除早于七天的消息） 从存档数据库删除该消息：</span><span class="sxs-lookup"><span data-stu-id="0c76a-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="0c76a-120">**TimeCreated** MessageStorageIn 表中的字段是 utc 格式。</span><span class="sxs-lookup"><span data-stu-id="0c76a-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c76a-121">不应删除不超过一小时的传入消息。</span><span class="sxs-lookup"><span data-stu-id="0c76a-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="0c76a-122">当[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发送传出消息时，它有权访问不可否认性协议。</span><span class="sxs-lookup"><span data-stu-id="0c76a-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="0c76a-123">如果协议要求不可否认，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息保存在 MessageStorageOut 表中。</span><span class="sxs-lookup"><span data-stu-id="0c76a-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="0c76a-124">如果没有，它不会保存在表中的消息。</span><span class="sxs-lookup"><span data-stu-id="0c76a-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="0c76a-125">这意味着没有无需**ToBePurged**此表中的字段。</span><span class="sxs-lookup"><span data-stu-id="0c76a-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="0c76a-126">仅维护所需的 MessageStorageOut 表是到脱机的数据库的不可否认性消息存档后适当的时间段，并可在其不可否认期后删除每条消息已过期。</span><span class="sxs-lookup"><span data-stu-id="0c76a-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="0c76a-127">可以使用以下 SQL 语句 （这将删除早于七天的消息） 执行操作：</span><span class="sxs-lookup"><span data-stu-id="0c76a-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c76a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c76a-128">See Also</span></span>  
 <span data-ttu-id="0c76a-129">[RNIF 消息处理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="0c76a-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="0c76a-130">管理配置、证书、数据库和安全性</span><span class="sxs-lookup"><span data-stu-id="0c76a-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)