---
title: 创建控制消息失败，批次 id |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba63bc570ac29f95c70b5bc6e09050e26c435b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979798"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="ac74c-102">创建控件消息失败，批 ID 为</span><span class="sxs-lookup"><span data-stu-id="ac74c-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="ac74c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ac74c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ac74c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ac74c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ac74c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ac74c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ac74c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ac74c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ac74c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ac74c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ac74c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ac74c-108"> EDI</span></span> |
|    <span data-ttu-id="ac74c-109">组件</span><span class="sxs-lookup"><span data-stu-id="ac74c-109">Component</span></span>    |                                       <span data-ttu-id="ac74c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ac74c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ac74c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ac74c-111">Symbolic Name</span></span>  |                               <span data-ttu-id="ac74c-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="ac74c-112">CreateControlMessageFailed</span></span>                               |
|  <span data-ttu-id="ac74c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ac74c-113">Message Text</span></span>   |                  <span data-ttu-id="ac74c-114">创建控制消息失败，批次 id {0}。</span><span class="sxs-lookup"><span data-stu-id="ac74c-114">Creation of Control Message failed for Batch id {0}.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="ac74c-115">解释</span><span class="sxs-lookup"><span data-stu-id="ac74c-115">Explanation</span></span>  
 <span data-ttu-id="ac74c-116">此错误/警告/信息事件表明 BizTalk Server 已启动/停止某个批处理。</span><span class="sxs-lookup"><span data-stu-id="ac74c-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac74c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ac74c-117">User Action</span></span>  
 <span data-ttu-id="ac74c-118">若要解决此错误，请确保所包含协议的“协议”属性中存在具有给定 ID 的批处理并且数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="ac74c-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>