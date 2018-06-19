---
title: 不支持的功能组版本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b92b7844c750d9a709ac2376bb8f126a32119f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246445"
---
# <a name="functional-group-version-not-supported"></a><span data-ttu-id="0cf2d-102">不支持功能组版本</span><span class="sxs-lookup"><span data-stu-id="0cf2d-102">Functional Group Version Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="0cf2d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0cf2d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0cf2d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0cf2d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0cf2d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0cf2d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0cf2d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0cf2d-106">Event ID</span></span>|-|  
|<span data-ttu-id="0cf2d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0cf2d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0cf2d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0cf2d-108"> EDI</span></span>|  
|<span data-ttu-id="0cf2d-109">组件</span><span class="sxs-lookup"><span data-stu-id="0cf2d-109">Component</span></span>|<span data-ttu-id="0cf2d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0cf2d-110">EDI Engine</span></span>|  
|<span data-ttu-id="0cf2d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0cf2d-111">Symbolic Name</span></span>|<span data-ttu-id="0cf2d-112">X12FaGroupVersionNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="0cf2d-112">X12FaGroupVersionNotSupportedDescription</span></span>|  
|<span data-ttu-id="0cf2d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0cf2d-113">Message Text</span></span>|<span data-ttu-id="0cf2d-114">不支持功能组版本</span><span class="sxs-lookup"><span data-stu-id="0cf2d-114">Functional Group Version Not Supported</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0cf2d-115">解释</span><span class="sxs-lookup"><span data-stu-id="0cf2d-115">Explanation</span></span>  
 <span data-ttu-id="0cf2d-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 BizTalk Server 不支持功能组的段 GS08 中的版本号。</span><span class="sxs-lookup"><span data-stu-id="0cf2d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because BizTalk Server does not support the version number in segment GS08 of a functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0cf2d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0cf2d-117">User Action</span></span>  
 <span data-ttu-id="0cf2d-118">若要解决此错误，请确保 BizTalk Server 支持交换的所有功能中段 GS08 的每个实例中的版本号，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="0cf2d-118">To resolve this error, ensure that the version numbers in each instance of segment GS08 in all functional groups in the interchange are supported by BizTalk Server, and then have the interchange resent.</span></span> <span data-ttu-id="0cf2d-119">请注意，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 产品帮助的“EDI 文档架构支持”主题中列出了 BizTalk Server 致辞后的标准版本。</span><span class="sxs-lookup"><span data-stu-id="0cf2d-119">Note that the standard versions that BizTalk Server supports are listed in the "EDI Document Schema Support" topic of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product help.</span></span>