---
title: "面向合作伙伴和 TPA 组控制编号的规则已耗尽 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1850b968a2c9b4c8d2c16fd90d9e37d80b60f8b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="ad70f-102">组控制编号序列的合作伙伴和 TPA 耗尽</span><span class="sxs-lookup"><span data-stu-id="ad70f-102">Group control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="ad70f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ad70f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad70f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ad70f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ad70f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ad70f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ad70f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ad70f-106">Event ID</span></span>|-|  
|<span data-ttu-id="ad70f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ad70f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ad70f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ad70f-108"> EDI</span></span>|  
|<span data-ttu-id="ad70f-109">组件</span><span class="sxs-lookup"><span data-stu-id="ad70f-109">Component</span></span>|<span data-ttu-id="ad70f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ad70f-110">EDI Engine</span></span>|  
|<span data-ttu-id="ad70f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ad70f-111">Symbolic Name</span></span>|<span data-ttu-id="ad70f-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="ad70f-112">EdiControlNumberExhaustedForParty</span></span>|  
|<span data-ttu-id="ad70f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ad70f-113">Message Text</span></span>|<span data-ttu-id="ad70f-114">TPA {2} 的情况下，组控制编号规则耗尽合作伙伴 {1} 状态。</span><span class="sxs-lookup"><span data-stu-id="ad70f-114">Group control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="ad70f-115">重置 {2}-EDI 属性使用 BizTalk Server 管理中的序列。</span><span class="sxs-lookup"><span data-stu-id="ad70f-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad70f-116">解释</span><span class="sxs-lookup"><span data-stu-id="ad70f-116">Explanation</span></span>  
 <span data-ttu-id="ad70f-117">此错误/警告/信息事件指示 BizTalk Server 无法处理该文档，因为组控件范围已用完在 {2} 协议。</span><span class="sxs-lookup"><span data-stu-id="ad70f-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Group control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad70f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ad70f-118">User Action</span></span>  
 <span data-ttu-id="ad70f-119">若要解决此错误，请点击重置 {2} 协议的控制编号或增大控制编号范围或协议中点击针对控制编号范围规范的重置按钮的复选框。</span><span class="sxs-lookup"><span data-stu-id="ad70f-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>