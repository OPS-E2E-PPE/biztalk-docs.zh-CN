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
ms.openlocfilehash: 8e8325f999a7793db7bc99aae90666bdfdde8f0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353518"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="7fe48-102">创建控制消息失败，批次 id</span><span class="sxs-lookup"><span data-stu-id="7fe48-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="7fe48-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7fe48-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7fe48-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7fe48-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7fe48-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7fe48-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7fe48-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7fe48-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7fe48-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7fe48-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7fe48-108">EDI</span><span class="sxs-lookup"><span data-stu-id="7fe48-108">EDI</span></span> |
|    <span data-ttu-id="7fe48-109">组件</span><span class="sxs-lookup"><span data-stu-id="7fe48-109">Component</span></span>    |                                       <span data-ttu-id="7fe48-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7fe48-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7fe48-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7fe48-111">Symbolic Name</span></span>  |                               <span data-ttu-id="7fe48-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="7fe48-112">CreateControlMessageFailed</span></span>                               |
|  <span data-ttu-id="7fe48-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7fe48-113">Message Text</span></span>   |                  <span data-ttu-id="7fe48-114">创建控制消息失败，批次 id {0}。</span><span class="sxs-lookup"><span data-stu-id="7fe48-114">Creation of Control Message failed for Batch id {0}.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="7fe48-115">解释</span><span class="sxs-lookup"><span data-stu-id="7fe48-115">Explanation</span></span>  
 <span data-ttu-id="7fe48-116">此错误/警告/信息事件表明 BizTalk Server 已启动/停止某个批处理。</span><span class="sxs-lookup"><span data-stu-id="7fe48-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7fe48-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7fe48-117">User Action</span></span>  
 <span data-ttu-id="7fe48-118">若要解决此错误，请确保所包含协议的“协议”属性中存在具有给定 ID 的批处理并且数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="7fe48-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>