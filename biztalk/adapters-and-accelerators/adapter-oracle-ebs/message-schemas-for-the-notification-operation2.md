---
title: "通知 Operation2 的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c004e83ada00b41013c2a22c5e48f29bb39ffd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="9049c-102">通知操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="9049c-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="9049c-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]面，用于接收从 Oracle E-business Suite 中的基础数据库的数据库更改通知的通知操作。</span><span class="sxs-lookup"><span data-stu-id="9049c-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces the Notification operation to receive database change notifications from the underlying database in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="9049c-104">通过设置绑定属性配置通知操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9049c-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="9049c-105">有关与通知相关的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9049c-105">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="9049c-106">你设置**NotificationStatement**绑定属性来指定 SELECT 语句，以查询通知。</span><span class="sxs-lookup"><span data-stu-id="9049c-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="9049c-107">通知操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="9049c-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="9049c-108">下表显示通知操作的 XML 消息结构。</span><span class="sxs-lookup"><span data-stu-id="9049c-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="9049c-109">运算</span><span class="sxs-lookup"><span data-stu-id="9049c-109">Operation</span></span>|<span data-ttu-id="9049c-110">XML 消息</span><span class="sxs-lookup"><span data-stu-id="9049c-110">XML Message</span></span>|<span data-ttu-id="9049c-111">Description</span><span class="sxs-lookup"><span data-stu-id="9049c-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="9049c-112">通知</span><span class="sxs-lookup"><span data-stu-id="9049c-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="9049c-113">这是由 Oracle E-business Suite 发送到适配器客户端的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="9049c-113">This is the inbound message that is sent by Oracle E-Business Suite to the adapter clients.</span></span> <span data-ttu-id="9049c-114">中会显示消息：</span><span class="sxs-lookup"><span data-stu-id="9049c-114">In the message:</span></span><br /><br /> <span data-ttu-id="9049c-115">-`<Info>`标记指示通知的原因。</span><span class="sxs-lookup"><span data-stu-id="9049c-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="9049c-116">例如，在该标记中的"插入"值指示，已在一个或多个通知语句中引用的表中插入数据。</span><span class="sxs-lookup"><span data-stu-id="9049c-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="9049c-117">-`<Source>`标记指示通知的源。</span><span class="sxs-lookup"><span data-stu-id="9049c-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="9049c-118">例如，此标记中的"数据"值指示的数据中引用的对象的更改。</span><span class="sxs-lookup"><span data-stu-id="9049c-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="9049c-119">同样，此标记中的"对象"值指示引用的对象中的更改。</span><span class="sxs-lookup"><span data-stu-id="9049c-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="9049c-120">-`<Type>`标记指示的数据更改的类型。</span><span class="sxs-lookup"><span data-stu-id="9049c-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="9049c-121">例如，"更新"值中`<Type>`标记指示已更新查询的结果。</span><span class="sxs-lookup"><span data-stu-id="9049c-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="9049c-122">通知操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="9049c-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="9049c-123">通知操作的消息操作是"通知"。</span><span class="sxs-lookup"><span data-stu-id="9049c-123">The message action for the notification operation is “Notification.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9049c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9049c-124">See Also</span></span>  
 [<span data-ttu-id="9049c-125">消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="9049c-125">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)