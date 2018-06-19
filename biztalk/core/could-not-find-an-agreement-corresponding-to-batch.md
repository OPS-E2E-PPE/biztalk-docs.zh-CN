---
title: 找不到对应于批处理协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce17af0e382a137dc8d55d30705da58dd52301c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237925"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a><span data-ttu-id="0bf19-102">找不到对应于批的协议</span><span class="sxs-lookup"><span data-stu-id="0bf19-102">Could not find an Agreement corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="0bf19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0bf19-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bf19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0bf19-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0bf19-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0bf19-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0bf19-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0bf19-106">Event ID</span></span>|-|  
|<span data-ttu-id="0bf19-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0bf19-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0bf19-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0bf19-108"> EDI</span></span>|  
|<span data-ttu-id="0bf19-109">组件</span><span class="sxs-lookup"><span data-stu-id="0bf19-109">Component</span></span>|<span data-ttu-id="0bf19-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0bf19-110">EDI Engine</span></span>|  
|<span data-ttu-id="0bf19-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0bf19-111">Symbolic Name</span></span>|<span data-ttu-id="0bf19-112">AgreementNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="0bf19-112">AgreementNotFoundForBatch</span></span>|  
|<span data-ttu-id="0bf19-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0bf19-113">Message Text</span></span>|<span data-ttu-id="0bf19-114">找不到与批处理 {0} 相对应的协议。</span><span class="sxs-lookup"><span data-stu-id="0bf19-114">Could not find an Agreement corresponding to batch {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0bf19-115">解释</span><span class="sxs-lookup"><span data-stu-id="0bf19-115">Explanation</span></span>  
 <span data-ttu-id="0bf19-116">此错误/警告/信息事件指示 BizTalk Server 找不到启动/停止一批或处理批处理消息一批在尝试时与此 Id 相对应。</span><span class="sxs-lookup"><span data-stu-id="0bf19-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a Batch corresponding to this Id while trying to start/stop a batch or process a batch message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0bf19-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0bf19-117">User Action</span></span>  
 <span data-ttu-id="0bf19-118">若要解决此错误，确保验证具有给定 Id 的批处理中存在包含协议的协议属性。</span><span class="sxs-lookup"><span data-stu-id="0bf19-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement.</span></span>