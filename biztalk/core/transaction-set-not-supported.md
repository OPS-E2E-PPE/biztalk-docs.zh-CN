---
title: 不支持事务集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e767e81ba45ab711cc8c84b5f682ac0eba56b5a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001127"
---
# <a name="transaction-set-not-supported"></a><span data-ttu-id="1cbd7-102">不支持事务集</span><span class="sxs-lookup"><span data-stu-id="1cbd7-102">Transaction Set Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="1cbd7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1cbd7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cbd7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1cbd7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1cbd7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1cbd7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1cbd7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1cbd7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1cbd7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1cbd7-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1cbd7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1cbd7-108"> EDI</span></span> |
|    <span data-ttu-id="1cbd7-109">组件</span><span class="sxs-lookup"><span data-stu-id="1cbd7-109">Component</span></span>    |                                       <span data-ttu-id="1cbd7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1cbd7-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="1cbd7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1cbd7-111">Symbolic Name</span></span>  |                              <span data-ttu-id="1cbd7-112">X12TsNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="1cbd7-112">X12TsNotSupportedDescription</span></span>                              |
|  <span data-ttu-id="1cbd7-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1cbd7-113">Message Text</span></span>   |                             <span data-ttu-id="1cbd7-114">不支持事务集</span><span class="sxs-lookup"><span data-stu-id="1cbd7-114">Transaction Set Not Supported</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="1cbd7-115">解释</span><span class="sxs-lookup"><span data-stu-id="1cbd7-115">Explanation</span></span>  
 <span data-ttu-id="1cbd7-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为尚为该事务集的文档类型部署文档架构。</span><span class="sxs-lookup"><span data-stu-id="1cbd7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a document schema has not been deployed for the document type of that transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cbd7-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="1cbd7-117">User Action</span></span>  
 <span data-ttu-id="1cbd7-118">若要解决此错误，请在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中为事务集的文档类型部署文档架构。</span><span class="sxs-lookup"><span data-stu-id="1cbd7-118">To resolve this error, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] deploy a document schema for the document type of the transaction set.</span></span>