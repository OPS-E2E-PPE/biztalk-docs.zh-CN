---
title: "无法创建 AS2 EDIINT MIC 表中的条目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c51cac2861fabaf8fc50269623130c90f3d445b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a><span data-ttu-id="1d07b-102">无法在 AS2 EDIINT MIC 表中创建条目</span><span class="sxs-lookup"><span data-stu-id="1d07b-102">Unable to create the entry in the AS2 EDIINT MIC table</span></span>
## <a name="details"></a><span data-ttu-id="1d07b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1d07b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d07b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1d07b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1d07b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1d07b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1d07b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1d07b-106">Event ID</span></span>|-|  
|<span data-ttu-id="1d07b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1d07b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1d07b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1d07b-108"> EDI</span></span>|  
|<span data-ttu-id="1d07b-109">组件</span><span class="sxs-lookup"><span data-stu-id="1d07b-109">Component</span></span>|<span data-ttu-id="1d07b-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="1d07b-110">AS2 Engine</span></span>|  
|<span data-ttu-id="1d07b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1d07b-111">Symbolic Name</span></span>|<span data-ttu-id="1d07b-112">AS2MicDataStoreCreateEntryError</span><span class="sxs-lookup"><span data-stu-id="1d07b-112">AS2MicDataStoreCreateEntryError</span></span>|  
|<span data-ttu-id="1d07b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1d07b-113">Message Text</span></span>|<span data-ttu-id="1d07b-114">无法在 AS2 EDIINT MIC 表中创建条目。</span><span class="sxs-lookup"><span data-stu-id="1d07b-114">Unable to create the entry in the AS2 EDIINT MIC table.</span></span> <span data-ttu-id="1d07b-115">这可能是由于在该表中写入了重复的 AS2-From、AS2-To 和 MessageID 组合。</span><span class="sxs-lookup"><span data-stu-id="1d07b-115">This could be caused by duplicate AS2-From, AS2-To and MessageID combinations being written to the table.</span></span>  <span data-ttu-id="1d07b-116">错误： {0}</span><span class="sxs-lookup"><span data-stu-id="1d07b-116">Error: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d07b-117">解释</span><span class="sxs-lookup"><span data-stu-id="1d07b-117">Explanation</span></span>  
 <span data-ttu-id="1d07b-118">此错误表明数据库连接出现问题或者数据库表中已存在行密钥。</span><span class="sxs-lookup"><span data-stu-id="1d07b-118">This error indicates either database connection problems or the row keys already exist in the database table.</span></span> <span data-ttu-id="1d07b-119">完整的错误消息应该提供有关插入操作失败的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="1d07b-119">The full error message should provide information as to why the insert operation failed.</span></span> <span data-ttu-id="1d07b-120">收到 MDN 后已将表中的条目删除（无论成功还是失败），因此收到 MDN 后应该从不会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="1d07b-120">The entries in the table are removed after the MDN has been received (whether successful or failed), so this error should never happen after the MDN has been received.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d07b-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="1d07b-121">User Action</span></span>  
 <span data-ttu-id="1d07b-122">若要解决此错误，请检查有关插入操作失败的原因的信息的完整的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1d07b-122">To resolve this error, check the full error message for information about why the insert operation failed.</span></span> <span data-ttu-id="1d07b-123">在 SQL 中，在 EDIINT_MIC 表中，确定是否有重复的 AS2-从和 AS2-到 MessageID 组合。</span><span class="sxs-lookup"><span data-stu-id="1d07b-123">In SQL, in the EDIINT_MIC table, determine whether there is duplicate AS2-From and AS2-To MessageID combinations.</span></span> <span data-ttu-id="1d07b-124">如果出现这种情况，请将它们删除。</span><span class="sxs-lookup"><span data-stu-id="1d07b-124">If so, remove them.</span></span>