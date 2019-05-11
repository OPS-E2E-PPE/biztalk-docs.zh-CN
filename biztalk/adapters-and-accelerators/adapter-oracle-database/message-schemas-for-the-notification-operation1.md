---
title: 为通知 Operation1 消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15778686c162b6e8bc3fce7bf87eda94797926f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376416"
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="96c7b-102">通知操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="96c7b-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="96c7b-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]用于从 Oracle 数据库接收数据库更改通知的通知操作的图面。</span><span class="sxs-lookup"><span data-stu-id="96c7b-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the Notification operation to receive database change notifications from the Oracle database.</span></span>  
  
 <span data-ttu-id="96c7b-104">通过设置绑定属性来配置通知操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96c7b-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="96c7b-105">有关与通知相关的绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="96c7b-105">For more information about the Notification-related binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="96c7b-106">您设置**NotificationStatement**绑定属性来指定 SELECT 语句，以在查询通知。</span><span class="sxs-lookup"><span data-stu-id="96c7b-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="96c7b-107">通知操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="96c7b-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="96c7b-108">下表显示了通知操作的 XML 消息结构。</span><span class="sxs-lookup"><span data-stu-id="96c7b-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="96c7b-109">操作</span><span class="sxs-lookup"><span data-stu-id="96c7b-109">Operation</span></span>|<span data-ttu-id="96c7b-110">XML 消息</span><span class="sxs-lookup"><span data-stu-id="96c7b-110">XML Message</span></span>|<span data-ttu-id="96c7b-111">Description</span><span class="sxs-lookup"><span data-stu-id="96c7b-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="96c7b-112">通知</span><span class="sxs-lookup"><span data-stu-id="96c7b-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="96c7b-113">这是 Oracle 数据库发送到适配器客户端的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="96c7b-113">This is the inbound message that is sent by the Oracle database to the adapter clients.</span></span> <span data-ttu-id="96c7b-114">在消息：</span><span class="sxs-lookup"><span data-stu-id="96c7b-114">In the message:</span></span><br /><br /> <span data-ttu-id="96c7b-115">-`<Info>`标记指示通知的原因。</span><span class="sxs-lookup"><span data-stu-id="96c7b-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="96c7b-116">例如，此标记中的"插入"值指示表明已在一个或多个通知语句中引用的表中插入数据。</span><span class="sxs-lookup"><span data-stu-id="96c7b-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="96c7b-117">-`<Source>`标记指示通知的源。</span><span class="sxs-lookup"><span data-stu-id="96c7b-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="96c7b-118">例如，此标记中的"数据"值指示被引用对象中的数据的更改。</span><span class="sxs-lookup"><span data-stu-id="96c7b-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="96c7b-119">同样，此标记中的"对象"值指示被引用对象的更改。</span><span class="sxs-lookup"><span data-stu-id="96c7b-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="96c7b-120">-`<Type>`标记表示的数据更改的类型。</span><span class="sxs-lookup"><span data-stu-id="96c7b-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="96c7b-121">例如，"更新"值中`<Type>`标记指示已更新查询的结果。</span><span class="sxs-lookup"><span data-stu-id="96c7b-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="96c7b-122">通知操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="96c7b-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="96c7b-123">通知操作的消息操作是"<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>。</span><span class="sxs-lookup"><span data-stu-id="96c7b-123">The message action for the notification operation is “<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c7b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c7b-124">See Also</span></span>  
 [<span data-ttu-id="96c7b-125">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="96c7b-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)